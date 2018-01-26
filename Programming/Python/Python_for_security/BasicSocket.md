## Server side

    >>> import socket
    >>> sock = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
    >>> HOST = ''
    >>> PORT = 50000
    >>> sock.bind((HOST, PORT))
    >>> sock.listen(1)
    >>> conn, addr = sock.accept()
    >>> print(conn, addr)
    (<socket._socketobject object at 0x1083a2bb0>, ('127.0.0.1', 64337))
    >>> conn.recv(1024)
    'I am your hero!!!'
    >>> sock.close()
    >>> conn.close()

## Client side

    >>> import socket
    >>> s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
    >>> s.connect(('127.0.0.1', 50000))
    >>> s.send("I am your hero!!!")
    17
    >>> s.close()

- import socket
    - the library for all socket operations
    - defines for Python the means of accessing BSD sockets for network communication.
    - Any networking program will have this import.

- sock = socket.socket(socket.AF_INET , socket.SOCK_STREAM)
    - sock - the variable name for the socket object which will be returned
    - socket.socket() - the constructor function for socket objects
    - socket.AF_INET - IPv4
        - socket.AF_INET6 - IPv6
    - socket.SOCK_STREAM - TCP
        - socket.SOCK_DGRAM -UDP

- socket.bind((HOST , PORT))
    - No variable, you can (and typically should) error check with this function, but it doesn’t return any objects, so there’s no need to store anything
    - socket.bind() - associates a socket object with a specific interface and port
    - HOST - the IP/interface with which to associate
    - PORT - the logical address on an interface with which to associate

- socket.listen(listenqueue)
    - socket.listen() - sets the socket object in blocking mode waiting for a client to attempt connnection
    - listenqueue - determines the number of connections to permit while waiting for acceptance.
        - Older systems need a lower number, but modern computers can pretty much listen for as many as necessary

- conn, addr = socket.accept()
    - conn - a new socket object, this one is for a specific client connection, whereas the “sock” object was for our server to listen
    -  addr - address information about the client (IP, port, etc)
    - socket.accept() - this is where a connection is fully negotiated, and data can begin travelling back and forth

- socket.send(string)
    - socket.send() - sends a buffer to the specified target and returns the number of bytes sent.
        - This return value is a useful error check, make sure you send as much as you think you do.
    - string - this can be a hard-coded string, or it can be a variable you define and populate elsewhere

- socket.recv(bufsize[, flags])
    - socket.recv() - receives data from a connection.
    - bufsize - the amount of data to accept
    - flags - It defaults to 0, and that’s the only value most people will ever use.

- socket.close()
    - this terminates the connection, and frees up the memory.
    - The interpreter will do this automatically, but good habits are good habits.