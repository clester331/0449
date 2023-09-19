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







  




