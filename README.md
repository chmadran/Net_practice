# Net_practice

<h2>IP ADDRESS</h2>
An IPv4-adress (where IP stands for Internet Protocol), is an identifier for a computer or device on a network. It is a 32-bit numeric address divided into 4 "blocks", each 4 numbers/each 8 bits, that is 1 octet, separated by a period. The number range in each octet is 0-255 i.e.: 

`192.168.100.1` turns into `11000000.10101000.01100100.00000001`
So the min. value of one "block" is `0` and the max. value is `255`. Why ? 

![image](https://github.com/chmadran/Net_practice/assets/113340699/99aaeed2-2d57-40c9-a3bc-6e3a891fd09c)


To make things easier, we can alias an IP address with a human-readable name called a domain name. For example (at the time of writing; IP addresses can change) google.com is the domain name used on top of the IP address 142.250.190.78. So using the domain name is the easiest way for us to reach a computer over the Internet.

An IP address consists of : 
* a network address : a unique number assigned to a network
* a host address : a unique number assigned to host within that network, such as computers, tablets etc

* ![image](https://github.com/chmadran/Net_practice/assets/113340699/f2368cc7-6997-40f1-8937-9ee6f3b4a6e5)


To tell which part is which, thats where the subnet mask comes in. It is a number that ressembles an IP address and it reveals how many bits in the IP address are used for the network by masking the network portion of the IP address.

![image](https://github.com/chmadran/Net_practice/assets/113340699/f1ae5270-4960-46b4-91c7-031b26d5ff14)
![image](https://github.com/chmadran/Net_practice/assets/113340699/b51f8023-aec9-43ce-bdcd-92a15580b761)
![image](https://github.com/chmadran/Net_practice/assets/113340699/bf737a13-3b1c-4042-a2d5-654409d66459)

The following special address-ranges are reserved for Private Networks:    
`10.0.0.0 – 10.255.255.255`  
`172.16.0.0 – 172.31.255.255`  
`192.168.0.0 – 192.168.255.255`  

The following address-range is reserved for so called loopback addresses / localhost:  
`127.0.0.0 – 127.255.255.255`

There is some more special ip-ranges, but for this project, you only need to remember those above.

<h2>MASK ADDRESS</h2>

The same logic applies to the network-mask:
`255.255.255.0` turns into `11111111.11111111.11111111.00000000`

The network-mask, subnet-mask or in our project only called mask is there to decide which range of ip-adresses are part of the same subnet. There are 2 different ways of writing the mask:  
* "Dot-decimal notation": `255.255.255.0`  
* "Class Inter-Domain Routing" or "CIDR": `/24`  (this counts the number of 1s in the subnet mask)

![image](https://github.com/chmadran/Net_practice/assets/113340699/733b64ca-78ff-429b-aabe-7f3132bec987)

The more usable ip-addresses you need in one subnet, the less subnets you will be able to create. Special to the mask is, after one bit was 0 there can't be any 1 bit's anymore. So the only available numbers are:

`255 (binary: 11111111)`  
`254 (binary: 11111110)`  
`252 (binary: 11111100)`  
`248 (binary: 11111000)`  
`240 (binary: 11110000)`  
`224 (binary: 11100000)`  
`192 (binary: 11000000)`  
`128 (binary: 10000000)`  
`0 (binary: 00000000)`  

Through which `255.255.255.0` is a valid mask and `255.255.128.128` is not a valid mask.

One thing to note is how you write in binary is based on : 
![image](https://github.com/chmadran/Net_practice/assets/113340699/c84d8029-9d62-4217-8093-42f4a97c3477)
Or : 

![image](https://github.com/chmadran/Net_practice/assets/113340699/dc9e0264-a24f-4984-a21c-5f14e05687a3)


**In order to have the ability to send packages between two IP-addresses they either need to be part of the same network or they need to be connected by a router which is part of both subnets.**

<h2>Switches</h2>

A switch will enable you to connect more than two devices to the same network. It can turn one ethernet port into many, is a bridge with a lot of outputs.

Its only purpose is to distribute packages to its network.
To see a working example, you can take a look at Level 3.

<h2>Routers</h2>

As previously mentioned a router is an interface which enables communication between different networks.
A router has the ability to be part of multiple networks, in Netpractice this is visualized by the so called Interface.

A Router creates a very own local network with each devide you want to connect having its own local IP address like a flat number in a building where each appartment has the same street address. Web traffic gets to the appropriate device within your home, as routed by the router.

<h2>Subnetting</h2>

Why does an IP address have a network part? Its manageability, its for breaking down a large network into smaller netoworks or subnetworks which is known as **subnetting***. Let's say we have a large amount of computers in one huge computer. Now when one computer wants to talk to another computer, it needs to know how and where to reach that computer.  

And it does this by using **broasdcast**. A broadcast is when a computer sends out data to all computers on a network so it can locate and talk to a certain computer. In order to prevent every computer from broadcasting to every other computer (asking who is [insert IP Address] at the same time) then the network needs to be broken down into smaller networks. To do that, we use **routers**. Broadcasts do not go past routers, they stay within a network. Thats why IP addresses have a network part. 

**Subnetting** is done by changing the default subnet mask by borrowing some of the bits from the host portion. 
![image](https://github.com/chmadran/Net_practice/assets/113340699/6d3c87a3-0817-4a8d-ab87-620ce9b5cd0b)
![image](https://github.com/chmadran/Net_practice/assets/113340699/88e9a814-2149-41fb-932a-19fb72b59753)

It doubles the number of networks but it divides the number of hosts.

IP addressses ans subnet masks come  in 5 different classes but 3 of these are for commercial use. This is the chart of the IP Addresses and the Default Subnet Masks which are class A,B, and C. A very large amount of networks needed? You'll be Class A as you'll have the larget HOST PART of your IP address (3 octets). Class A can produce up to 16Millions, Class B 65000, and Class C 254 IP addresses.

![image](https://github.com/chmadran/Net_practice/assets/113340699/74becdc2-2431-415b-94db-5c0125ee6220)

<h2>NAT : Network address Translation</h2>

<h3>Interesting Ressources</h3>    

* https://github.com/tblaase/Net_Practice

* https://www.youtube.com/watch?v=s_Ntt6eTn94

* https://developer.mozilla.org/en-US/docs/Learn/Common_questions/Web_mechanics/How_does_the_Internet_work   
