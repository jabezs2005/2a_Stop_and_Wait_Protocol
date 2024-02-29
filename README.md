### 2a_Stop_and_Wait_Protocol
### AIM:
To write a python program to perform stop and wait protocol
### ALGORITHM:
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
### PROGRAM:
## Client Output:

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
## Server Output:
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Received".encode())

```
### OUTPUT:
## Client Output:
![Client Output](https://github.com/jabezs2005/2a_Stop_and_Wait_Protocol/assets/147473463/e44ec166-5c59-440f-9e6b-9d167c995409)

## Server Output:
![Server Ouput](https://github.com/jabezs2005/2a_Stop_and_Wait_Protocol/assets/147473463/a18b1773-9c68-4d52-a928-3914605c9477)

![Client and Server Output](https://github.com/jabezs2005/2a_Stop_and_Wait_Protocol/assets/147473463/670379ef-40db-47d7-b6b2-16772c214863)

### RESULT:
Thus, python program to perform stop and wait protocol was successfully executed.
