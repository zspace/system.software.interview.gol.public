## zSpace Coding Exercise #1:

# Conway's Game of Life (GoL)
(Trivial C Implementation)

Read: <https://en.wikipedia.org/wiki/Conway%27s_Game_of_Life>

Implement: A command line version of the Game of Life (GoL) on a 8x8 _toroidal_ grid.

* We provide a Windows [sample implementation of gol.exe](https://github.com/zspace/system.software.interview.gol.public/tree/master/bin) that demonstrates the desired functionality, and which is described below.  Your implementation should strive to follow this behavior.

* Expected behaviour using case insesitive command line argument is demonstrated below:

![gol.exe](https://raw.githubusercontent.com/zspace/system.software.interview.gol.public/master/gol/gol.random.png)
![gol.exe blinker](https://raw.githubusercontent.com/zspace/system.software.interview.gol.public/master/gol/gol.blinker.png)
![gol.exe toad](https://raw.githubusercontent.com/zspace/system.software.interview.gol.public/master/gol/gol.toad.png)
![gol.exe beacon](https://raw.githubusercontent.com/zspace/system.software.interview.gol.public/master/gol/gol.beacon.png)

* You can use this template for Exercise #1 (or roll your own from scratch):

![GoL code structure](https://raw.githubusercontent.com/zspace/system.software.interview.gol.public/master/gol/gol.c.fill-the-blanks.png)

* Please ensure that your implementation compiles without any warnings when your toolchain is configured to the highest warning level (e.g. -Wall -Wextra -pedantic-errors or equivalent)

* Once you are proud of the result, please send the _bare_ gol.c source file as an email attachment to <system.software.jobs@zspace.com>
