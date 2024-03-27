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
### Client:
```
import socket
from datetime import datetime
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
print("Client Address : ",addr)
now = datetime.now()
c.send(now.strftime("%d/%m/%Y %H:%M:%S").encode())
ack=c.recv(1024).decode()
if ack:
 print(ack)
c.close()
```
### Server:
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
print(s.getsockname())
print(s.recv(1024).decode())
s.send("acknowledgement recived from the server".encode())
```
## OUTPUT
### Client:
![image](https://github.com/Yuvaranithulasingam/2a_Stop_and_Wait_Protocol/assets/121418522/6ea53092-5fa2-43d6-9d3a-29c431c5d4fa)

### Server:
![image](https://github.com/Yuvaranithulasingam/2a_Stop_and_Wait_Protocol/assets/121418522/7561f88e-ff8b-4b09-8b32-9924f66e1ecf)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
