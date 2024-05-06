# 2a_Stop_and_Wait_Protocol
# NAME: DEVA DHARSHINI I

# REGISTER NO: 212223240026
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
CLIENT
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
SERVER
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
 print(s.recv(1024).decode())
 s.send("Acknowledgement Recived".encode())
```
## OUTPUT
CLIENT
![Screenshot 2024-05-06 160536](https://github.com/deesk13/2a_Stop_and_Wait_Protocol/assets/150927063/d81aaa33-a8b5-48c0-b2ea-4d963caea3a9)
SERVER
![Screenshot 2024-05-06 160553](https://github.com/deesk13/2a_Stop_and_Wait_Protocol/assets/150927063/31c35a01-5886-44e1-8462-d89f977582a9)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
