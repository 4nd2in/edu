- When you work with a TCP stream, you are guaranteed that all bytes sent will be identical with bytes received and that they will arrive in the same order to the client. TCP is optimised for accurate delivery rather than a timely one.
- TCP uses flags to indicate different states of connectivity
  collapsed:: true
	- **Synchronization (SYN)** is used to establish the three-way-handshake. This is the first packet sent.
	- **Acknowledgement Number (ACK)** s used to acknowledge the receipt of a TCP segment and to communicate the next expected sequence number to the sender. The acknowledgement number field contains the sequence number of the next expected segment, rather than the number of the last received segment
	- **Acknowledgement (ACK)** is used to acknowledge packets which are successful received by the host. The flag is set if the acknowledgement number field contains a valid acknowledgement number
	- **Finish (FIN)** is used to request a connection termination. This is the last packet sent.
	- **Reset (RST)** is used to terminate the connection if the sender feels something is wrong with the TCP connection or that the conversation should not exist
	- **Urgent (URG)** s used to indicate that the data contained in the packet should be prioritized and handled urgently by the receiver. This flag is used in combination with the Urgent Pointer field to identify the location of the urgent data in the packet
	- **Push (PSH)** is used to request immediate data delivery to the receiving host, without waiting for additional data to be buffered on the sender’s side. This flag is commonly used in applications such as real-time audio or video streaming
	- **Window (WND)** is used to communicate the size of the receive window to the sender. The window size is the amount of data that the receiving host is capable of accepting at any given time. The sender should limit the amount of data it sends based on the size of the window advertised by the receiver
	- **Checksum (CHK)** is used to verify the integrity of the TCP segment during transmission. The checksum is computed over the entire segment, including the header and data fields, and is recalculated at each hop along the network path
	- **Sequence Number (SEQ)** is a unique number assigned to each segment by the sender to identify the order in which packets should be received by the receiver. The sequence number is used in conjunction with the acknowledgement number to ensure reliable data transfer and to prevent duplicate packets
- TCP is using a three-way-handshake before sharing any application data
  collapsed:: true
  ![three-way-handshake](../assets/three-way-handshake_1681984421287_0.png)
	- Client picks a random sequence number `x` and sends a **SYN** packet, which may also include additional TCP flags and options.
	- Server increments `x` by one, picks own random sequence number `y`, appends its own set of flags and options, and dispatches the response in a **SYN ACK** packet.
	- Client increments both `x` and `y` by one and completes the handshake by dispatching the last **ACK** packet in the handshake.
- It is important to understand that when using TCP this handshake is made every time a new connection establishes and causes a full roundtrip of #latency before any application data can be transferred