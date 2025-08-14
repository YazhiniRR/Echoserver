## Date: 14-08-2025
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
server_socket = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
server_socket.bind(('localhost', 12345))
server_socket.listen(1)

print("Server is listening on port 12345...")
conn, addr = server_socket.accept()
print(f"Connected by {addr}")

while True:
    data = conn.recv(1024)
    if not data:  # If no data, client closed connection
        break
    print(f"Received from client: {data.decode()}")
    conn.sendall(data)  # Echo back the same data

conn.close()

```
Client.py
```
import socket
client_socket = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
client_socket.connect(('localhost', 12345))

while True:
    msg = input("Enter message (type 'exit' to quit): ")
    if msg.lower() == 'exit':
        break
    client_socket.sendall(msg.encode())
    data = client_socket.recv(1024)
    print(f"Echo from server: {data.decode()}")

client_socket.close()
```

## OUTPUT:

<img width="857" height="224" alt="Screenshot 2025-08-14 090737" src="https://github.com/user-attachments/assets/184d1474-5554-499a-9494-0a376238018c" />
<img width="863" height="403" alt="Screenshot 2025-08-14 090533" src="https://github.com/user-attachments/assets/c9b26133-3433-4b7c-a8f7-d4ef6fa0cd38" />

## RESULT:
The program is executed successfully
