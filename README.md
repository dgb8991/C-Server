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
3. [Conclusiones](#conclusiones)
4. [Referencias](#referencias)

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


### **Details**

En el proyecto se usan principalmente 3 herramientas:

|Compilador|Build|Debugger|
|---|---|---|
|gcc|meson|gdb|

#### Proceso de verificación e instalación:

Debian, Ubuntu y derivativos:

Para instalar gcc y gdb

``` bash
sudo apt install build-essential gdb
sudo apt install meson ninja-build
```
Para instalar meson y ninja
```

``` bash
sudo apt install meson ninja-build
```

Para iniciar un projecto en el directorio actual

``` bash
meson init --name server --build
```

Para compilar y probar

``` bash
meson compile -C builddir
meson test -C builddir
```

Debuggear

``` bash
gdb build/server
```

Algunos comandos útiles de GDB incluyen break, run, next, step, print, backtrace, finish, continue, watch, entre otros.

Comando para iniciar la aplicación

``` bash
./build/server
./build/server PORT LOGFILE DOCROOT
```


## **Glosario y Terminología**

En esta sección se describirá la terminología util para la realización del proyecto.

### Three way Handshake

Es un proceso de tres pasos que se realiza al comienzo de una conexión TCP, para asegurar que ambos dispositivos estén sincronizados y listos para la transmisión de datos.

- C ->syn=1                    S
- C <-ack=1; syn=1             S
- C ->ack=1                    S

### Estado de la conexión

Connection: Keep alive ; Se prioriza que no sean conecciones shortlived, que se puedan hacer varios requests de manera conjunta.

El servidor web y el cliente negocian si desean mantener la conexión abierta mediante el uso de la cabecera "Connection" en las solicitudes HTTP y las respuestas correspondientes. 

### - bind
La función bind en programación de redes en C se utiliza para asociar una dirección IP y un número de puerto a un socket. Es una llamada al sistema que asigna una dirección local a un socket identificado por su descriptor de archivo.

### - listen
La función listen en programación de redes en C se utiliza para indicar al sistema operativo que el socket está listo para aceptar conexiones entrantes. Esta llamada al sistema especifica el número máximo de conexiones pendientes que se pueden encolar para el socket.

### - accept
La función accept en programación de redes en C se utiliza para aceptar una conexión entrante en un socket previamente configurado para escuchar. Esta llamada al sistema devuelve un nuevo descriptor de archivo que representa la conexión aceptada.

### - connect()
La función connect() en programación de redes en C se utiliza para establecer una conexión con otro host a través de una red. Esta llamada al sistema se utiliza en el lado del cliente para conectar un socket de cliente a un socket de servidor.

### - recv()
La función recv() en programación de redes en C se utiliza para recibir datos a través de un socket. Esta llamada al sistema recibe los datos enviados por el otro extremo de la conexión y los almacena en un búfer especificado.

### - sockaddr_in
sockaddr_in es una estructura de datos en programación de redes en C que se utiliza para representar una dirección IP y un número de puerto en el protocolo IPv4. Esta estructura se utiliza con otras funciones de socket para asignar direcciones y puertos a los sockets.

### - strstr
La función strstr en programación de C se utiliza para encontrar la primera aparición de una subcadena en una cadena. Esta función devuelve un puntero al primer carácter de la subcadena encontrada o NULL si la subcadena no se encuentra en la cadena.

### - memcpy
La función memcpy en programación de C se utiliza para copiar un bloque de memoria de un lugar a otro. Esta función toma dos punteros como argumentos, el primer puntero es el destino donde se copiará el bloque de memoria y el segundo puntero es el origen del bloque de memoria que se copiará.


******

# **Conclusiones**
 Al inicio de este proyecto se planteó la pregunta si hacerlo en python o en C, e inclusive se hizo un pequeño prototipo en Python y se compararon ambos lenguajes de programación.

Como modo de reto se aceptó realizarlo en C, y aunque el nivel de dificultad creció en gran medida con esta elección se pudo evidenciar la velocidad y manejo de recursos mas eficiente que proporciona C respecto al otro lenguaje. Esto fue un aprendizje inesperado y muy satisfactorio.

Se pudo apreciar en gran medida tambien la complejidad de algo que se da por sentado para la gran mayoria del mundo, Internet. Se pudo evidenciar lo compleja que es cada petición y respuesta, y se adquirió un mayor aprecio y admiración por los robustos sistemas que soportan nuestras acciones en la red día a día.

Solo podemos teorizar sobre lo robustos que son sistemas como las plataformas bancarias, plataformas de streaming o servicios de pago, y que tan delicadas son las operaciones que realizan los servidores que las soportan. 

Se ha aprendido en el desarrollo de este proyecto una gran infinididad de conocimientos que aportan positivamente al entendimiento de los sistemas de telecomunicaciones.


# **Referencias**

Se leyeron varios articulos y se visitaron varios archivos como referentes para el proyecto, los cuales se listan a continuación.

### Webgrafia y Bibliografia:

Video Tutorial "I made a web server in C like a true sigma". Imran Rahman. Disponible en youtube: https://www.youtube.com/watch?v=cEH_ipqHbUw&ab_channel=ImranRahman 

#### Referentes:
- HTTP Semantics. Disponible en: https://www.rfc-editor.org/rfc/rfc9110.html

- Hypertext Transfer Protocol -- HTTP/1.1 . Dispoible en: https://datatracker.ietf.org/doc/rfc2616/

- Beej's Guide to Network Programming | System Calls or Bust. Disponible en: https://beej.us/guide/bgnet/html/split/system-calls-or-bust.html

- Ejemplo de un servidor sencillo en C. Comunidad de programadores. Disponible en: https://www.lawebdelprogramador.com/foros/C-Visual-C/1565635-Servidor-web-en-C.html 

- Ejemplo de proyecto de servidor en C. Blooming Institute of Technology. Repositorio en Github. Disponible en: https://github.com/bloominstituteoftechnology/C-Web-Server 

- Información impartida por el docente en clase. Curso de telemática, Universidad EAFIT 2023-1. 


#### Fuentes de recursos web:

- Formato de la página 404. Por Piotr Galor. Codepen. Disponible en: https://codepen.io/pgalor/pen/OeRWJQ 

- Formato de páginas web de Elegant Themes. Disponibles en: https://www.elegantthemes.com/ 
