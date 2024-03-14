# Open Systems Interconnection model (OSI model)
	- A single layer N uses services of layer N-1 (and only of that layer) to complete its job and provides an interface to layer N+1 so that N+1 can use services of N.
	- A layer N on one client communicates with layer N on the other client via a defined protocol
	- Layer 1-4 (Media Layers) are responsible for the physical transmission of data and some basic data manipulation. This layers are implemented in the operating systems and drivers
	- Layer 5-7 (Host Layers) are responsible for end-user services and application functionality
	- Different layers of the OSI model use different kinds of protocol data units (PDU)
		- PDU of transport layer is called [[Segment]]
		- PDU of network layer is called [[Packet]]
		- PDU of data link layer is called [[Frame]]
	- ## Application layer (7)
	  id:: 645bb059-accb-4052-951b-6927d78a2919
	- ## Presentation layer (6)
	- ## Session layer (5)
	- ## Transport layer (4)
	  id:: 645bb06d-51da-4253-a0b4-4aeade7bf72e
	- ## Network layer (3)
	  id:: 645bb072-6c02-4323-bbdb-4e7115196663
		-
	- ## Data link layer (2)
	  id:: 645bb078-6af4-4bd5-9afa-99f9ba197b07
		- Known as the most complex layer of the OS model as it hides all the underlying complexities of the hardware from the above layers
		- IT is responsible for the node-to-node delivery of data. Its major role is to ensure error-free transmission of information
		- This layer can be split up into two sub layers:
			- Media Access Control (MAC) which provides flow control and multiplexing for device transmissions over a network.
				- **Framing**: Packets received from the network layer are divided into small frames which then are sent bit-by-bit to the physical layer
				- **Addressing**: This layer encapsulates the source and destination's [[MAC address]] in the header of each frame
			- Logical Link Control (LLC) which provides flow and error control over the physical medium as well as identifies line protocols
				- **Error Control**: With error detection and correction techniques this layer handles corrupted data. Each frame has some bits attached for error control and addressing
				- **Flow Control**: Synchronise the sender's and receiver's speed so that overflows and packet loss are under control
				- **Access Control**: Check which device has control over the channel when multiple devices are using the same one.
	- ## Physical layer (1)
		- This layer provides an interface between the device (eg. computers) and the transmission medium
		- It provides modulation, which is the process of converting the data into radio waves by adding the information to an electrical or optical nerve signal.
		- It is responsible for decisions regarding [[Transmission Modes]]
		- Typically a combination of hardware and software programming makes up the physical layer. Bluetooth is an example protocol of the physical layer
	- ### How to remember
	  collapsed:: true
		- Please Do Not Throw Sausage Pizza Away
		- Alle Priester Saufen Tequila Nach Der Predigt
- Sources
	- https://www.geeksforgeeks.org/physical-layer-in-osi-model/
	- https://www.youtube.com/watch?v=LiyA3mEedYM
	- https://www.baeldung.com/cs/networking-packet-fragment-frame-datagram-segment
- Tags
	- #computer-science