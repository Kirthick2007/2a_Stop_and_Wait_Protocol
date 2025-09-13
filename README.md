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
## CLIENT PROGRAM:
```py
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

##SERVER PROGRAM:
```py
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Received".encode())
```
## OUTPUT
<img width="863" height="298" alt="image" src="https://github.com/user-attachments/assets/e1d92922-3968-41ea-b41b-efc580323d57" />
<img width="853" height="188" alt="image" src="https://github.com/user-attachments/assets/17970530-3bce-4f6e-8d96-bb85a8aa1141" />


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
