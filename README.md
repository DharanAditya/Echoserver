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
SERVER:
# echo-server.py


import socket


HOST = "127.0.0.1"  
PORT = 65432 


with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.bind((HOST, PORT))
    s.listen()
    conn, addr = s.accept()
    with conn:
        print(f"Connected by {addr}")
        while True:
            data = conn.recv(1024)
            if not data:
                break
            conn.sendall(data)



CLIENT:
import socket


HOST = "127.0.0.1"  # The server's hostname or IP address
PORT = 65432  # The port used by the server


with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.connect((HOST, PORT))
    s.sendall(b"Dharan Aditya S,212223040035")
    data = s.recv(1024)


print(f"Received {data!r}")


## OUTPUT:
SERVER:


![Screenshot (12)](https://github.com/user-attachments/assets/815c5c73-4dbd-46a8-a50b-41dc4abe9855)


CLIENT:

![Screenshot (11)](https://github.com/user-attachments/assets/47c851a4-3cea-400f-b4b7-34d81b540355)



## RESULT:
The program is executed successfully
