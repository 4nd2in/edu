- # Internet Protocol (IP)
	- Is a [network layer (layer 3)]( ((64412719-7dde-4652-ae30-ed9ed4768876)) ) communication protocol for relaying #datagram across network boundaries.
	- This layer provides no guarantee about message delivery or notification of failure and hence directly exposes the unreliability to the layer above.
	- Each datagram is encapsulated within an IP packet which identifies the source and the destination addresses, as well as a number of other routing parameters.
	- ## RFC 791 - IPv4
		- 32 bit long addresses (maximum of 4.29 billion addresses)
		- Each address consists of numbers (0-255) concatenated with dots -> 192.168.1.1
		- #### Private network IP Ranges
			- | IP address range | Number of addresses |
			  |--------------------|-------------------------|
			  | 10.0.0.0 - 10.255.255.255 | 16'777'216 |
			  | 172.16.0.0 - 172.31.255.255 | 1'048'576 |
			  | 10.0.0.0 - 10.255.255.255| 16'777'216 |
			-
	- ## RFC 2460 - IPv6
		- #WIP
	-
- Source
	- https://hpbn.co/building-blocks-of-udp/
	- https://en.wikipedia.org/wiki/Internet_Protocol
	-