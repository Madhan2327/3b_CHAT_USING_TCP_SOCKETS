# 3b.CREATION FOR CHAT USING TCP SOCKETS
## AIM
To write a python program for creating Chat using TCP Sockets Links.
## ALGORITHM:
1. Import the necessary modules in python
2. Create a socket connection to using the socket module.
3. Send message to the client and receive the message from the client using the Socket module in
 server
4. Send and receive the message using the send function in socket.
## PROGRAM
Developed by : MADHAN C

Reg no : 212224240081

### Client
```
import socket
s = socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c, addr = s.accept()
address = {"6A:08:AA:C2":"192.168.1.100","8A:BC:E3:FA":"192.168.1.99"}
while True:
    ip = c.recv(1024).decode()
    try:
        c.send(address[ip].encode())
    except KeyError:
        c.send("Not Found".encode())
```

### Server
```
import socket
s  =socket.socket()
s.connect(('localhost',8000))
while True:
    ip = input("Enter MAC Address : ")
    s.send(ip.encode())
    print("Logical Adress : ",s.recv(1024).decode())
```
## OUPUT
Refer to the following screenshot to view the output of the program.

![OutputScreenshot](https://github.com/user-attachments/assets/28cc7f40-23e0-49ea-9a75-d779f02bf49a)

## RESULT
Thus, the python program for creating Chat using TCP Sockets Links was successfully 
created and executed.
