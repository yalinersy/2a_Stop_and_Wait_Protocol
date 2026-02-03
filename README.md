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

## Server
<img width="722" height="100" alt="image" src="https://github.com/user-attachments/assets/7710e91b-a2ae-4e9d-ab9f-e828b1bdb5f9" />


## Client
<img width="604" height="84" alt="image" src="https://github.com/user-attachments/assets/e38d7509-f597-4d45-a6b5-ce1078057934" />



## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
