# ** C Web Server - "Saranai Server".**
# Telematics -  
## UNIVERSIDAD EAFIT - Medellin, Antiquia, 2023-I.

# **Project Description:**
This project explores the application layer of the TCP/IP architecture. It will focus on
studying the HTTP protocol from a networking programming perspective and will involve the
development and implementation of a web server.

**Team Members:**

- Daniel González Bernal
- Sara Rodríguez Velásquez
- Jorge Alfredo Villarreal

******

# **Index:**

1. [Introduction](#Introduction)
2. [Development](#Development)
3. [Conclusions](#conclusions)
4. [References](#references)

******

# **Introduction**

This project explores the application layer of the TCP/IP architecture. Specifically, it will focus on studying
the HTTP protocol from a networking programming perspective. The main objective is to develop and implement a web server.

In general terms, the primary function of a web server is to deliver web resources (such as HTML pages, images, style files, etc.)
to a client that requests them (e.g., a web browser). For this purpose, both the client and the server communicate through the HTTP protocol.

The ultimate goal of this laboratory work is to develop and implement a web server named Telematics Web Server (TWS) that supports the HTTP/1.1 version. 


******

# **Development**

## Code Description:

This code is a web server write in C that accepts HTTP requests. It receives HTTP requests from clients and returns an HTTP response based on the request. The server is a console program that runs in an infinite loop and waits for new client connections. The socket protocol is used to establish connections between the client and the server. The pthread.h library is used to create a thread for each client connection. The server is capable of handling multiple connections simultaneously.

The HTTP request is parsed using the parse_request_line function, which analyzes the HTTP request line to determine the method, path, and host. The server supports the GET, POST, and HEAD methods. If a request with a different method or a poorly written request is received, it returns an HTTP 400 Bad Request response code.

The server has a logger that is saved in a text file in txt format, which is specified as a command-line argument. The logger function records each HTTP request, post, and response in the log file with the corresponding timestamp.


## **Glossary and Terminology**

This section will describe the terminology used for the project.

### Three way Handshake

It is a three-step process carried out at the beginning of a TCP connection to ensure that both devices are synchronized and ready for data transmission.

- C ->syn=1                    S
- C <-ack=1; syn=1             S
- C ->ack=1                    S

### Connection State

Connection: Keep alive; Prioritizes not having short-lived connections, enabling multiple requests to be made together.

The web server and the client negotiate whether to keep the connection open by using the "Connection" header in HTTP requests and the corresponding responses. 

### - bind
The bind function in C network programming is used to associate an IP address and a port number with a socket. It's a system call that assigns a local address to a socket identified by its file descriptor.

### - listen
The listen function in C network programming is used to inform the operating system that the socket is ready to accept incoming connections. This system call specifies the maximum number of pending connections that can be queued for the socket.

### - accept
The accept function in C network programming is used to accept an incoming connection on a socket previously configured to listen. This system call returns a new file descriptor representing the accepted connection.

### - connect()
The connect() function in C network programming is used to establish a connection with another host over a network. This system call is used on the client side to connect a client socket to a server socket.

### - recv()
The recv() function in C network programming is used to receive data over a socket. This system call receives the data sent by the other end of the connection and stores it in a specified buffer.

### - sockaddr_in
sockaddr_in is a data structure in C network programming used to represent an IP address and a port number in the IPv4 protocol. This structure is used with other socket functions to assign addresses and ports to sockets.

### - strstr
The strstr function in C programming is used to find the first occurrence of a substring in a string. This function returns a pointer to the first character of the found substring or NULL if the substring is not found in the string.

### - memcpy
The memcpy function in C programming is used to copy a block of memory from one location to another. This function takes two pointers as arguments: the first pointer is the destination where the block of memory will be copied, and the second pointer is the source of the block of memory to be copied.


******

# **Conclusions**
At the beginning of this project, the question of whether to implement it in Python or C was raised. A small prototype was even developed in Python, and both programming languages were compared.

As a challenge, the decision was made to implement it in C. Despite the significantly increased level of difficulty with this choice, the speed and more efficient resource management provided by C in comparison to the other language became evident. This unexpected experience was very satisfying.

The complexity of something that is taken for granted by most of the world, the Internet, was also greatly appreciated. The intricate nature of each request and response was highlighted, fostering a greater understanding and admiration for the robust systems that support our online actions day by day.

We can only theorize about the robustness of systems like banking platforms, streaming services, or payment gateways, and how delicate the operations performed by their supporting servers are.

In the development of this project, a myriad of knowledge was gained, contributing positively to the comprehension of telecommunications systems.


# **References**

- HTTP Semantics. Disponible en: https://www.rfc-editor.org/rfc/rfc9110.html

- Hypertext Transfer Protocol -- HTTP/1.1 . Dispoible en: https://datatracker.ietf.org/doc/rfc2616/

- Beej's Guide to Network Programming | System Calls or Bust. Disponible en: https://beej.us/guide/bgnet/html/split/system-calls-or-bust.html

- Ejemplo de un servidor sencillo en C. Comunidad de programadores. Disponible en: https://www.lawebdelprogramador.com/foros/C-Visual-C/1565635-Servidor-web-en-C.html 

- Ejemplo de proyecto de servidor en C. Blooming Institute of Technology. Repositorio en Github. Disponible en: https://github.com/bloominstituteoftechnology/C-Web-Server 

- Información impartida por el docente en clase. Curso de telemática, Universidad EAFIT 2023-1. 

- Formato de la página 404. Por Piotr Galor. Codepen. Disponible en: https://codepen.io/pgalor/pen/OeRWJQ 

- Formato de páginas web de Elegant Themes. Disponibles en: https://www.elegantthemes.com/ 
