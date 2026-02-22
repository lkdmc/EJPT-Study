## Network Fundamentals
- Network Protocols
	- hosts communicate with each other through the user of network protocols.
- Packets
	- information is transferred by packets.
	- nothing but streams of bits running as electric signals
	- signals are interpreted as bits (zeros and one)
	- ![[Pasted image 20260222211104.png]]
	- Header: 
		- protocol-specific structure, ensures the receiving host can interpret the payload and handle the overall communication
	- Payload:
		- actual information, (email message)
-

## OSI Model (open systems interconnection)
- Conceptual framework that standardizes the functions of a telecommunication.
- **Seven layers**
- ![[Pasted image 20260222211334.png]]

## Network Layer
- IPv4
	- 32-bit
- IPv6
	- 128-bit

### Internet Protocol (IP) Functionality
- Logical Addressing:
	- assigned to network interfaces. uniquely assigned to a each address
- Packet Structure
- Fragmentation and Reassembly
- IP Addressing Types
- Subnetting
	- divides a large IP network into smaller, more manageable sub-networks. enhances network efficiency and security.
- Internet Control Message Protocol (ICMP)
- Dynamic Host Configuration Protocol (DHCP)
	- is often used in conjunction with IP to dynamically assign IP addresses to devices on a network, simplifying the process of network configuration.

### IP Header Format
- IP Protocol defines many different fields in the packet header. These fields contain binary values that the IPv4 services reference as they forward packets across the network.
	- IP Source Address - Packet Source
	- IP Destination Address - Packet Destination
	- Time-to-Live (TTL) - An 8-bit value that indicates the remaining life of the packet
	- Type-of-Service (ToS) - The type of service field contains 8-bit binary value that is used to determine the priority of each packet.
	- Protocol - This 8-bit value indicates the data payload type that the packet is carrying
![[Pasted image 20260222213214.png]]![[Pasted image 20260222213247.png]]
![[Pasted image 20260222213344.png]]
![[Pasted image 20260222213452.png]]
![[Pasted image 20260222213617.png]]


## Transport Layer
- TCP: connection-oriented protocol providing reliable and ordered delivery of data
	- accurate, correct order
	- ACK - SYN (3-way handshake)![[Pasted image 20260222215840.png]]![[Pasted image 20260222215538.png]]
- UDP: connectionless protocol that is faster but provides no guarantees regarding the order or reliability of data delivery
	- simple, minimalistic way, stateless (meaning it does not maintain any state information about the communication)
	- Each UDP packet is treated independently, no persistent state maintained between sender and receiver.
	- Unreliable: not guarantee that packets will be delivered. No mechanism to retransmission.
	- 
![[Pasted image 20260222220935.png]]