## Date: 03-03-2025
# Echoserver
Echo server and client using python socket

# AIM:

To develop a simple webserver to serve html programming pages.

## DESIGN STEPS:

### Step 1:

Design of echo server and client using python socket

### Step 2:

Implementation using Python code

### Step 3:

Testing the server and client 

## PROGRAM:
Server.py
```
import socket

HOST, PORT = '127.0.0.1', 65432

with socket.create_server((HOST, PORT)) as server:
    conn, addr = server.accept()  
    print(f"Connected by {addr}")

    data = conn.recv(1024)  # Receive data
    print(f"Received: {data.decode()}")

    conn.sendall(b'My name is Yash')  

```
Client.py
```
import socket

HOST, PORT = '127.0.0.1', 65432

with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as client:
    client.connect((HOST, PORT)) 
    client.sendall(b'YAZHINI R R ,212224100063')  

    response = client.recv(1024)  
    print(f"Server says: {response.decode()}")

```

## OUTPUT:
![client](https://github.com/user-attachments/assets/02e2ea8a-fc90-4511-b41e-31aaff81b8cf)

![server](https://github.com/user-attachments/assets/790798e9-b019-4bc7-96ab-e12a97a691cb)


## RESULT:
The program is executed successfully
