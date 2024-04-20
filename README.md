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
## client
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
## server
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
   print(s.recv(1024).decode())
   s.send("Acknowledgement Recived".encode())
```
## OUTPUT
## client

![Screenshot 2024-04-20 105645](https://github.com/Danica-christa/2a_Stop_and_Wait_Protocol/assets/151514009/96fd3098-5715-4900-b5a9-86e824d0ec5b)
## server

![Screenshot 2024-04-20 105659](https://github.com/Danica-christa/2a_Stop_and_Wait_Protocol/assets/151514009/1a289b3a-5016-47fc-812f-905136fc5548)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
