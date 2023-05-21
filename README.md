# EX-6 IMPLEMENTATION OF PING COMMAND

# DATE :13.04.2023

# AIM :
### To write the python program for simulating ping command.
# ALGORITHM :
### Step 1: start the program. 
### Step 2: Include necessary package in java. 
### Step 3: To create a process object p to implement the ping command. 
### Step 4: declare one Buffered Reader stream class object. 
### Step 5: Get the details of the server 
### 5:1: length of the IP address. 
### 5:2: time required to get the details. 
### 5:3: send packets, receive packets and lost packets. 
### 5.4: minimum, maximum and average times. 
### Step 6: print the results. Step 7: Stop the program.
# CLIENT PROGRAM :
```PY
## Developed : Kavinraja D
## Reg no : 212222240047
import socket
from pythonping import ping
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
while True:
    hostname=c.recv(1024).decode()
    try:
        c.send(str(ping(hostname, verbose=False)).encode())
    except KeyError:
        c.send("Not Found".encode())
```
# SERVER PROGRAM :
```PY
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    ip=input("Enter the website you want to ping ")
    s.send(ip.encode())
    print(s.recv(1024).decode())

```
# OUTPUT :
![output](./o1.png)
![output](./o2.png)
# RESULT:
### Thus, the python program for simulating ping command was successfully executed.



