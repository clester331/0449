# Lecture 4

## Integers in C: Limits
* Since size of integers are technically arbitrary, they are usually based on the understanding architecture
* C provides standard library constants defining the ranges
  
![image](https://github.com/clester331/0449/assets/122314614/73efe0ef-f339-4de1-9f76-7019029ae786)

* sizeof gives us the ability to programmatically obtain the byte size of data
 
![image](https://github.com/clester331/0449/assets/122314614/e4a27c61-ccef-4c75-b6f7-b14e5c439838)

* **Sizes of C Data Types**

![image](https://github.com/clester331/0449/assets/122314614/62628189-4d4b-4170-8043-a05a2ec408ad)

## Integer Casting

* Explicit conversion between signed & unsigned

![image](https://github.com/clester331/0449/assets/122314614/d682c9f1-e396-4765-b331-0df919baab7c)

* C Lets you move a value from an unsigned integer variable to a signed integer variable. (and vice versa)
* This is not always valid however, yet it will do it anyways
  * The binary value is the same. **Its interpretation is different**
  * Since it ignores obvious invalid operations this is sometimes referred to as “weak" typing.
  • The strong/weak terminology has had very fragile definitions over the years and are arguably useless in our context. Let’s ignore them.
* Moving values between different types is called **Casting**.
### Example of coercion -> bits are unchanged
![image](https://github.com/clester331/0449/assets/122314614/32541e16-551b-4893-8386-f550310aaf40)

* Implicit casting also occurs via assignments and procedure calls
  
![image](https://github.com/clester331/0449/assets/122314614/6b915bd9-3874-4140-8c4b-43548df2a4df)

* Integer literals (constants)
  * By default, integer constants are considered signed integers
  * Use "U" (or "u") sufix to explicitly force unsigned
* Expression Evaluation
  * When you mix unsigned and signed in a single expression, **signed values are implicity casted to unsigned**
* Watch out for implicit casts!
  
![image](https://github.com/clester331/0449/assets/122314614/a8c11f1b-eb35-4b8d-84f5-d567b0f3c6d5)

## Floating Point in C
* C garuntees two levels
  * Float - single percision
  * double double percision
* Conversion/Casting
  * Casting between int, float, and double changes bit representation
  * double/loat -> int
    * Truncates fractional part
    * Like rounding towards zero
    * Not defined when out of range or Nan: Genreally sets to TMin
  * int -> double
    * Exact conversion, as long as int has <= 53 bit word size
  * int -> float
    * wukk round according to rounding mode
   
### Floating Point Summery
* Systems don't usually use floats
* Floats also suffer from the fixed number of bits available to represent them
  * Can get overflow/underflow
  * “Gaps” produced in representable numbers means we can lose precision, unlike
* Floating point arithmetic not associative or distributive
* Never test floating point variables for exact equality 
