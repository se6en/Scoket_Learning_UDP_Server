# Scoket_Learning_UDP_Server
 # 6/9/2021
Create UDP socket communication server.

## Sample project files
---
### Socket_Learning_UDP_Server(.h and .cpp)
---
We need take following steps to create socket server for UDP communication:(Step.1 to Step.4 are the same as TCP communication)
1. Start up socket with function WSAStartup() to find the usable Windowsock DLL. We use Winsock 2.2 dll in this sample as the sample in MSDN.
2. Create socket server with the socket constructor. Parameters SOCK_DGRAM and IPPROTO_UDP were used for UDP protocol.(TCP use SOCK_STREAM and IPPROTO_TCP).
3. Transfer the server ip adress from string to in_addr.
4. Bind the socket server created in Step.2 with the address. AF_INET was the family used for TCP protocol. Port number also needed to be specific in this step.
5. Use recvfrom function to receive data from client. The parameter clientaddr will filled with the client address so that server will know where the message come from. (TCP will require listen and accept before receive information form client)
6. WSACleanup was used to clean all the information and finished the use of Winsock dll.