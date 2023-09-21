# Lecture 8 (9-21-23)

## Strings

### Strings/Arrays

* Strings are arrays, and as such, inherit all their limitations/issues
  * The size is not stored
  * They are essentially just pointers to memory
* Text is represented as an array of char elements

### String length

* Arrays in C are just pointers and as such **do not store their length**
  * They are simply continuous sections of memory!

* Two common ways of expressing length
  * Storing the length alongside the array
  * Storing a special value within the array to mark the end (sentinel value)

* Strings in C commonly employ a sentinel value
  * Such a value must be something considered invallid for actual data

### The String Literal

* String literals ar char pointers in C (That is: char*)
* The contents of the literal are read-only (immutable) so it is a: const char*
  * Modifying it will crash the program
![image](https://github.com/clester331/0449/assets/122314614/ed50558f-a34e-40a0-8f5a-3c2301e99e74)

### strlen

* The strlen standard library function reports the length of a string
  * This is done roughly in O(n) time as it must find the sentinel.
  * The following cofe investagates and prints out the sentinel
  ![image](https://github.com/clester331/0449/assets/122314614/1da78baa-7be0-4e93-a649-2643140178fb)
  ![image](https://github.com/clester331/0449/assets/122314614/f8d31453-0f12-4be0-93ff-842589183328)
  ![image](https://github.com/clester331/0449/assets/122314614/ab91b926-cdc3-43f6-8f74-f6ac50213dd6)

### Comparing Strings

* When you compare strings using == it compares the addresses
  * Since string literals are constat, they only exist in the executable once/
  * All references will refer to the same string
  ![image](https://github.com/clester331/0449/assets/122314614/19b7eac6-d3b6-4adc-8d94-e3ebc1fdbf60)
* When the addresses differ, they are note equal
* To compare values, use the standard library's strcmp
  * This will perform a byte by byte comparison of the string
  * Therefore, it is case sensitive. It has O(n) time complexity
  ![image](https://github.com/clester331/0449/assets/122314614/947bcd8b-be0d-4913-96e1-3b1c8942b916)
* strcpy starts at the beginning while strncat adds on to an existing string

### Memory Allocation & Input/Output Summary

![image](https://github.com/clester331/0449/assets/122314614/13ed88e0-e12b-471c-8018-784369041e2e)
![image](https://github.com/clester331/0449/assets/122314614/6884c72e-45b5-4407-b53f-b0a22a9bac46)

## Structures

### Allocated Structures

*You are going to allocate a lot of structures
  * They are big in size and are needed around, therefore, they are not good on the stack
  * You could make them golbals, except when you want them dynamically.
![image](https://github.com/clester331/0449/assets/122314614/db1de61f-5bb9-4cdd-b2a5-a73aa61f9135)

### Pointing to structure fields

* A shorthad for (*p_song).field is p_song -> field
  * The arrow syntax works only on struct pointers and dereferencs a field
  ![image](https://github.com/clester331/0449/assets/122314614/e77d5707-db6a-4f4f-8c90-e9e1071da17e)


### Pointing to structure fields

* Recall that typedef is what names types.
  * If you want a song data type, you can use typedef to do so: 

### NULL Pointer error

* When we need to denote that we are not pointing to anything
  * We use a null value and hope that nobody derefences it
  * It is not built-in, we must include stddef.h to use it
  ![image](https://github.com/clester331/0449/assets/122314614/a7dd689c-fa3c-4df1-a266-8c78f50fb5f7)
* When your request for memory cannot be made, malloc returns Null
  * In your perfect program, you would always check for this
* You can check if ptr is null with if(!ptr)
  * C specifically considers any pointer equal to NULL to be a false value 


