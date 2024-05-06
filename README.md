# 2a_Stop_and_Wait_Protocol

### NAME: K ESWANTH KUMAR
### DEPT: CSE
## AIM 
To write a python program to perform stop and wait protocol.
## ALGORITHM
1. Start the program.
2. Get the frame size from the user.
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client.
6. Stop the Program.
## PROGRAM:
## Client:
```
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,address=s.accept()
while True:
    i = input("Enter a data:")
    c.send(i.encode())
    ack = c.recv(1024).decode()
    if ack:
        print(ack)
        continue
    else:
        c.close()
        break
```

## Server:
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledment Received".encode())
```

## OUTPUT:
## CLIENT:
![Screenshot (35)](https://github.com/eswanth2005/2a_Stop_and_Wait_Protocol/assets/164656722/f5230ae6-d33a-46d8-afb6-1f15ad027a19)

## SERVER
![Screenshot (36)](https://github.com/eswanth2005/2a_Stop_and_Wait_Protocol/assets/164656722/fb8d05a4-7add-417b-8290-b7c69da80e5b)

## RESULT:
Thus, python program to perform stop and wait protocol was successfully executed.
