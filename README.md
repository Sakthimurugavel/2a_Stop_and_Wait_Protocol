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
```
Client Code
```
```
import socket
s=socket.socket()
s.bind(('localhost', 8000))
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
```
Server Code
```
```
import socket
s = socket.socket()
s.connect(('localhost', 8000))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Recived".encode())
```
## OUTPUT
```
Client Output
```
![out 1 cn](https://github.com/Sakthimurugavel/2a_Stop_and_Wait_Protocol/assets/118707246/01d6ecc1-9fd0-4319-877d-6849836bd42c)


```
Server Output
```
![out 2 cn](https://github.com/Sakthimurugavel/2a_Stop_and_Wait_Protocol/assets/118707246/69655dae-b298-49af-ade8-674e33978feb)


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
