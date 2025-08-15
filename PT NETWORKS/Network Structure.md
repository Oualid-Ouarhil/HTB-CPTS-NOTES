Tags:[[Networks]]

#### Example No. 1

Building smaller networks and putting Access Control Lists around them is like putting a fence around the property's border that creates specific entry and exit points. Yes, an attacker could jump over the fence, but this looks suspicious and is not common, allowing it to be quickly detected as malicious activity. Why is the printer network talking to the servers over HTTP?

#### Example No. 2

Taking the time to map out and document each network's purpose is like placing lights around the property, making sure all activity can be seen. Why is the printer network talking to the internet at all?

#### Example No. 3

Having bushes around windows is a deterrent to people attempting to open the window. Just like Intrusion Detection Systems like Suricata or Snort are a deterrent to running network scans. Why did a port scan originate from the printer network?

These examples may sound silly, and it is common sense to block a printer from doing all of the above. However, if the printer is on a "flat /24 network" and gets a DHCP address, it can be challenging to place these types of restrictions on them.

![[Pasted image 20250306155018.png]]

The website address or `Uniform Resource Locator` (`URL`) which we enter into our browser is also known as `Fully Qualified Domain Name` (`FQDN`).

The difference between `URL`s and `FQDN`s is that:

- an `FQDN` (`www.hackthebox.eu`) only specifies the address of the "building" and
- an `URL` (`https://www.hackthebox.eu/example?floor=2&office=dev&employee=17`) also specifies the "`floor`," "`office`," "`mailbox`" and the corresponding "`employee`" for whom the package is intended

PRINTERS CAN BE USED TO CONDUCT ATTACKS, SO THEY SHOULD USE THEIR OWN NETWORK