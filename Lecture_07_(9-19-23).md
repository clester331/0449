# Lecture 5

## Pointers

### The "Memory Adrress" Variable Type

* A poiner s a specific variable type that holds a memory address
* You can cretae a pointer that poitns to any adress in memory
* You can tell it what type of data it should interpret that memory to be. Just place * at the end.
![image](https://github.com/clester331/0449/assets/122314614/44924f08-9fe0-444c-9fce-42769af7a1a6)

![image](https://github.com/clester331/0449/assets/122314614/cf87cffa-5cde-4c5b-9629-18fc2afc0995)

* Pointers can refer to the same address as other pointers just fine
  * **They interpret whatever binary information is there**

### Dereferencing Pointers

* If we have a variable that holds an address, normal operations change the address not the value referenced by the pointer
  * We use the **dereference Operator** ( * )
  ![image](https://github.com/clester331/0449/assets/122314614/447be279-7633-46da-ac76-beb13bfce359)

* Remember: C implicity coerces whatever value you thrw at it
* Incorrectly assigning a value to an address or vice versa will lead to compilers issuing a warning
![image](https://github.com/clester331/0449/assets/122314614/e12f92cb-5369-4490-b35e-6243d49d6268)

### Referecing Data with ( & )

* We can pull out the address to data and assign that to a pointer
* We use the **reference operator** ( & )
![image](https://github.com/clester331/0449/assets/122314614/a849e6a4-cc7d-4659-83a2-741011a91bb5)
![image](https://github.com/clester331/0449/assets/122314614/77166318-04af-4f3f-99bc-c2568104ed1a)
![image](https://github.com/clester331/0449/assets/122314614/3780a532-8bd6-4c40-b7f5-3704a1c5f299)

### The C Memory Model: The Heap
* The heap is the dynamic data section!
* You interact with the heap entirely with pointers
* malloc returns the addres to the heap with at least the number of bytes requested or NULL on errors
![image](https://github.com/clester331/0449/assets/122314614/c1254eeb-3432-4a4d-a12b-db49da425d04)

## More Arrays

* An array is simply a continuous span of memory
* we can declare an array on the stack
![image](https://github.com/clester331/0449/assets/122314614/3f506cd5-34c7-4e9c-8b99-8f1477c48758)

### Initialization
* You can initialize them depending on how they are allocated
* And the heap (for values other than 0, you'll need a loop):
![image](https://github.com/clester331/0449/assets/122314614/369091bf-41d9-4f55-b8ec-50aab77638d4)

### Function Arugments
* All arguments are passed "by value" in C
 * This means the values are copied into temporary space (the stack, usually) when the functions re called
 * This means changing those values does nt change their original sources
* However, we can pass "by reference" indirectly using pointers
 * Similar to how you pass "by reference" in Java using arrays.
   ![image](https://github.com/clester331/0449/assets/122314614/a15e8200-b9a4-42e1-a359-82552f96de3b)
* Since passed arrays are just pointers and the length is not known:
 * Accessing any elemnt is correct regardless of actual intended legth
 * No array bounds checking is the source of many very serious bugs
  * Can pull out and leak arbitray memory
  * Can potentially cause the program to execute arbitrary code
    ![image](https://github.com/clester331/0449/assets/122314614/30b4688a-4c0d-470d-9940-669a7851761b)

### Pointer Arithmetic
* Ideally, pointers should "align" to their values in memory
 * Goal: incrementing an int pointer should go to the next int in memory
* Therefor, pointer sum is scaled to the element size
 * Multiplication and other operators are undefined and result in compiler error
   ![image](https://github.com/clester331/0449/assets/122314614/486270d9-dfc8-4c82-8fcb-6476a1278959)
   ![image](https://github.com/clester331/0449/assets/122314614/490ba186-fe70-4f9b-ae23-1fae58d96bdc)





 








  




