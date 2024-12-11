---
date: 2024-12-11 
tags: 
    - CA304
hubs: 
    -   "[[2024-12-07_Network-2|network 2]]"
---

# Sockets & Ports & WebSockets

## Context
- The bottom tree layers of the [[2024-12-08_osi-model-vs-tcp-ip-model|TCP/IP model]] 
  - transport, internet, network access
  - handle how to get a packet to you pc
- The *Application* layer handle what to do with that packet

## Problem
- There are a *lot of apps* sending packets to/from you pc
- How does you pc know *which app to give which packet?*
- They use *Sockets* and *Ports*

## Ports
- A port is a *logical endpoint* for communication used in computer networks. 
  - It helps *distinguish* between *different types* of *traffic* on the same network address (IP).
- Rules:
  - An app can open as many ports as it wants
  - Two appes can not open the same port at the same time
  - Some port are reserver, TIP (choose high and you are good to go)

## Socket
- Socket is a *programming abstraction* to interact with network port.
  - is a combination of *IP and Port*
  - is a *point of comunication* between two programs on the network
### Python example
#### Client
```python
import socket

def myclient():
    myscocket = socket.socket(socket.AF_INET,socket.SOCK_STREAM)
    myIPAddress = '127.0.0.1'
    myPort = 8000
    myscocket.connect((myIPAddress, myPort))
    #keep sending data until the word 'bye' is encounterd. 
    #If so, close the socket
    data = input ('>> ')
    while data.lower().strip() != 'bye':
        myscocket.send(data.encode()) 
        message = myscocket.recv(1024).decode()
        print(">> Server: " + str(message))
        data = input('>> ')
    myscocket.close()

if __name__ == '__main__':
    myclient()    
```
#### Server
```python
import socket

def myserver():
    mysocket = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
    myIPaddress = '127.0.0.1'
    myPort = 8000
    mysocket.bind((myIPaddress, myPort))
    mysocket.listen()
    print("I'm listening.....")
    connection, address = mysocket.accept()
    print("Connection from " + str(address))
    while True:
        message = connection.recv(1024).decode()
        if not message:
            break
        print(">> Client: " + str(message))
        data = input('>> ')
        connection.send(data.encode())
    connection.close()

if __name__ == '__main__':
    myserver()
```
## WebSocket

### *Before Websockets*
- Maintaining a constant open connection between client and server was difficult.
- Traditional communication relied on the **pull method**:
  - Server only responds to client requests.
  - Connection closes after each request.
  - Inefficient in bandwidth usage and risks overwhelming the server with excessive requests.
- To send updates from server to client, a **push method** was needed.

### *Websockets*
- **Application Layer Protocol**:
  - Enables full-duplex communication between client and server.
  - Introduced in 2009 and supported by all modern browsers.
- **Protocols**:
  - `ws://<server address>`: Opens a standard WebSocket connection.
  - `wss://<server address>`: Opens a secure WebSocket connection over TLS.


### *Websockets vs. Normal Sockets*
- **Normal Sockets**:
  - more freedom:
    - Specify connection address via the `family` attribute.
    - Choose protocol: TCP or UDP.
  - Not limited to browser environments.

- **Websockets**:
  - Designed for browsers and event-driven communication.
  - Events:
    - **Open**: Triggered when a connection is established.
    - **Message**: Triggered when data is received.
    - **Error**: Triggered when an error occurs.
    - **Close**: Triggered when the connection is closed.

