# Lecture 5

## Continued...

### Taking a break and switching it up

* The switch statement requires prper placement of break to work properly
  * Starts at case matching expression and follows until it seeas a break
  * It will "fall throguh" other case statements if ther is no break between them
 
### Functions

* Must declare return type before the name
  * void is used when there is nothing to be returned
  * it is also used to explicitly denote there being no arguments
  * You should specify void instead of having an empty list
* Functions must be declared before they can be used

### Structs (NOT CLASSES)

* C gives us a very simple method of defining aggregate data types
* The *struct* keyword can combine several data types together
![image](https://github.com/clester331/0449/assets/122314614/9f16ccdb-a986-4da7-835b-87e4d19d9a2d)

### Typedef

* To avoid typing the full name "struct Song" we can create a Song type instead
* The *typedef* keyword defines new types
![image](https://github.com/clester331/0449/assets/122314614/c14aaa10-998a-4a05-9949-ea850c92b6f2)
* You can also o this with integer types. For instance to define bool:
  * typedef int bool;
* And enum types, although it wount complain if you mix/match them
  * typedef enum { cs445, cs447, cs449 } course;
* Now functions can better illustrate they take an enum value

### Garbage
* Variables do not reuqire initialization in C, but they do not have a default value
  * The OS will ultimately decide it's value
  * **Always initialize your variables**
* Every variable and data in your program technically has a location in which it lives
  * in the previous example "x" was sharing the same space as the "a" variable from the other function
* C does not imposy many rules on how memory is laid out and used

## Scope and Lifetime

### Scope

* Scope: refers to the visibility of a symbol
  * symbol: the name of something stored in memory

### Lifetime

* Refers to the validity of a variable
  * When is memory allocated? When the compiler runs
  * When does it become invalid?
![image](https://github.com/clester331/0449/assets/122314614/f285c9f1-4ae0-45b2-b4eb-f0e0df1e15df)

### Static

* THe static keyword in java is used to make class/variable functions
* You can declare static functions and global variables in C
  * It simply affects the ability of other files to use them
  * Since they are already static because their size is calculated at compile time
* This is useful for avoiding name colissions, when two functions have the same name
  * This normally would make using multiple files and other people's code troublesome
 
### Extern

* The extern keyword tells the linker that it should expect the symbol to be found elsewhere
  * Avoid using this one
* You should always avoid using global variables
  * If they are used, make sure th liberally use static, so it will stop the nmes of variables from polluting the name space
 
## Introduction to Memory

### The C Memory Model

* Memory is a continuous series of bits that can logically divided into bytes or words
* It is treated as byte-addressable, which means individual bytes can be read
* With byte addressable-memory, each and every byte (8 bits) has its own unique address (the place it lives).
* There are two main parts of a program: code and data
  * Code is somethimes called text
* Static Data is an oft forgotten but useful section
  * It does change.
  * It generally must be loaded before a program starts and the size of the data is fixed
* The stack is a space for temporary dynamic data
  * It holds local variables and function arguments
  * Allocates when functions are called. Freed on return
  * Grows "downward" (Allocates lower addresses)
* The heap is the dynamic data section
  * Managing this memory can be very complex
  * No garbage collection provided

### Arrays

* An array is a continuous span of memory
  * All the elements are the same type
* You can declare an array on the stack
![image](https://github.com/clester331/0449/assets/122314614/c5459a21-5f03-4944-9029-8f96f4f03eac)
* You can ititalize an array as it is allocated on the steack
![image](https://github.com/clester331/0449/assets/122314614/cc7ed611-fb10-432b-a73c-9410cfaa2785)
* Variables delcated on the stack are temporary
* All arrays can be considered pointers but addresses to the stack are not reliable




