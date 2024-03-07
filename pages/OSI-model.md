# Open Systems Interconnection model (OSI model)
	- A single layer N uses services of layer N-1 (and only of that layer) to complete its job and provides an interface to layer N+1 so that N+1 can use services of N.
	- A layer N on one client communicates with layer N on the other client via a defined protocol
	- Layer 1-4 (Media Layers) are responsible for the physical transmission of data and some basic data manipulation. This layers are implemented in the operating systems and drivers
	- Layer 5-7 (Host Layers) are responsible for end-user services and application functionality
	- ## Application layer (7)
	  id:: 645bb059-accb-4052-951b-6927d78a2919
	- ## Presentation layer (6)
	- ## Session layer (5)
	- ## Transport layer (4)
	  id:: 645bb06d-51da-4253-a0b4-4aeade7bf72e
	- ## Network layer (3)
	- ## Data link layer (2)
		- Known as the most complex layer of the OS model as it hides all the underlying complexities of the hardware from the above layers
		- IT is responsible for the node-to-node delivery of data. Its major role is to ensure error-free transmission of information
		- Packets received from the network layer are divided into small frames which then are sent bit-by-bit to the physical layer.
	- ## Physical layer (1)
	  collapsed:: true
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
- Tags
	- #computer-science