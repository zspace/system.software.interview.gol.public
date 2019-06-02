# Conway's Game of Life
simple and straighforward C implementation

See README.md for instructions.

Step 2

Using code from step one implement client-server version of Game of Life via TCP/IP stream sockets
as explained below. Particular port number and protocol is up to you.

You can use any platform (Mac OS, Linux etc).
In our implementation code runs on Windows command line and behaves as desribed below.

1. There is single application that is linked to two files gol-server and gol-client.
2. Upon startup application examines it's name like busybox or toybox does and behaves accordingly.

![start server](https://raw.githubusercontent.com/leo-zspace/cgol.public/master/cs/1.gol-server.png)
![start client](https://raw.githubusercontent.com/leo-zspace/cgol.public/master/cs/2.gol-client.png)

3. Server listens on port 6666 and client connects to it. Single client server pair.
4. Client is capable of sending commands described above to the server. 
   Server replies with the new state of the board for each new command.
   Here are examples of client server comminication:

![client send "*.*" (dot) command](https://raw.githubusercontent.com/leo-zspace/cgol.public/master/cs/3.gol-client-send-request-dot-command.png)
![random init "*R*"](https://raw.githubusercontent.com/leo-zspace/cgol.public/master/cs/4.gol-client-send-random-init-R-command.png)
![single step "*S*"](https://raw.githubusercontent.com/leo-zspace/cgol.public/master/cs/5.gol-client-send-step-S-command.png)
![flip cell *3C*](https://raw.githubusercontent.com/leo-zspace/cgol.public/master/cs/6.gol-client-send-flip-3C-command.png)
![flip cells *3D* and *3E*](https://raw.githubusercontent.com/leo-zspace/cgol.public/master/cs/7.gol-client-send-flip-3D-3E-commands.png)
![make server go "*G*"](https://raw.githubusercontent.com/leo-zspace/cgol.public/master/cs/8.gol-client-send-go-G-command.png)

After command G (go) server starts running and periodically (once in three seconds in our implementation) send 
board state and generation number (e.g. 2146> on the screenshot above) to the client.

Client displays generation number and board state but is capable of still accepting user controls for flipping cells, 
re-initializing the board, stopping the running server with "*T*" (stop) command and starting it again.

*Q* quits the client leaving server running.

*K* kills the server and quits the client.

