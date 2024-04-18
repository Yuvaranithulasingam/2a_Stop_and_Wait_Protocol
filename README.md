# EX.NO:2a     Stop_and_Wait_Protocol

## AIM 
To write a python program to perform stop and wait protocol
## ALGORITHM
1. Start the program.</br>
2. Get the frame size from the user</br>
3. To create the frame based on the user request.</br>
4. To send frames to server from the client side.</br>
5. If your frames reach the server it will send ACK signal to client</br>
6. Stop the Program</br>
## PROGRAM
### Client:
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
### Server:
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
 print(s.recv(1024).decode())
 s.send("Acknowledgement Recived".encode())
```
## OUTPUT
### Client:
![image](https://github.com/Yuvaranithulasingam/2a_Stop_and_Wait_Protocol/assets/121418522/eb561cf4-e279-4c99-bb10-f608e701ec02)
### Server:
![image](https://github.com/Yuvaranithulasingam/2a_Stop_and_Wait_Protocol/assets/121418522/3cb1211c-6827-4b7c-914f-292990f416fd)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
