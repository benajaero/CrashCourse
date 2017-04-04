# Programming Crash Course

You can use the [editor on GitHub](https://github.com/Blaze349/CrashCourse/edit/master/README.md) to maintain and preview the content for your website in Markdown files.

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

# Architecture

Computers are made up of:
* Processor
* Random Access Memory (RAM)
* Input/s (microphone, HDD, keyboard, mouse, etc)
* Output/s (screen, HDD, speaker, etc)

### Processor

The processor is the logical component component of a computer. It is responsible for completing instructions given to it by the programmer. It reads input, processes it according to its instructions and outputs the changed input.

The processor uses the RAM to store all of its temporary values, such as variables and constants.

### RAM

RAM is responsible for storing all the data of programs that are running. It is made up of two parts, the stack and the heap.

The stack is the part of the RAM responsible for thread execution. It manages the functions running (more about this later). The stack is controlled and allocated by the operating system of the computer.

The heap is the part of the RAM that is available for dynamic allocation. The heap allows you to create variables without explicitly specifying them in code. Your program can use the heap to create variables on the fly.

### Input

Input is simply data that is given to the program. Input can take many forms such as:
* Mouse coordinates
* Key press
* Data from a file

### Output

Output is the processed, changed data of the program. The program processess the input, according to the instructions it is given and the outcome of the process is the output. 
Output is simply data. Devices that utilize output as input(programs) are things such as:
* LCD
* Audio Speaker
* File

# The root of everything
You've now learnt about the architecture of computers. You now understand the components of a computer. Now we will go into the most important section of computing. If you can implement this then you can recreate every single computer program ever created.

## Turing Machine

The Turing machine was contrived by Alan Turing in 1936. It was described as an infinitely long tape with a head. The tape represented the idea of memory, RAM. It was composed of squares that could hold 3 values. 1, 0 and null. The head represented the processsor. It could read a tile, write to a tile and edit a tile. It could also follow instructions and perform conditional checking. 

Here is a picture such a machine:
![Turing Machine](http://2009.igem.org/wiki/images/2/2d/Turing.jpg)

An example program for a turing machine is:
```
Read square
if 1 write 0 move left
if 0 write 1 move right
Repeat
```

### If you got to the end...

You the real MVP
