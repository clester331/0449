# Lecture 2 - Data Representation

## Positional Numbers
* The numbers we use are written **positionally**: the position of a digit within the number has a meaning (2023 - > 2000 + 000 + 20 + 3)
  * The smallest non-negative number representable with n digits is 0
  * The largest number represented by n digits is 10<sup>n</sup> - 1
* We canll a binary digit a bit - a single 0 or 1
  * ![image](https://github.com/clester331/0449/assets/122314614/4b8d761a-3771-4f43-9135-124d602db168)
* In base 2, the smallest non-negaitve number is 0
  * Largest number is 2<sup>n</sup> - 1  

## Hexidecimal
* Digit symbols are A-F meaning 10-15 respectively (ex: 003B EE70)
* Hex is usually shorthand for binary
  * ![image](https://github.com/clester331/0449/assets/122314614/cc38b14f-b27e-452b-8020-10ed98498a22)
 
## Lecture Encoding

### The Finitude of Variables
![image](https://github.com/clester331/0449/assets/122314614/ce36fdec-f228-4281-89f0-c8ad5d420f2c)

### Twos Compliment
![image](https://github.com/clester331/0449/assets/122314614/d52a3337-119a-4710-a120-4c704b205d27)
* Addition
* ![image](https://github.com/clester331/0449/assets/122314614/0646577a-a575-453c-bde0-6e2a56542d1d)

### Integer Ranges
* Range of an unsigned integer: 0 - 2<sup>n</sup> - 1
* Range of signed integer: -2<sup>n-1</sup> to 2<sup>n-1</sup> – 1
