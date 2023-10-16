Nama  : Ihsan Widagdo  
NRP   : 5025211231
Kelas : D  

#TCP
1. What is the IP address and TCP port number used by the client computer (source) that is transferring the alice.txt file to gaia.cs.umass.edu?
   Answer :
   ![image](https://github.com/dagdo03/tcp-udp/assets/95538168/2792bc29-e660-45c2-b60c-50887516cd3e)  
   IP Source = 192.168.86.68 and Source Port = 55639

2. What is the IP address of gaia.cs.umass.edu? On what port number is it sending and receiving TCP segments for this connection?  
   Answer :
   ![image](https://github.com/dagdo03/tcp-udp/assets/95538168/2792bc29-e660-45c2-b60c-50887516cd3e)  
   IP Destination = 128.119.245.12 and Destination Port = 80  

3. a. What is the sequence number of the TCP SYN segment that is used to initiate the TCP connection between the client computer and gaia.cs.umass.edu?  
   b. What is it in this TCP segment that identifies the segment as a SYN segment?  
   c. Will the TCP receiver in this session be able to use Selective Acknowledgments?  
   Answer :
   ![image](https://github.com/dagdo03/tcp-udp/assets/95538168/749d4a00-2b7f-47cd-bd2c-89eb335f260b)  
   a. Sequence Number: 0 and Sequence Number (raw) : 4236649187  
   b. Because has Flags: 0x002 (SYN)  
   c. Yes, because SACK allowed in SYN segment  

4. a. What is the sequence number of the SYNACK segment sent by gaia.cs.umass.edu to the client computer in reply to the SYN?  
   b. What is it in the segment that identifies the segment as a SYNACK segment?  
   c. What is the value of the Acknowledgement field in the SYNACK segment?  
   d. How did gaia.cs.umass.edu determine that value?  
   Answer :  
   ![image](https://github.com/dagdo03/tcp-udp/assets/95538168/6db29df7-f7f6-4266-9e09-705753cfba55)  
   a. Sequence Number: 0 and Sequence Number (raw) : 1068969752  
   b. Because has Flags : 0x012 (SYN, ACK)  
   c. Acknowledgment number : 4236649188  
   d. From sequence number segmen SYN before, that is 4236649187, plus by one  

5. a. What is the sequence number of the TCP segment containing the header of the HTTP POST command?  
   b. How many bytes of data are contained in the payload (data) field of this TCP segment?  
   c. Did all of the data in the transferred file alice.txt fit into this single segment?  
   Answer :
   ![image](https://github.com/dagdo03/tcp-udp/assets/95538168/ed9760b7-f0d9-45ce-9778-4aa19db47457)
   a. Sequence Number: 152041 and Sequence Number (raw): 4236801228  
   b. TCP payload (1385 bytes)  
   c. No, because the packet was sent by MIME multipart  

6. a. At what time was the first segment (the one containing the HTTP POST) in the data-transfer part of the TCP connection sent?  
   b. At what time was the ACK for this first data-containing segment received?  
   c. What is the RTT for this first data-containing segment?  
   d. What is the RTT value the second data-carrying TCP segment and its ACK?  
   Answer :
   ![image](https://github.com/dagdo03/tcp-udp/assets/95538168/1f86057a-4e9b-42ce-907a-dad28bad44d9)  
   a. 0.24047  
   b. 0.052671  
   c. 0.028624  
   d. 0.028628  

7. What is the length (header plus payload) of each of the first four data-carrying TCP segments?  
   Answer : 4 * (Payload + Header) = 4 * (1448 + 32) = 4 * 1480 = 5920 byte  

8. a. What is the minimum amount of available buffer space advertised to the client by gaia.cs.umass.edu among these first four data-carrying TCP segments?  
   b. Does the lack of receiver buffer space ever throttle the sender for these first four datacarrying segments?  
   Answer :
   a. 13712  
   b. Receiver buffer spacer never throttle sender because window size value is always greater than length  

9. a. Are there any retransmitted segments in the trace file?  
   b. What did you check for (in the trace) in order to answer this question?  
   Answer :  
   a. Yes, there are  
   b. Retransmitted segments can be detected via sequence number. When resending, there are packets where the sequence number of the next packet is not greater than the sequence number of the previous packet.  

10. a. How much data does the receiver typically acknowledge in an ACK among the first ten data-carrying segments sent from the client to gaia.cs.umass.edu?  
    b. Can you identify cases where the receiver is ACKing every other received segment among these first ten data-carrying segments?
    Answer :
    a. 1448 byte  
    b. If the data is doubled, the acking segment for each segment is received, for example in the second segment the data is doubled from 1448 to 2896 bytes  

#UDP  

1. a. What is the packet number of this segment in the trace file?  
   b. What type of application-layer payload or protocol message is being carried in this UDP segment?  
   c. How many fields there are in the UDP header?  
   Answer :
   ![image](https://github.com/dagdo03/tcp-udp/assets/95538168/e0787f36-aa71-49a4-833f-a45182e05fdc)
   a. Packet number : 5  
   b. SSDP (Simple Service Discovery Protocol)  
   c. 4 field, source port, destination port, length, dan checksum  

2. What is the length (in bytes) of each of the UDP header fields?  
   Answer : Each field is 2 bytes in size so the total is 8 bytes because the header has 4 fields  

3. The value in the Length field is the length of what?  
   Answer : The length field is the total length of the UDP segment which includes the header and payload4. In the image above, the length value of 283 bytes is obtained from the header (8 bytes) plus payload (275 bytes)  

4. What is the maximum number of bytes that can be included in a UDP payload?  
   Answer : UDP has a 16-bit field which has a maximum length of 65,535 bytes, but because there is a header (8 bytes) the maximum length is 65,527 bytes  
   
6. What is the largest possible source port number?  
   Answer : 65535, because the port is represented with 16 bits so the possible numbers are between 0 to 65535 (2^16 - 1)  

7. What is the protocol number for UDP?  
   Answer : 17  

8. a. What is the packet number of the first of these two UDP segments in the trace file?  
   b. What is the packet number of the second of these two UDP segments in the trace file?  
   c. Describe the relationship between the port numbers in the two packets  
   Answer :  
   a. 15  
   b. 17  
   c. The source port for packet 15 is the destination port for packet 17 and it can be applied in the opposite.  



   


   
