# Frame (protocol data unit)
- Just like a [[Packet]], a frame is a small part of a message in the network. It helps to identify data and determine the way it should be decoded and interpreted. The main difference between a [[Packet]] and a frame is the association with the [[OSI-model]]
- A frame is used in the ((645bb078-6af4-4bd5-9afa-99f9ba197b07))
- A frame, compared to a packet, contains more information about the transmitted message
- consists of a header, payload, and trailer. The header contains control information such as source and destination MAC addresses, frame type, and error-checking information. Frames are used for local network communication between directly connected devices, such as between 
  switches and network interface cards.