# GDB

Gdb is a debugger for C and C++. It allows you to do things like run the program then stop whenever you want and print the values of certain variables or structures at that point.

## Compile

* you must compile it with the -g flag

Exemple:
gcc -g main.c -o main

to run gdb:
* gdb <filepath>

## The survival kit

### file
file "<path>" specifies which program you want to run and debug.

### run
run <arg1> <arg2> ... will start the debugging process and stops at the first break point.
If there is not any break points, gdb will not stop until the program finishes.

### start 
start <arg1> <arg2> ... will start the debugging process and sets the first breakpoint in the main function.

### print
print <variable> prints out the value of the variable.

### display
display <variable> prints out the value of the variable at each step.

### break
A breakpoint is the area in your program where you would like to stop the execution of your program in order to check out the values of variables within the function you are at.

to set a breakpoint:
* break function
* break filename:function
* break filename:linenumber
* break linenumber


### next
next will go to next line in the current function

### step
step steps in the current source line.

### continue
continue will continue running the program and will stop at the first breakpoint.

### help
For more information feel free to run the command help in gdb
