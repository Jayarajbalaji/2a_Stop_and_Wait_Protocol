# 2a_Stop_and_Wait_Protocol
## Name JAYARAJ B
## Reg.NO.24013576
## AIM 
To write a python program to perform stop and wait protocol
## ALGORITHM
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM:
### Client program:
~~~
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
~~~
### Server program:
~~~
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
 print(s.recv(1024).decode())
 s.send("Acknowledgement Recived".encode())

~~~
## OUTPUT:

### Client:
![image](https://github.com/user-attachments/assets/1393c6b0-7a3d-4dfc-ae20-64336963c422)


### Server:
![image](https://github.com/user-attachments/assets/7d20451c-d724-4205-8198-5c7c94efae2e)


## RESULT:
Thus, python program to perform stop and wait protocol was successfully executed.
