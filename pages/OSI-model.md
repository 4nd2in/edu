# Open Systems Interconnection model (OSI model)
	- A single layer N uses services of layer N-1 (and only of that layer) to complete its job and provides an interface to layer N+1 so that N+1 can use services of N.
	- A layer N on one client communicates with layer N on the other client via a defined protocol
	- Layer 1-4 (Media Layers) are responsible for the physical transmission of data and some basic data manipulation. This layers are implemented in the operating systems and drivers
	- Layer 5-7 (Host Layers) are responsible for end-user services and application functionality
	- Different layers of the OSI model use different kinds of protocol data units (PDU)
		- PDU of transport layer is called [[Segment]]
		- PDUs of network layer are [[Packet]] and [[Datagram]]
		- PDU of data link layer is called [[Frame]]
	- ## Application layer (7)
	  id:: 645bb059-accb-4052-951b-6927d78a2919
	- ## Presentation layer (6)
	- ## Session layer (5)
		-
	- ## Transport layer (4)
	  id:: 645bb06d-51da-4253-a0b4-4aeade7bf72e
		- This layer strongly works together with the network layer. Instead of addressing and routing, this layer is responsible for segmenting and ordering the data. Some protocols of this layer also handle quality of service, congestion avoidance, reliability and packet retransmission.
		- Protocols in this layer are either connection-oriented like [[TCP]] or connectionless like [[UDP]]
	- ## Network layer (3)
	  id:: 645bb072-6c02-4323-bbdb-4e7115196663
		- This layer is responsible to route and send packets over different networks to its correct destination. This allows communication between non-adjacent networks.
			- **Routing**: Each network device a packet transits through is known as a hop. At each hop, the network layer processes the packet. If the packet has reached its final destination, the data is sent to the transport layer. Otherwise, the packet receives a new header and footer and is sent back to the data link layer for forwarding to the next hop.
			- **Fragmantation**: This layer is responsible for breaking down packets into smaller pieces that are too large for the lower layer links. At the destination this fragments are reassembled to the original packet.
		- The most crucial protocol of this layer is [[IP]]
		- The router is an example of a layer three device even though it might also implement some higher layer functions
	- ## Data link layer (2)
	  id:: 645bb078-6af4-4bd5-9afa-99f9ba197b07
		- Known as the most complex layer of the OS model as it hides all the underlying complexities of the hardware from the above layers
		- It is responsible for the node-to-node delivery of data. Its major role is to ensure error-free transmission of information
		- This layer can be split up into two sub layers:
			- Logical Link Control (LLC)
				- This is the higher of the two layers. It acts as an interface between the network layer and the MAC layer
				- **Error Control**: With error detection and correction techniques (like bit correction algorithms) this layer handles corrupted data. Each frame has some bits attached for error control and addressing
				- **Flow Control**: Synchronise the sender's and receiver's speed so that overflows and packet loss are under control
				- **Access Control**: Check which device has control over the channel when multiple devices are using the same one. This is also known as multiplexing
			- Media Access Control (MAC)
				- The MAC layer is closely entwined with the physical layer. The MAC layer controls network access, frame synchronisation, byte/bit stuffing, and link addressing. It encapsulates data from the LLC layer into the appropriate format for the link layer protocol. It also adds and removes a frame checksum to help identify erroneous frames and implements collision detection
				- **Framing**: This involves dividing data into smaller, manageable  units called [[Frame]] before transmission.
				- **Addressing**: This involves including the [[MAC address]] of both the sender and the receiver within the frame header. This allows network devices to determine whether they are the intended recipients of incoming frames and process the data accordingly
		- A typical protocol for this layer is Ethernet. Compared to the physical layer, Ethernet in this layer defines the frame structure, such as addressing schemes.
		- A network switch is an example of a data link layer device
	- ## Physical layer (1)
		- This layer provides an interface between the device (eg. computers) and the transmission medium
		- It provides modulation, which is the process of converting the data into radio waves by adding the information to an electrical or optical nerve signal.
		- It is responsible for decisions regarding [[Transmission Modes]]
		- A typical protocol for this layer is Ethernet. In the physical layer ethernet specifies the characteristics of the physical medium, such as cable types, connectors and signalling methods
	- ### How to remember
	  collapsed:: true
		- Please Do Not Throw Sausage Pizza Away
		- Alle Priester Saufen Tequila Nach Der Predigt
- Sources
	- https://www.linode.com/docs/guides/introduction-to-osi-networking-model/
	- https://www.cloudflare.com/learning/network-layer/what-is-the-network-layer/
	- https://www.youtube.com/watch?v=LiyA3mEedYM
	- https://www.geeksforgeeks.org/physical-layer-in-osi-model/
- Tags
	- #computer-science