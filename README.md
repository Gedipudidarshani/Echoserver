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
## Server.py
```
import socket
HOST = '127.0.0.1' 
PORT = 65432 
with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.bind((HOST, PORT))
    s.listen()
    print(f"Server started. Listening on {HOST}:{PORT}...")
    conn, addr = s.accept()
    with conn:
        print(f"Connected by {addr}")
        while True:
            data = conn.recv(1024)
            if not data:
                break
            conn.sendall(data)
```
## Client.py
```
import socket
HOST = '127.0.0.1' 
PORT = 65432
with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.connect((HOST, PORT))
    while True:
        message = input("Enter message (or 'exit' to quit): ")
        if message.lower() == 'exit':
            break
        s.sendall(message.encode())
        data = s.recv(1024)
        print(f"Echo from server: {data.decode()}")
```
## OUTPUT:
<img width="1114" height="233" alt="image" src="https://github.com/user-attachments/assets/e5c74d21-e29b-4ef8-a05b-6dbae2e448fd" />

<img width="1248" height="390" alt="image" src="https://github.com/user-attachments/assets/18b535aa-68f0-4554-bcba-0b30aadada5a" />


## RESULT:
The program is executed successfully
