# EXP-3b.CREATION FOR CHAT USING TCP SOCKETS
NAME:RAMYA.P

REGISTER NUMBER: 212223240137

DEPARTMENT: AIML
## AIM
To write a python program for creating Chat using TCP Sockets Links.
## ALGORITHM:
1. Import the necessary modules in python
2. Create a socket connection to using the socket module.
3. Send message to the client and receive the message from the client using the Socket module in
 server
4. Send and receive the message using the send function in socket.
## PROGRAM:
## CLIENT:
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
## SERVER:
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

## OUPUT:
## CLIENT:
![image](https://github.com/23014107/3b_CHAT_USING_TCP_SOCKETS/assets/151625620/ea32fc7b-2e8e-4eac-bbc3-59bbd91d0a76)

## SERVER:
![image](https://github.com/23014107/3b_CHAT_USING_TCP_SOCKETS/assets/151625620/5bfa0df6-5330-4db1-a6e0-bc2b570fb9a8)

## RESULT
Thus, the python program for creating Chat using TCP Sockets Links was successfully 
created and executed.
