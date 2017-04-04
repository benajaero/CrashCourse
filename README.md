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
This is a complete computer program. Any algorithm can be replicated in a Turing machine. To create your own Turing machine it must have:
* A place to store memory
* The ability to read from a memory address
* The ability to write to a memory address
* The ability to move memory addresses
* The ability to do above methods according to specified instructions

A machine that can do all of the above is known as Turing Complete.

## Reading the instructions

The turing machine, like all computers, doesn't understand english. In fact it doesn't understand anything but 1 and 0. It is very stupid. But it is very good at doing menial repetitive tasks quickly and without errors. So how do we teach it?

In the early days of computing people wrote their computer programs in binary. With just two numbers. Then some smart guys realised this wasn't sustainable or efficient and created a faster way of doing things.They invented...

### Assembly

Assembly was revolutionary. It allowed them to write programs in a more human-readable form and convert it to be read by the processor. They wrote code in assembly then ran it through an **assembler** that converted it into binary code.
Assembly code:
```
MOV R0, R7
```

It is still hard to read but is definitely better than:
```
0x0700A0E1
```

The main problem with Assembly, aside from its readability, is that it is platform-specific code. Assembly for one processor will not work on another processor. Even if they are made by the same company. This made it harder to easily share knowledge.
The next innovation solved the problem.

### Compiled languages

Rather than writing in assembly people could now write in a human readable language. Compiled lanuages are not platform-specific. They compile down into the assembly code of whatever processor the system has then assemble into binary code

With compiled languages we can do: 
```
int x = 10;
```
One line. 11 characters. Easy.

# Coding concepts

# Expressions
Expressions are the smallest piece of code that can be executed by a computer.
They are pieces of code made up of variables, constants, literals and functions that evaluate into a single value.

A simple expression is:
```
9 + 3
```
This evaluates to 12.

You can add variables to expressions:
```
int x = 3;
x + 4;
```
To solve this the computer finds the value of x and adds it to 4. It evaluates to seven.

You can use functions (will explain) in expressions:
``` C++
int add(int x, int y) {
	return x + y
}
add(2,5) * 5
```
The computer runs the add function first and receives the value 7. Then it multiples 7 by 5, evaluating the expression as 35.
Next, statements.

### Statements

A statement is a complete line of code executed by a computer. A statement is one instruction.
Some statements:

``` javascript
//statement 1
var x = 3

//statement 2
getPhysical()

//statement 3
return x - 1

//statement 4
var g = getPhysical()

```

### Variables

Variables allow us to store, reuse and change a specific value. 
In most C-based language we can declare variables in this format:
```
int x = 2;
```
We have the name of the variable on the left side and value on the right side of the **assignment operator**

We can change variables by using operators. Here are some operators.
```
* // Multiplication operator
+ // Addition and string concatenation operator
- // Subtraction operator
/ // Division operator

= // Assignment operator. Makes the object on the left side equal to the object on the right side.
== // Equality operator: Checks to see if both values are the same. If the same returns 'true' if not the same returns 'false'
x == x || y == y // OR: operator: The '||' Checks if either one conditions or both conditions are equal to true then returns true or false
x == x && y == y // AND: Checks if both conditions are equal to true
!= // NOT operator Returns true if unequal returns false otherwise

++ //increments variable by 1
+= //increments variable by value on right hand side
-- //deincrements by 1
-= //deincrements variable by value on right hand side
```

Variables have type and scope. The types can be numbers, strings, boolean, enums, classes or structs. 
Some types are the:
```
Int //integer
Float // Floating point number
Double // Bigger float
Long // bigger Int
String // collection of Char
Char // Single character
```
You can also make your own types. Some languages are *dynamically-typed* which means you don't have to define a time. The type is inferred from the variable's value.

Variables are stored in two places. Variables declared within functions are stored with the funcion in the stack part of the RAM. The variables can only be accessed with their parent function. They are known as local variables.

Variables can also be stored in the heap. All global variables(variables outside every function) are stored in the heap. You can use the heap to dynamically allocate a variable. Here is a simple program that repeatdly creates and allocate a new variable in C++. You use pointers for this.

``` c++
for (int i = 1; i <= 10; i++) {
	int *ptr = new int;
	*ptr = i;
	std::cout << *ptr;
	delete ptr;
}
```
This program prints the numbers from 1 to 10. 

### Function

There is a well-known rule in the programming world. 
**Don't.Repeat.Yourself!**

*But how can we do this? Won't we inevitably write the same instructions twice?*
We can use functions! 

Whenever you find that you've written the same code more than once, consider using a function instead.
Functions are **blocks** of code that allow you to repeat the same code without typing it again and again. Functions decrease bugs and increase workflow and speed.

A function looks something like this (pseudocode): 
```
doSomething(parameters) {
 //stuff...
}

// or as in the previous example

func add(x,y) {
	return x + y
}
```
A function is made up of a function keyword, a name, a list of parameters/arguments, code inside. 
The function keyword is what you use to declare the function. Some languages make the return type the function keyword but some languages use the **keywords** func, def or function.

Parameters are placeholder values for the function to work with. In our example above, the function add has two parameters. X and Y. x and y can be any number. If you removed the parameters and returned a literal you would have to write a different function for every addition expression ever (infinite). By just using placeholdlers, you can then allow the user of the function to subsitute x and y for their own **arguments**. 

Lets see how we can do that, but first let us explain arguments, parameters and *passing*. Parameters are placeholders for functions to use. They have a type. Arguments are the values that you put in place of the placeholders when you call the function. Passing is the action of replacing the placeholders/parameters with your arguments.

Ok lets try writing a function and calling it with our own arguments: 
``` c++
//define the function
int add(int x, int y) {
	return x + y;
}
// call it with our own values

add(2,8);
// There, magic.
```
What happens when you call a function? The function is added onto the top of the stack as becomes the primary thing the processor is executing. When the function **returns** it gives control of the computer to the next object in the stack. Last on. First out.

**Return**:
Functions can, but don't have to, return values. A function is evaluated to return a single value. If it doesn't it returns null/void/nil. If it does return a value then the function in the expression will be evaluated as the return value.

**First class functions**:
Some languages have the ability to store functions as variables. This allows for callbacks and other fancy things.
Javascript is a good example of this.
``` javascript
var append = function(list, value) {
	return list += value 
}
```

## Controlflow

## If/else/elseif

## Switch

## For loops

## Do while loops

## Async

### If you got to the end...

You the real MVP
