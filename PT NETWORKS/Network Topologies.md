Tags:[[PRE- SECURITY]][[Networks]][[Network Structure]][]

A `network topology` is a typical arrangement and `physical` or `logical` connection of devices in a network. Computers are `hosts`, such as `clients` and `servers`, that actively use the network.
The network topology determines the components to be used and the access methods to the transmission media.


We can divide the entire network topology area into three areas:

#### 1. Connections

| `Wired connections`  | `Wireless connections` |
| -------------------- | ---------------------- |
| Coaxial cabling      | Wi-Fi                  |
| Glass fiber cabling  | Cellular               |
| Twisted-pair cabling | Satellite              |
| and others           | and others             |

#### 2. Nodes - Network Interface Controller (NICs)

|||||

	|   Repeaters    |    Hubs    |    Bridges   |     Switches     |
	|  Router/Modem      |     Gateways   |    Firewalls  ||


#### 3. Classifications

We can imagine a topology as a virtual form or `structure of a network`. This form does not necessarily correspond to the actual physical arrangement of the devices in the network. Therefore these topologies can be either `physical` or `logical`. For example, the computers on a `LAN` may be arranged in a circle in a bedroom, but it is very unlikely to have an actual ring topology.

|                |             |
| -------------- | ----------- |
| Point-to-Point | Bus         |
| Star           | Ring        |
| Mesh           | Tree        |
| Hybrid         | Daisy Chain |

## Point-to-Point

![[Pasted image 20250314131812.png]]

## Bus

All hosts are connected via a transmission medium in the bus topology. Every host has access to the transmission medium and the signals that are transmitted over it. There is no central network component that controls the processes on it. The transmission medium for this can be, for example, a `coaxial cable`.

Since the medium is shared with all the others, only `one host can send`, and all the others can only receive and evaluate the data and see whether it is intended for itself.

![[Pasted image 20250314131950.png]]

## Star

The star topology is a network component that maintains a connection to all hosts. Each host is connected to the `central network component` via a separate link. This is usually a router, a hub, or a switch. These handle the `forwarding function` for the data packets. To do this, the data packets are received and forwarded to the destination. The data traffic on the central network component can be very high since all data and connections go through it.

![[Pasted image 20250314132945.png]]

## Ring

The `physical` ring topology is such that each host or node is connected to the ring with two cables:

- One for the `incoming` signals and
- the another for the `outgoing` ones.

![[Pasted image 20250314133228.png]]


## Mesh

Many nodes decide about the connections on a `physical` level and the routing on a `logical` level in meshed networks. Therefore, meshed structures have no fixed topology. There are two basic structures from the basic concept: the `fully meshed` and the `partially meshed` structure.

![[Pasted image 20250314133850.png]]

## Tree

The tree topology is an extended star topology that more extensive local networks have in this structure. This is especially useful when several topologies are combined. This topology is often used, for example, in larger company buildings.

There are both logical tree structures according to the `spanning tree` and physical ones. Modular modern networks, based on structured cabling with a hub hierarchy, also have a tree structure. Tree topologies are also used for `broadband networks` and `city networks` (`MAN`).

![[Pasted image 20250314134324.png]]

## Hybrid

Hybrid networks combine two or more topologies so that the resulting network does not present any standard topologies. For example, a tree network can represent a hybrid topology in which star networks are connected via interconnected bus networks. However, a tree network that is linked to another tree network is still topologically a tree network. A hybrid topology is always created when `two different` basic network topologies are interconnected.

![[Pasted image 20250314134346.png]]

## Daisy Chain

In the daisy chain topology, multiple hosts are connected by placing a cable from one node to another.

Since this creates a chain of connections, it is also known as a daisy-chain configuration in which multiple hardware components are connected in a series. This type of networking is often found in automation technology (`CAN`).

Daisy chaining is based on the physical arrangement of the nodes, in contrast to token procedures, which are structural but can be made independent of the physical layout. The signal is sent to and from a component via its previous nodes to the computer system.

![[Pasted image 20250314135536.png]]