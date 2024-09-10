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
Client
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
Server
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
print(s.recv(1024).decode())
s.send("Acknowledgement Recived".encode())
```
## OUTPUT
<img width="641" alt="image" src="https://github.com/user-attachments/assets/343d7c3d-9b6e-44c5-b2d8-902ee1331a61">
<img width="644" alt="image" src="https://github.com/user-attachments/assets/67baddbc-3d68-400a-9d3b-c46a31b08957">


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
