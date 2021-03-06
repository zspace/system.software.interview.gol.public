## zSpace Coding Exercise #2:

# Conway's Game of Life (GoL) 
(Client/Server C Implementation)

Prerequisite: Complete [Exercise #1 - Trivial GoL](https://github.com/zspace/system.software.interview.gol.public/blob/master/GOL-trivial.md), which you will build upon for this exercise.

Implement: A client/server version of the Game of Life (GoL) via TCP/IP stream sockets.

* The particular port number and protocol are up to you.

* We provide a Windows [sample implementation of gol-client.exe and gol-server.exe](https://github.com/zspace/system.software.interview.gol.public/tree/master/bin) that demonstrate the desired functionality, and which is described below.  Your implementation should strive to follow this behavior.

* You should produce a single application binary that can be hard-/sym-linked to two names, *gol-server* and *gol-client* on 'nix or *gol-server.exe* and *gol-client.exe* on Windows.

* Upon startup, the application should introspect its filename and behave accordingly as client or server, e.g. like busybox or toybox.

* Starting the server should look like this:

![start server](https://raw.githubusercontent.com/zspace/system.software.interview.gol.public/master/gol-cs/1.gol-server.png)

* The server should listen on some port, and accept client connection to it.  You only need to support the case of a single concurrent server.

* On startup, the client should print out a summary of its commands, and then attempt to connect to the server.  You only need to support the case of a single concurrent client.

![start client](https://raw.githubusercontent.com/zspace/system.software.interview.gol.public/master/gol-cs/2.gol-client.png)

* The client should be capable of sending all the commands summarized above to the server, most of which should be self-evident from the above screenshot.  

* The server should be capable of handling all these commands, and then replying back to the client with the resulting state of the board.  

* When the client receives such board state updates, it should display the board configuration and generation number as shown in the examples below. 
   
* Example of "**.**" command (current state):

![current state "."](https://raw.githubusercontent.com/zspace/system.software.interview.gol.public/master/gol-cs/3.gol-client-send-request-dot-command.png)

* Example of "**R**" command (random init):

![random init "R"](https://raw.githubusercontent.com/zspace/system.software.interview.gol.public/master/gol-cs/4.gol-client-send-random-init-R-command.png)

* Example of "**S**" command (single step):

![single step "S"](https://raw.githubusercontent.com/zspace/system.software.interview.gol.public/master/gol-cs/5.gol-client-send-step-S-command.png)

* Example of "**3C**" command (flip cell '3C'):

![flip cell 3C](https://raw.githubusercontent.com/zspace/system.software.interview.gol.public/master/gol-cs/6.gol-client-send-flip-3C-command.png)

* Example of "**3D**" and "**3E**" commands (flip cell '3D' and '3E'):

![flip cells 3D and 3E](https://raw.githubusercontent.com/zspace/system.software.interview.gol.public/master/gol-cs/7.gol-client-send-flip-3D-3E-commands.png)

* The "**G**" (go) command should cause the server begin computing successive generations automatically until explicitly stopped.

* The "**S**" (stop) command should cause the server to halt the periodic computation state engaged via "**G**".  This is the default state at server startup.

* While the server is in the "**G**" state, it should periodically (every 3 seconds in our implementation) send the board state to the client. 

* While the server is in the "**G**" state, the client should display any incoming board state updates. (Note the gap between generation '>2' and '>2146' in the example below.)

* While the server is in the "**G**" state, client and server should still be capable of accepting and dispatching all valid user commands.

* Example of "**G**" command (go):

![go "G"](https://raw.githubusercontent.com/zspace/system.software.interview.gol.public/master/gol-cs/8.gol-client-send-go-G-command.png)

* The "**Q**" command (quit) should disconnect and terminate the client, but leave the server running.

* The "**K**" command (kill) should terminate the server, and then terminate the client.

* You can use this template for Exercise #2 (or roll your own from scratch):

![gol-cs code structure server](https://raw.githubusercontent.com/zspace/system.software.interview.gol.public/master/gol-cs/gol-server.png)
![gol-cs code structure client](https://raw.githubusercontent.com/zspace/system.software.interview.gol.public/master/gol-cs/gol-client.png)

* Once you are proud of your results, please send all your source files, make/project/solution files necessary to build it, and resulting binaries to <system.software.jobs@zspace.com>. We prefer a GitHub repo link, but a zip archive is also acceptable.
 

