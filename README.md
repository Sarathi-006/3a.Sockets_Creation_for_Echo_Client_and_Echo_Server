# 3a.CREATION FOR ECHO CLIENT AND ECHO SERVER USING TCP SOCKETS
# AIM
To write a python program for creating Echo Client and Echo Server using TCP
Sockets Links.
## ALGORITHM:
1. Import the necessary modules in python
2. Create a socket connection to using the socket module.
3. Send message to the client and receive the message from the client using the Socket module in
 server .
4. Send and receive the message using the send function in socket.
## PROGRAM
##client
```
import socket

HOST = '127.0.0.1'  
PORT = 65432        

with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.connect((HOST, PORT))
    while True:
        message = input("Enter message to send to server: ")
        s.sendall(message.encode())
        data = s.recv(1024)
        print('Received', repr(data.decode()))

```
##server
```
import socket

HOST = '127.0.0.1'  
PORT = 65432       

with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.bind((HOST, PORT))
    s.listen()
    conn, addr = s.accept()
    with conn:
        print('Connected by', addr)
        while True:
            data = conn.recv(1024)
            if not data:
                break
            conn.sendall(data)

```
## OUPUT
##client
![310513915-4f0dca11-0077-463c-80d3-eaf1922c1ac4](https://github.com/Sarathi-006/3a.Sockets_Creation_for_Echo_Client_and_Echo_Server/assets/149349756/056d34c7-8fad-4bab-96e1-9af216659d45)

##server
![310513763-21e8cf8f-c448-445a-a520-02462699f482](https://github.com/Sarathi-006/3a.Sockets_Creation_for_Echo_Client_and_Echo_Server/assets/149349756/2722ce2d-a691-4dba-85be-db9ef014ec17)

## RESULT
Thus, the python program for creating Echo Client and Echo Server using TCP Sockets Links 
was successfully created and executed.
