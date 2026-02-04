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
## Client
```
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
while True:
  i=input("Enter a data: ")
  c.send(i.encode())
  ack=c.recv(1024).decode()
  if ack:
    print(ack)
    continue
  else:
    c.close()
    break
```

## Server
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
 print(s.recv(1024).decode())
 s.send("Acknowledgement Recived".encode())
```
## OUTPUT
## Client
<img width="661" height="247" alt="image" src="https://github.com/user-attachments/assets/39d05ec6-6de4-4bb1-9be1-1a7e2619bfcb" />

## Server
<img width="601" height="116" alt="image" src="https://github.com/user-attachments/assets/02ad06b2-3b33-44aa-a0dc-07abb4a9ef05" />

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
