- # Internet Protocol (IP)
	- Is a [network layer (layer 3)]( ((64412719-7dde-4652-ae30-ed9ed4768876)) ) communication protocol for relaying #datagram across network boundaries.
	- This layer provides no guarantee about message delivery or notification of failure and hence directly exposes the unreliability to the layer above.
	- Each datagram is encapsulated within an IP packet which identifies the source and the destination addresses, as well as a number of other routing parameters.
	- ## RFC 791 - IPv4
		- 32 bit long addresses (maximum of 4.29 billion addresses). The problem here is that we run out of IP addresses if we want to give every device on the world a unique one. Because of that Network Address Translators (NAT) were introduced. The proposed IP reuse solution was to introduce NAT devices at the edge of the network, each of which would be responsible for maintaining a table mapping of local IP and port tuples to one or more globally unique (public) IP and port tuples The local IP address space behind the translator could then be reused among many different networks, thus solving the address depletion problem.
		- Each address consists of numbers (0-255) concatenated with dots -> 192.168.1.1
		- Instead of this dot-decimal representation you could use the compact CIDR notation. This specifies an IP address, a slash character and a decimal number. The decimal number is the count of consecutive leading 1-bits (from left to right) in the network mask.  The number can also be thought of as the width (in bits) of the network prefix.
		- #### Private network IP Ranges
			- | IP address range | Number of addresses |
			  |--------------------|-------------------------|
			  | 10.0.0.0 - 10.255.255.255 | 16'777'216 |
			  | 172.16.0.0 - 172.31.255.255 | 1'048'576 |
			  | 192.168.0.0 - 192.168.255.255 | 65'536 |
	- ## RFC 2460 - IPv6
		- #WIP
	-
- Source
	- https://hpbn.co/building-blocks-of-udp/
	- https://en.wikipedia.org/wiki/Internet_Protocol
	-