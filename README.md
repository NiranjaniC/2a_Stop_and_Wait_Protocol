# 2a_Stop_and_Wait_Protocol
## DATE:27/08/2024
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
![Screenshot 2024-08-20 094119](https://github.com/user-attachments/assets/857c12cf-c63a-4af5-a11c-26f65d0feb6b)
![Screenshot 2024-08-20 094206](https://github.com/user-attachments/assets/3206401b-0000-4408-b1f8-5cca4754066c)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
