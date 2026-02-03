# 2a_Stop_and_Wait_Protocol
## AIM 
To write a python program to perform stop and wait protocol
## ALGORITHM
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM

## Server
```
import socket
import datetime

s = socket.socket()
s.bind(('localhost', 8000))
s.listen(5)

print("Server waiting for connection...")

while True:
    c, addr = s.accept()
    print("Connected from:", addr)

    now = datetime.datetime.now()
    c.send(str(now).encode())

    msg = c.recv(1024).decode()
    print("Client Message:", msg)

    c.close()

```

## Client
```
import socket

s = socket.socket()
s.connect(('localhost', 8000))

print(s.getsockname())
print(s.recv(1024).decode())

s.send("Acknowledgement received from the server".encode())
s.close()

```
## OUTPUT

## Client
<img width="693" height="179" alt="image" src="https://github.com/user-attachments/assets/33d2278d-381e-45f4-a2a8-e1282818f9e9" />

## Server
<img width="592" height="195" alt="image" src="https://github.com/user-attachments/assets/5cfd3962-b0dc-43fd-af86-aa853485348d" />


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
