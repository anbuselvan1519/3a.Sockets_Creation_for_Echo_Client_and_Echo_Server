# 3a.CREATION FOR ECHO CLIENT AND ECHO SERVER USING TCP SOCKETS.

### Developed by: Anbuselvan.S
### Register no: 212223240008

## AIM:
To write a python program for creating Echo Client and Echo Server using TCP
Sockets Links.

## ALGORITHM:
1. Import the necessary modules in python
2. Create a socket connection to using the socket module.
3. Send message to the client and receive the message from the client using the Socket module in
 server .
4. Send and receive the message using the send function in socket.
   
## PROGRAM:

### Server:
```py
import socket

# Create a socket object
server_socket = socket.socket(socket.AF_INET, socket.SOCK_STREAM)

# Get local machine name (can also use 'localhost' or an IP address)
host = socket.gethostname()
port = 9999

# Bind to the port
server_socket.bind((host, port))

# Start listening for incoming connections (up to 5)
server_socket.listen(5)
print(f"Server is listening on {host}:{port}")

while True:
    # Establish a connection with the client
    client_socket, addr = server_socket.accept()
    print(f"Got a connection from {addr}")
    
    # Send a message to the client
    message = 'Hello, Client! This is the Server.\n'
    client_socket.send(message.encode('ascii'))

    # Receive the message from the client
    client_message = client_socket.recv(1024).decode('ascii')
    print(f"Client says: {client_message}")

    # Close the connection with the client
    client_socket.close()

```

### Client:
```py
import socket

# Create a socket object
client_socket = socket.socket(socket.AF_INET, socket.SOCK_STREAM)

# Get the local machine name
host = socket.gethostname()
port = 9999

# Connection to hostname on the port.
client_socket.connect((host, port))

# Receive the message from the server
server_message = client_socket.recv(1024).decode('ascii')
print(f"Server says: {server_message}")

# Send a message back to the server
client_message = "Hello, Server! This is the Client."
client_socket.send(client_message.encode('ascii'))

# Close the connection
client_socket.close()

```

## OUPUT:

### Server:
![image](https://github.com/user-attachments/assets/d674ab54-a937-485f-9656-ac8d6f2f95e8)

### client:
![image](https://github.com/user-attachments/assets/4bb07963-4463-4b8a-87cd-7772dee8b9b5)

## RESULT
Thus, the python program for creating Echo Client and Echo Server using TCP Sockets Links 
was successfully created and executed.
