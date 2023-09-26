# Lecture 9

## Files 

### Files Intro

* These files are automatically open and ready
  * stdin - The standard input
  * stdout - The standard output
  * stderr - The standard error

* Example of implicit utilization:
  * printf("Hello World\n") -> writes to stdout
  * scanf("%d", &x) -> reads from stdin
 
### Making it Explicit

* Other print functions:
  * fprintf/fscanf - the first f stands for "file"
 
* These are equivalent forms of printing
  
  ![image](https://github.com/clester331/0449/assets/122314614/56d01b3f-5dd9-4237-8902-4f02cffd8203)

* These are equivalent forms for reading
  
  ![image](https://github.com/clester331/0449/assets/122314614/9b36aa7d-4b29-4da5-abd8-eefda2f9ace9)

* File operations: **Open**
  * FILE *fopen( const char *path, const char *mode );
* What are the arguments?
  * The path is the location of th efile in the computer
  * The mode selects wich operations can be done
    
  ![image](https://github.com/clester331/0449/assets/122314614/6c6d7996-17b3-4c3d-a6d2-c187f135c456)

* What does it return?
  * FILE * -> A file stream that can be used to access the contents
  * null on error
    * A value is set (errno)  
     
### Closing

* File operations: **close**
  * int fclose( FILE *stream );

* What are the arguments?
  * FILE *stream -> the file streamed returned on open
* What is the return?
  * 0 on success
  * EOF (end of file) on error
    * A value is set (errno)

* Always close a file that is being written to, or data may not be written

![image](https://github.com/clester331/0449/assets/122314614/4db852c5-9f22-4475-9db9-48a55ea4f389)

### Standard Error

*Althuogh it may seem like a normal printf, stderr can seperate error messages from regular output

![image](https://github.com/clester331/0449/assets/122314614/3eba77d3-7155-43f8-9192-5f245575a5dc)

### Everything is in binary

![image](https://github.com/clester331/0449/assets/122314614/3d1323f7-43ef-415b-9d85-a3eada3d44d0)

### Reading Binary Files

* File Operations: **read**
  * size_t fread( void *ptr, size_t size, size_t n_items, FILE *stream );

* What are the arguments?
  * void *ptr -> The memory address where the data is stored
  * size_t size -> The size of each item being read
  * size_t n_items -> The number of items to read
  * File *stream -> The file stream to **read from**

* What is the return?
  * Number of items read
  * Something went wrong if 0 or less thatn n_items is returned

### Reading Binary Files

* File Operations: **rwrite**
  * size_t fwrite( void *ptr, size_t size, size_t n_items, FILE *stream );

* What are the arguments?
  * void *ptr -> The memory address where the data is stored
  * size_t size -> The size of each item being read
  * size_t n_items -> The number of items to read
  * File *stream -> The file stream to **write to**

* What is the return?
  * Number of items written
  * Something went wrong if less than n_items returned

### What Happens on read/write

* When a file is open, a cursor is initialized to the beginning of the file
  * Except if you open with the "a" (append) option, then the cursor is at the end
* On read/write the cursor is moved forwards and data read/written

![image](https://github.com/clester331/0449/assets/122314614/06675432-ff4f-4755-b0f8-f72525d7503b)

### Controlling the cursor

* File operations: **Move the cursor**
  * int fseek(FILE *stream, long offset, int whence);

* What are the arguments?
  * FILE *stream -> The file stream to read from
  * long offset -> The offset to move the cursor
  * int whence -> Where to move the cursor from (use constants)
    * Option 1 - SEEK_SET -> Move relative to the beginning of the file
    * Option 2 - SEEK_CUR -> Move relative to the current cursor position
    * Option 3 - SEEK_END -> Move relative to the end of the file
   
* What is the return?
  * 0 if successful
  * -1 if error
    * errno variable is set     
  
