# NetPractice 📡 🌐

<p align="center">
<img src="https://github.com/YounesMoukhlij/Net-Practice_42/assets/123767564/28d056b9-59b6-4986-bd53-421afb7d8668" w alt="mask">

42 school's net_practice project is an introduction to IP addressing, subnet masks and routing. In a training interface, we must solve networking errors over 10 levels.

## Project Infos :

Common Core Project.
Validated : Grade: 100%.
Check out my GitHub profile [Younes Moukhlij](https://github.com/YounesMoukhlij)

<div id="top"></div>

## Table of Contents

- [Important concepts](#important-concepts) 
  - [OSI Model](#osi-model)
  - [TCP/IP](#tcp-transport-layer)
  - [IP address](#ip-address-network-layer)
  - [Subnet mask](#subnet-mask)
  - [Switch](#switch)
  - [Router](#router)
- [Levels](#My-correction-levels)

---

## Important Concepts

In order to have the ability to send packages between two IP-addresses they either need to be part of the same network or they need to be connected by a router which is part of both subnets.


## Special IP-ranges

The following special address-ranges are reserved for Private Networks:<br>
`10.0.0.0 – 10.255.255.255`<br>
`172.16.0.0 – 172.31.255.255`<br>
`192.168.0.0 – 192.168.255.255`<br>

The following address-range is reserved for so called loopback addresses:<br>
`127.0.0.0 – 127.255.255.255`


There is some more special ip-ranges, but for this project, you only need to remember those above.

## Masks

The network-mask, subnet-mask or in our project only called mask is there to decide which range of ip-adresses are part of the same subnet.<br>
There are 2 different ways of writing the mask:

- "Dot-decimal notation": `255.255.255.0`
- "Class Inter-Domain Routing" or "CIDR": `/24`


The more usable ip-addresses you need in one subnet, the less subnets you will be able to create.<br>
To help you understanding it, I found this table very helpful:


| CIDR | Dot-decimal | Number of IP-addresses<br /> per subnet | Usable IP-addresses <br /> per subnet | Number of subnets |
| :---: | :-----------: | :---: | :---: | :---: |
| /32 | 255.255.255.255 | 1 | 0 | 256 |
| /31 | 255.255.255.254 | 2 | 0 | 128 |
| /30 | 255.255.255.252 | 4 | 2 | 64 |
| /29 | 255.255.255.248 | 8 | 6 | 32 |
| /28 | 255.255.255.240 | 16 | 14 | 16 |
| /27 | 255.255.255.224 | 32 | 30 | 8 |
| /26 | 255.255.255.192 | 64 | 62 | 4 |
| /25 | 255.255.255.128 | 128 | 126 | 2 |
| /24 | 255.255.255.0 | 256 | 254 | 1 |


The number of usable IP-addresses per subnet is lower than the total number of IP's because the first address is reserved as the network-address of the subnet and the last address is reserved as a broadcast-adress.<br>
i.e. for mask `255.255.255.252`:<br>
network: `190.3.2.252`<br>
broadcast: `190.3.2.255`<br>
usable IP's: `190.3.2.253`, `190.3.2.254`

## OSI Model:

![osi_model_7_layers](https://github.com/YounesMoukhlij/Net-Practice_42/assets/123767564/9421fb56-f5f7-4be5-a5e0-c4f33250ec9e)

Lets start with a brief introduction of OSI Model (The Open Systems Interconnection), it describes seven layers that computer systems use to communicate over a network. It was the first standard model for network communications, adopted by all major computer and telecommunication companies in the early 1980s.

#### Application Layer:

<p align="centre">
 <img width="1000" height="500" alt="Screen Shot 2024-06-08 at 1 15 38 PM" src="https://github.com/YounesMoukhlij/Net-Practice_42/assets/123767564/c75f4abf-d58b-4421-a148-e36006cab9b3" alt="mask">

- The application layer is the layer closest to the user and is where application-specific protocols and services reside. It defines how applications communicate with each other and handles tasks such as file transfer, email, and web browsing.

#### Presentaion Layer :

<p align="centre">
<img width="1000" height="500" alt="Screen Shot 2024-06-08 at 1 17 45 PM" src="https://github.com/YounesMoukhlij/Net-Practice_42/assets/123767564/63facc4b-08c6-4a29-b1ae-6d736e488fbc">

- The presentation layer is responsible for translating data between different formats and encodings. It ensures that data sent by one application can be understood by another, even if they use different data representations.

  -- ***1st step : Translation*** -> Transform data into binary code.
 
  -- ***2nd step : Compression*** -> Make data light. (When you send a message with WhatsApp you may had noticed that the                    picture's / video's size is less than its old size)
  
  -- ***3rd step : Crypting / Decrypting*** -> Make the data invincible.

#### Session Layer :

<img width="1000" height="500" alt="Screen Shot 2024-06-08 at 5 00 48 PM" src="https://github.com/YounesMoukhlij/Net-Practice_42/assets/123767564/7ddeb3ae-ade0-46cc-97af-a8fbedfe07fc">

#### Transport Layer :

-  The transport layer ensures end-to-end reliable data delivery, handling tasks like segmentation, flow control, and error correction. It provides features like error recovery, segmentation, and re-assembly.

<img width="1000" height="500" alt="Screen Shot 2024-06-08 at 5 03 23 PM" src="https://github.com/YounesMoukhlij/Net-Practice_42/assets/123767564/ba1feab8-c497-4324-9de4-f9986c13d9c9">


  -- ***1st step : Segmentation*** -> Transform data into small segment, which gives to each segment with order (port number, sequence number). 

  -- ***2nd step : Flow Control*** -> Lets imagine this example a computer with a phone.
  the computer's and phone's speed of transforming data is 100 Mbps and 10 Mbps, if the computer starts transforming data with a speed more than 10 Mbps the phone sends a message to the computer to lower the speed down so the phone could recieve packets proberly.

  -- ***3rd step : Determine Protocol*** -> TCP or UDP.
 
<p align="center">
  <img width="1000" height="500" alt="Screen Shot 2024-06-08 at 3 30 08 PM" src="https://github.com/YounesMoukhlij/Net-Practice_42/assets/123767564/b6b8c1cc-2842-4b1f-9bcb-dce78102c9ad"/> 
</p>
  
* Reliability:
TCP stands for **Transmission Control Protocol**. It is a communications standard that enables application programs and devices to exchange messages over a network. It is used to send packets across the internet.
UDP is a connectionless protocol, which means it does not establish a dedicated connection. It simply sends data packets without any guarantee of delivery, order, or error-checking.

* Connection Establishment:
TCP requires a three-way handshake to establish a connection before data can be exchanged, ensuring that both ends are ready to communicate.
UDP does not require any connection establishment process. Clients can simply send data to the server without any prior arrangement.

* Flow Control and Congestion Control:
TCP implements flow control and congestion control mechanisms to manage the rate of data transmission and prevent network congestion.
UDP does not have any built-in flow control or congestion control mechanisms, making it more susceptible to network congestion.

* Overhead:
TCP has a higher overhead due to the additional mechanisms required for reliable data transfer, such as acknowledgments, retransmissions, and sequence numbers.
UDP has a lower overhead as it does not need to maintain a connection or handle reliability, making it more efficient for certain types of applications.

* Use Cases:
TCP is commonly used for applications that require reliable data transmission, such as web browsing, file transfers, and email.
UDP is often used for applications that prioritize speed over reliability, such as real-time applications (e.g., video streaming, online gaming, and VoIP).

TCP guarantees the integrity of the data being communicated over a network. Before it transmits data, TCP establishes a connection between a source and its destination, which remains active until communication begins. It then breaks large amounts of data into smaller packets, while ensuring end-to-end delivery without loss of any data.

#### Network Layer :

<img align="center" width="1000" height="500" alt="Screen Shot 2024-06-08 at 5 55 01 PM" src="https://github.com/YounesMoukhlij/Net-Practice_42/assets/123767564/c9958733-af14-40aa-b6f3-bace2ef8a132">

The network layer is responsible for logical addressing and routing of data packets between different networks. It determines the best path for data to travel from the source to the destination.

**Logical Addressing:**

The Network Layer is responsible for assigning logical addresses, such as IP addresses (IPv4 or IPv6), to devices on the network.
These logical addresses are used to identify the source and destination of data packets as they traverse the network.

**Routing:**

The Network Layer determines the best path for data packets to travel from the source to the destination across multiple networks.
It uses routing algorithms and protocols, such as OSPF (Open Shortest Path First), BGP (Border Gateway Protocol), or RIP (Routing Information Protocol), to make routing decisions.
The router, a Network Layer device, is responsible for forwarding data packets based on the destination address and the routing table information.

#### Data Link Layer:

<img width="1000" height="500" alt="Screen Shot 2024-06-08 at 6 37 51 PM" src="https://github.com/YounesMoukhlij/Net-Practice_42/assets/123767564/813fe4bd-c3a3-4cc5-96b5-5830d03dca93">

##### Error Detection:
The Data Link Layer employs various error detection techniques to identify errors in the transmitted data. Some common error detection methods include:

****Parity Checking:**** The sender adds an extra bit (parity bit) to the data frame, which represents the parity (even or odd) of the data bits. The receiver can then check the parity of the received data and detect if any single-bit errors have occurred.

<img width="895" alt="Screen Shot 2024-06-08 at 7 43 14 PM" src="https://github.com/YounesMoukhlij/Net-Practice_42/assets/123767564/3dd7b2b2-f5e6-44d2-8337-05e1ecca9af3">

****Checksum:**** The sender calculates a checksum (e.g., using algorithms like CRC - Cyclic Redundancy Check) on the data and includes it in the frame. The receiver recalculates the checksum and compares it to the received checksum to detect if any errors have occurred.

<img width="896" alt="Screen Shot 2024-06-08 at 7 46 46 PM" src="https://github.com/YounesMoukhlij/Net-Practice_42/assets/123767564/2fdfe4b3-fbab-49a7-984e-26383b8b6209">

****Frame Check Sequence (FCS):**** The sender appends a cyclic redundancy check (CRC) value to the end of the frame. The receiver calculates the CRC on the received data and compares it to the FCS to detect errors.

##### CSMA

CSMA stands for Carrier Sense Multiple Access, and it is a media access control (MAC) protocol used in computer networking, particularly in local area networks (LANs).

CSMA is a contention-based access method, which means that multiple devices on the network can access the shared communication medium (e.g., a wired Ethernet or wireless network) simultaneously, and they use a specific mechanism to avoid or resolve collisions.

The core principles of CSMA are:

Carrier Sense:
Before transmitting data, a device listens to the communication medium to check if it is currently being used by another device.
If the medium is detected as busy (i.e., another device is transmitting), the device waits for the medium to become available before attempting to transmit.
Multiple Access:
Multiple devices on the network can access the shared communication medium and transmit data.
The CSMA protocol defines the rules and mechanisms that allow these devices to share the medium effectively.

<div align="right">
  <b><a href="#top">↥ back to top</a></b>
</div>
</br>

### TCP/IP

![image](https://github.com/YounesMoukhlij/Net-Practice_42/assets/123767564/8f326585-4348-4070-a2f0-9543fec756c7)

The TCP/IP (Transmission Control Protocol/Internet Protocol) model is a conceptual framework that describes how communication should take place on the internet and other IP-based networks. It is the de facto standard for modern computer networking and forms the foundation of the internet.

The TCP/IP model consists of four distinct layers:

1. Application Layer:
   - This is the layer that interacts directly with the user or application.
   - It defines protocols for specific application-level services, such as HTTP (web browsing), SMTP (email), FTP (file transfer), and DNS (domain name resolution).

2. Transport Layer:
   - The Transport Layer is responsible for end-to-end communication between applications.
   - It provides protocols like TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) to ensure reliable data delivery, flow control, and error correction.

3. Internet Layer:
   - Also known as the Network Layer, this layer is responsible for logical addressing and routing of data packets across multiple networks.
   - The primary protocol at this layer is IP (Internet Protocol), which handles logical addressing (IP addresses) and packet forwarding.

4. Link Layer:
   - The Link Layer deals with the physical and data link aspects of network communication.
   - It encompasses the protocols and hardware specifications for transmitting data over the physical network medium, such as Ethernet, Wi-Fi, or other local area network (LAN) technologies.

The TCP/IP model is simpler and more practical than the OSI (Open Systems Interconnection) reference model, which has seven distinct layers. The TCP/IP model focuses on the essential functionalities required for internetworking, making it the predominant model used in modern computer networks and the internet.

The TCP/IP model has been widely adopted and has become the de facto standard for network communication, enabling the interconnectivity and interoperability of diverse devices and networks that make up the global internet infrastructure.

### IP Address: Network Layer

</br>
<p align="center"> <img src="https://github.com/lpaube/NetPractice/blob/main/img/ip1.png?raw=true" height=250 alt="mask"></p>
</p>
</br>

IP is part of an internet protocol suite, which also includes the transmission control protocol. Together, these two are known as TCP/IP. The internet protocol suite governs rules for packetizing, addressing, transmitting, routing, and receiving data over networks.

IP addressing is a logical means of assigning addresses to devices on a network. Each device connected to the internet requires a unique IP address.

An IP address has two parts; one part identifies the host such as a computer or other device, and the other part identifies the network it belongs to. TCP/IP uses a [subnet mask](#subnet-mask) to separate them.
</br>
</br>

#### IPv4 vs. IPv6

IP addresses come in 2 versions--IPv4 and IPv6:
<br>

<p align="center">
  <kbd><img src="https://github.com/lpaube/NetPractice/blob/main/img/ip_version.png?raw=true" height=100 alt="ip_versions"></kbd>
</p>
<br>

Internet Protocol version 4 (IPv4) defines an IP address as a 32-bit number. However, because of the growth of the Internet and the depletion of available IPv4 addresses, a new version of IP (IPv6), using 128 bits for the IP address, was standardized in 1998. However, only IPv4 addresses are used in NetPractice.
</br>
</br>

#### Public Address vs. Private Address

A public IP address is an IP address that can be accessed directly over the internet and is assigned to your network router by your internet service provider (ISP). A public (or external) IP address helps you connect to the internet from inside your network, to outside your network.

A private IP address is an address your network router assigns to your device. Each device within the same network is assigned a unique private IP address (sometimes called a private network address) — this is how devices on the same internal network talk to each other.

When a network is connected to the internet, it cannot use an IP address from the reserved private IP addresses. The following ranges are reserved for private IP addresses:

```
192.168.0.0 – 192.168.255.255 (65,536 IP addresses)
172.16.0.0 – 172.31.255.255   (1,048,576 IP addresses)
10.0.0.0 – 10.255.255.255     (16,777,216 IP addresses)
```

<div align="right">
  <b><a href="#top">↥ back to top</a></b>
</div>
</br>

---

### Subnet Mask

</br>
<p align="center">
  <kbd><img src="https://github.com/lpaube/NetPractice/blob/main/img/mask1.png?raw=true" height=250 alt="mask"></kbd>
</p>
</br>

A subnet mask is a 32 bits (4 bytes) address used to distinguish between a network address and a host address in the IP address. It defines the range of IP addresses that can be used within a network or a subnet.
</br>
</br>

#### Finding the network address

The _Interface A1_ above has the following properties:

```
IP address | 104.198.241.125
Mask       | 255.255.255.128
```

To determine which portion of the IP address is the network address, we need to apply the mask to the IP address. Let's first convert the mask to its binary form:

```
Mask | 11111111.11111111.11111111.10000000
```

The bits of a mask that are 1 represent the network address, while the remaining bits of a mask that are 0 represent the host address. Let's now convert the IP address to its binary form:

```
IP address | 01101000.11000110.11110001.01111101
Mask       | 11111111.11111111.11111111.10000000
```

We can now apply the mask to the IP address through a [bitwise AND](https://en.wikipedia.org/wiki/Bitwise_operation#AND) to find the network address of the IP:

```
Network address | 01101000.11000110.11110001.00000000
```

Which translates to a network address of `104.198.241.0`.
</br>
</br>

#### Finding the range of host addresses

To determine what host addresses we can use on our network, we have to use the bits of our IP address dedicated to the host address. Let's use our previous IP address and mask:

```
IP address | 01101000.11000110.11110001.01111101
Mask       | 11111111.11111111.11111111.10000000
```

The possible range of our host addresses is expressed through the last 7 bits of the mask which are all 0. Therefore, the range of host addresses is:

```
BINARY  | 0000000 - 1111111
DECIMAL | 0 - 127
```

To get the range of possible IP addresses for our network, we add the range of host addresses to the network address. Our range of possible IP addresses becomes `104.198.241.0 - 104.198.241.127`.

<ins>HOWEVER</ins>, the extremities of the range are reserved for specific uses and cannot be given to an interface:

```
104.198.241.0   | Reserved to represent the network address.
104.198.241.127 | Reserved as the broadcast address; used to send packets to all hosts of a network.
```

Therefore, our real IP range becomes `104.198.241.1 - 104.198.241.126`, which could have been found using an [IP calculator](https://www.calculator.net/ip-subnet-calculator.html).
</br>
</br>

#### CIDR Notation (/24)

The mask can also be represented with the Classless Inter-Domain Routing (CIDR). This form represents the mask as a slash "/", followed by the number of bits that serve as the network address.

Therefore, the mask in the example above of `255.255.255.128`, is equivalent to a mask of `/25` using the CIDR notation, since 25 bits out of 32 bits represent the network address.

<div align="right">
  <b><a href="#top">↥ back to top</a></b>
</div>
</br>

---

### Switch

</br>
<p align="center">
  <kbd><img src="https://github.com/lpaube/NetPractice/blob/main/img/switch1.png?raw=true" height=150 alt="switch"></kbd>
</p>
</br>

A switch connects multiple devices together in a single network. Unlike a router, the switch does not have any interfaces since it only distributes packets to its local network, and cannot talk directly to a network outside of its own.

<div align="right">
  <b><a href="#top">↥ back to top</a></b>
</div>
</br>

---

### Router

</br>
<p align="center">
  <kbd><img src="https://github.com/lpaube/NetPractice/blob/main/img/route1.png?raw=true" height=200 alt="router"></kbd>
</p>
</br>

Just as the switch connects multiple devices on a single network, the router connects multiple networks together. The router has an interface for each network it connects to.

Since the router separates different networks, the range of possible IP addresses on one of its interfaces must not overlap with the range of its other interfaces. An overlap in the IP address range would imply that the interfaces are on the same network.
</br>
</br>

#### Routing Table

</br>
<p align="center">
  <kbd><img src="https://github.com/lpaube/NetPractice/blob/main/img/routing_table1.png?raw=true" height=150 alt="routing_table"></kbd>
</p>
</br>

A routing table is a data table stored in a router or a network host that lists the routes to particular network destinations. In NetPractice, the routing table consists of 2 elements:

- **Destination**: The destination specifies a network address on which a host is the end target of the packets. The route of `default` or `0.0.0.0/0`, is the route that takes effect when no other route is available for an IP destination address. The default route will use the next-hop address to send the packets on their way without giving a specific destination. The default route will match any network.

- **Next hop**: The next hop refers to the next closest router a packet can go through. It is the IP address of the next router on the packet's way. Every single router maintains its routing table with a next hop address.

**Autor** Younes Moukhlij.

<div align="right">
  <b><a href="#top">↥ back to top</a></b>
</div>
</br>

## Levels

<details>
  <summary>Level 1</summary>
  <br>
<img width="1142" alt="Level 1" src="https://github.com/YounesMoukhlij/Net-Practice_42/assets/123767564/73631580-1663-4b8f-b57b-c50e7ec1907c">
  <br>
  <br>

**1.** Since _Client A_ and _Client B_ are on the same network, their IP address must represent the same network in accordance with the subnet mask.
<br>
The subnet mask is _255.255.255.0_, which means that the first 3 bytes of the IP address represent the network, and the 4th byte represents the host. Since we are on the same network, only the host can change.
<br>
The solution will be anything in the range of **104.96.23.0 - 104.96.23.255** excluding the following 3:

- **104.96.23.0:** The first number in the range of hosts (0 in this case) represents the network and cannot be used by a host.
- **104.96.23.255:** The last number in the range of hosts (255 in this case) represents the broadcast address.
- **104.96.23.12:** This address is already used by the host _Client B_.

**2.** The same reasoning as _1._, however the subnet mask is _255.255.0.0_ in this case. The first 2 bytes of the IP address will represent the network; and the last 2 bytes, the host address.
<br>
The solution will be anything in the range of **211.191.0.0 - 211.191.255.255**, excluding:

- **211.191.0.0:** Represents the network address.
- **211.191.255.255:** Represents the broadcast address.
- **211.191.89.75:** Already taken by host _Client C_.

<div align="right">
  <b><a href="#top">↥ back to top</a></b>
</div>
</br>

</details>

---

<details>
  <summary>Level 2</summary>
  <br>
<img width="1013" alt="Level 2" src="https://github.com/YounesMoukhlij/Net-Practice_42/assets/123767564/2679df93-fe5f-4daf-8fcd-0754d3b8dfcf">
  <br>
  <br>

**1.** Since _Client B_ is on the same private network as _Client A_, they should have the exact same subnet mask.
<br>
The solution can only be **255.255.255.224**.

**2.** To understand the subnet mask of _255.255.255.224_, let's look at it in binary form, along with the IP _192.168.20.222_ of _Client B_:

<center>

```
MASK: 11111111.11111111.11111111.11100000
IP:   11000000.10101000.00010100.11011101
```

</center>
As we can see, the first 27 bits represent the IP address, while only the last 5 bits represent the host address.
<br>
All these 27 bits representing the network must stay the same in the IP addresses of hosts on the same network. To get the answer, we can only change the last 5 bits.
<br>
<br>
The answer is in the range of:

```
BIN:  11000000.10101000.00010100.11000000 - 11000000.10101000.00010100.11011111
or
DEC:  192.168.20.192 - 192.168.20.223
```

Excluding:
<br>

- **11000000.10101000.00010100.11000000:** Represents the network address (notice all 0 in the last 5 bits).
- **11000000.10101000.00010100.11011111:** Represents the broadcast address (notice all 1 in the last 5 bits).
- **11000000.10101000.00010100.11011110:** _Client B_ already has that address.

**3.** Here we are introduced the slash "/" notation for the subnet mask on _Interface D1_. A subnet mask of _/30_ means that the first 30 bits of the IP address represent the network address, and the remaining 2 bits represent the host address:

<center>

```
Mask /30: 11111111.11111111.11111111.11111100
```

</center>

We can see that this binary number corresponds to the decimal _255.255.255.252_, therefore it is identical to the mask found on _Interface C1_.
<br>
<br>
The answers can then be any address, as long as they meet the following conditions:

- The network address (first 30 bits) must be identical for _Client D_ and _Client C_.
- The host bits (last 2 bits) cannot be all 1, nor all 0.
- _Client D_ and _Client C_ do not have identical IP addresses.

<div align="right">
  <b><a href="#top">↥ back to top</a></b>
</div>
</br>

</details>

---

<details>
  <summary>Level 3</summary>
  <br>
<img width="1003" alt="Level 3" src="https://github.com/YounesMoukhlij/Net-Practice_42/assets/123767564/3b042c7e-e4ba-4555-a72e-b1d30033fa96">
  <br>
  <br>

This exercise introduces the use of the **switch** (_Switch S_ in this example). The switch links multiple hosts of the same network together.
<br>
<br>

**1.** _Client A_, _Client B_, and _Client C_ are all on the same network. Therefore, they must all have the same subnet mask. Since _Client C_ already has the mask _255.255.255.128_, the mask for _Interface B1_ and for _Interface A1_ will also be _255.255.255.128_ (or in slash notation: _/25_).
<br>
<br>
The IP address of _Interface B1_ and _Interface C1_ must be on the same network range as the IP of _Client A_. This range is:

  <center>

```
104.198.241.0 - 104.198.241.128
```

  </center>
  Excluding of course the network address and the broadcast address.

  <div align="right">
  <b><a href="#top">↥ back to top</a></b>
</div>
</br>

</details>

---

<details>
  <summary>Level 4</summary>
  <br>
<img width="1086" alt="Level 4" src="https://github.com/YounesMoukhlij/Net-Practice_42/assets/123767564/a72ce1d1-819b-4629-9a12-1a2af743aaf7">
  <br>
  <br>

This exercise introduces the **router**. The router is used to link multiple networks together. It does so with the use of multiple interfaces (_Interface R1_, _Interface R2_, and _Interface R3_ in this example).
<br>
<br>

**1.** Since none of the masks on _Interface B1_, _Interface A1_, and _Interface R1_ are entered, we are free to choose our own subnet mask. A mask of **/24** is ideal as it leaves us with the entire 4th byte for the host address, and does not require binary calculations to find the range of possible host addresses.
<br>
<br>
The IP address of _Interface B1_ and _Interface R1_ must have the same network address as the IP address of _Interface A1_. With a subnet of _/24_, the possible range is:

  <center>

```
85.17.5.0 - 85.17.5.255
```

  </center>
  Excluding the network address and the broadcast address.
  <br>
  <br>

Note that we did not interact with the router _Interface R2_ and _Interface R3_, since none of our communications had to reach these sides of the router.

  <div align="right">
  <b><a href="#top">↥ back to top</a></b>
</div>
</br>

</details>

---

<details>
  <summary>Level 5</summary>
  <br>
<img width="1260" alt="Level 5" src="https://github.com/YounesMoukhlij/Net-Practice_42/assets/123767564/25248f8a-9ef7-4b67-a2a5-d8e685553da1">
  <br>
  <br>

This level introduces **routes**. A route contains 2 fields, the first one is the **destination** of outbound packets, the second one is the **next hop** of the packets.
<br>

The **destination** _default_ is equivalent to _0.0.0.0/0_, which will send the packets indiscriminately to the first network address it encounters. A destination address of _122.3.5.3/24_ would send the packets to the network _122.3.5.0_.

  <br>
  The **next hop** is the IP address of the next  router (or internet) interface to which the interface of the current machine must send its packets. 
  <br>
  <br>

**1.** _Client A_ only has 1 route through which it can send its packets. There is no use specifying a numbered destination. The destination _default_ will send the packets to the only path available.
<br>
<br>
The next hop address must be the IP address of the next router's interface on the packets' way. The next interface is _Interface R1_, with the IP address of _54.117.30.126_. Note that the next interface is not _Interface A1_, since this is the sender's own interface.

  <div align="right">
  <b><a href="#top">↥ back to top</a></b>
</div>
</br>

</details>

---

<details>
  <summary>Level 6</summary>
  <br>
  <img width="1207" alt="Level 6" src="https://github.com/YounesMoukhlij/Net-Practice_42/assets/123767564/99410649-dee1-409d-b42a-ff956bd2543f">
  <br>
  <br>

This level introduces the **internet**. The internet behaves like a router. However, if an interface is connected directly or indirectly to the internet, it **cannot** have an IP address in the following reserved private IP ranges:

```
192.168.0.0 - 192.168.255.255 (65,536 IP addresses)
172.16.0.0 - 172.31.255.255   (1,048,576 IP addresses)
10.0.0.0 - 10.255.255.255     (16,777,216 IP addresses)
```

**1.** The **next hop** of the internet is already entered, and matches the IP address of the _Interface R2_. Therefore we only need to bother with the destination of the internet.
<br>
<br>
The internet must send its packets to _Client A_. To do so, the internet's destination must match the network address of _Client A_. Let's find the network address of _Client A_:
<br>
_Client A_'s mask is _255.255.255.128_, which is equivalent to _/25_. This means that the first 25 bits of its IP address are its network address. We know then that the first 3 bytes (24 bits) of its IP address make part of its network address:

  <center>

```
40.178.145.?
```

  </center>

We now only need to find out if the 25th bit is a 1 or a 0.
<br>
If we convert the number 227 to binary, we get `11100011`. The first digit, which corresponds to the 25th bit, is a 1. Since only the 25th bit is part of the network address and not the remaining 7 bits, we get `10000000` for the last byte of the network address, which is 128 in decimal.
<br>
<br>
The full network address is:

  <center>

```
40.178.145.128
```

  </center>

With a range of _40.178.145.129 - 40.178.145.254_ for its host addresses.
<br>
<br>
We can now put this address of **40.178.145.128** in the Internet destination. The **/25** following the destination address represents the mask applied to its address.
<br>
<br>
A destination of _40.178.145.227/25_ is equivalent to the destination address _40.178.145.128/25_, since the mask of _/25_ will turn all the bits after the 25th to 0 to get the destination's network address.

  <div align="right">
  <b><a href="#top">↥ back to top</a></b>
</div>
</br>

</details>

---

<details>
  <summary>Level 7</summary>
  <br>
<img width="1242" alt="Level 7" src="https://github.com/YounesMoukhlij/Net-Practice_42/assets/123767564/4653e83c-8f62-40b0-a39a-761d44e0ac02">
  <br>
  <br>

This level introduces the concept of **overlaps**. The range of IP addresses of a network must not overlap the range of IP addresses of a separate network. Networks are separated by routers.
<br>
<br>

**1.** We have 3 separate networks:
<br>

1. Between _Client A_ and _Router R1_.
2. Between _Router R1_ and _Router R2_.
3. Between _Router R2_ and _Client C_.

For _Interface A1_, we cannot choose our IP address freely since the IP of _Interface R11_ is already entered. Also, if we give it a mask of _/24_, the IP address range will overlap with the range of _Interface R12_, which is already entered. They would both be in the range of _93.198.14.0 - 93.198.14.255_.
<br>
<br>

Since we need addresses for 3 separate networks, it is convenient to split the last bytes of the address into 4 or more address ranges. We do this by using a mask of _/26_ or higher. The mask of _/28_ for example will give us 16 ranges, from which we use the following 3:

```
93.198.14.1 - 93.198.14.14    (Client A to Router R1)
93.198.14.65 - 93.198.14.78   (Router R1 to Router R2)
93.198.14.241 - 93.198.14.254 (Router R2 to Client C)
```

To calculate the possible ranges of a mask:
<br>
https://www.calculator.net/ip-subnet-calculator.html?cclass=any&csubnet=28&cip=93.198.14.2&ctype=ipv4&printit=0&x=97&y=13

  <div align="right">
  <b><a href="#top">↥ back to top</a></b>
</div>
</br>

</details>

---

<details>
  <summary>Level 8</summary>
  <br>
<img width="1061" alt="Level 8" src="https://github.com/YounesMoukhlij/Net-Practice_42/assets/123767564/79fe126e-452c-4483-a01c-2a33a59ac8e4">
  <br>
  <br>

**1.** The hosts _Client C_ and _Client D_ will send packets to the internet, then the internet will respond by sending packets all the way back to the initial sender. To send these packets, the internet uses the destination _49.175.13.0/26_ to send the packets to the networks in the range of `49.175.13.0 - 49.175.13.63`.
<br>
<br>
All the receiving networks must be in this range, without overlapping each other.
<br>
<br>

**2.** On _Interface R23_ and _Interface R22_ we use the mask _255.255.255.240_ (or _/28_), to conveniently split the range of _/26_ from the destination address, into 4 separate ranges. This separation of 4 is necessary since we have the following 3 networks that must not overlap:
<br>

1. _Router R1_ to _Router R2_.
2. _Router R2_ to _Client C_.
3. _Router R2_ to _Client D_.

Each of these networks can then be attributed one of the following IP ranges with a mask of _/28_:

```
49.175.13.0 - 49.175.13.15
49.175.13.16 - 49.175.13.31
49.175.13.32 - 49.175.13.47
49.175.13.48 - 49.175.13.63
```

Note that the network address (first) and the broadcast address (last) must be excluded from each range.
<br>
<br>

**3.** The destination and next hop for the internet are already entered. We only need to enter the next hop for the _Router R2_, which is the IP on the _Interface R21_.

<div align="right">
  <b><a href="#top">↥ back to top</a></b>
</div>
</br>

</details>

---

<details>
  <summary>Level 9</summary>
  <br>
  <img width="1160" alt="Level 9" src="https://github.com/YounesMoukhlij/Net-Practice_42/assets/123767564/e25009d0-fb1f-45c6-88fb-23183f3ffce6">
  <br>
  <br>

This level is quite straightforward since the internet does not initially send its packets to a specific network. Therefore, the separate networks do not need to share a common address range. I would suggest simply following the 6 goals of the level one by one until the level is completed.
<br>
<br>
Remember not to use the network addresses from the reserved private IP ranges.
<br>
<br>

**1.** **Goal 3** states that we must connect _meson_ with the _internet_. The _internet_ will then have to respond to _meson_, so we enter _meson's_ network address in the _internet's_ destination.
<br>
<br>
**Goal 6** states that we must connect _cation_ with the _internet_, so we enter _cation's_ network address in the _internet's_ destination.
<br>
<br>
It is normal to have an empty field for the 3rd destination of the _internet_, and in _Router R1's_ destination. Not all fields of the routing tables need to be filled.

  <div align="right">
  <b><a href="#top">↥ back to top</a></b>
</div>
</br>

</details>

---

<details>
  <summary>Level 10</summary>
  <br>
<img width="1024" alt="Level 10" src="https://github.com/YounesMoukhlij/Net-Practice_42/assets/123767564/8842f2fc-1bd4-45a9-b74c-903ab4465bd4">
  <br>
  <br>

At this level, there are 4 different networks:
<br>

1. _Router R1_ to _Switch S1_
2. _Router R1_ to _Router R2_
3. _Router R2_ to _Client H4_
4. _Router R2_ to _Client H3_
   <br>

**1.** The internet must be able to send its packets to all the hosts, so its destination must cover the range of networks of all the hosts.
<br>
<br>

_Interface R11_ and _Interface R13_ already have an IP address entered. This IP address only differs in its last byte. _Interface R11_ has for last byte **1**, and _Interface R13_ has for last byte **254**. To cover this wide range to IP addresses, we take a mask of **/24** for the _internet's_ destination. This destination will cover a range of `70.101.30.0 - 70.101.30.255`.

  <br>
  <br>

**2.** When choosing the IP addresses, we must make sure of 2 things:
<br>

1. The IP address is covered by the _internet_ destination.
2. The IP address range of the various networks does not overlap.
   <br>

With the IP addresses already entered (greyed out), let's examine the ranges covered by the various networks:
<br>

1. _Router R1_ to _Switch S1_ - Covers the range **70.101.30.0 - 70.101.30.127** (mask /25).
2. _Router R2_ to _Client H4_ - Covers the range **70.101.30.128 - 70.101.30.191** (mask /26).
3. _Router R1_ to _Router R2_ - Covers the range **70.101.30.252 - 70.101.30.255** (mask /30).
4. _Router R2_ to _Client H3_ - ??? (mask ???).

The only IP addresses left for the network "Router R2 to Client H3" are **70.101.30.192 - 70.101.30.251**. We can pick any mask that will let us take 2 IP addresses from that range to put in _Interface R22_ and _Interface R31_.


  <div align="right">
  <b><a href="#top">↥ back to top</a></b>
</div>
</br>

</details>
