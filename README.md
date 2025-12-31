# NEUB-CSE-06131114-Fall-2025
NEUB CSE Structured Programming Languaage Lab Fall 2025

## List of Labs
1. [Lab 1](https://github.com/shparvez001/NEUB-CSE-06131114-Fall-2025/blob/main/lab-01.md).
    1. Write a program which will print your name in one line and your id in another line.
    2. Printing a right triangle pattern using star.
    3. Write a program that asks the user to enter two numbers, obtains the two numbers from the user and prints the sum, product, difference and quotient of the two numbers.
    4. Write a program that takes a lower-case letter from the user and convert it into an upper-case letter. 
2. [Lab 2](https://github.com/shparvez001/NEUB-CSE-06131114-Fall-2025/blob/main/lab-02.md).
    1. Write a program to input 2 numbers and print the one that is higher. 
    2. Write a program to print 100 to 1 with space in between them.
    3. Write a program to add the digits of a number.
    4. Write a program to reverse a number.
    5. Write a program to print the numbers from 1 to 100 on the screen. Skip those numbers which are divisible by 3 or 5 but not by both. 
3. [Lab 3](https://github.com/shparvez001/NEUB-CSE-06131114-Fall-2025/blob/main/lab-03.md).    
    1. Write a program that will generate the Fibonacci series of length n.
    2. Write a program to print a 5 × 5 square of *.
    3. Write a program to print a pyramid with n levels where n will be taken as input.
    4. Write a program to print a diamond with n levels where n will be taken as input.
    5. Write a program to print the following pattern:
        ```
        n: 3
        a
        bb
        ccc

        n: 4
        a
        bb
        ccc
        dddd
        ```
4. [Lab 4](https://github.com/shparvez001/NEUB-CSE-06131114-Fall-2025/blob/main/lab-04.md). 
    1. Write a C program that will take 2 numbers as input and print the prime numbers between them. The numbers can be in either order.
    2. Write a C program to take 2 numbers as input and print the HCF and LCM of them. The numbers can be in either order. 
    3. Write a C program takes marks of n subjects and print the GPA. Here n will be taken as input.
    4. Write a program to print the following pattern: 
        ```
        n: 2
         /\ 
        /__\ 

        n: 3
          /\ 
         /  \ 
        /____\

        n: 4
           /\ 
          /  \ 
         /    \ 
        /______\
        ```
5. [Lab 5](https://github.com/shparvez001/NEUB-CSE-06131114-Fall-2025/blob/main/lab-05.md). 
    1. Write a program that will declare a n-element integer array where n should be taken as input. Fill the array with integers taken from the user and show the sum and average of the integers. 
    2. Write a program that will declare a 10-element integer array. The array will be filled up by random integers in the range [0, 100]. Use the library functions `rand()` and `srand()` defined in `stdlib.h` to perform the task. After that, determine the maximum element, minimum element and the average of the numbers.
    3. Write a program that will read the marks of 40 students in an array and determine the frequency of grades. The marks will be in the range [25, 99].
    4. Write a program to sort an array of 20 integers using the **_Bubble Sort_** algorithm.

6. [Lab 6](https://github.com/shparvez001/NEUB-CSE-06131114-Fall-2025/blob/main/lab-06.md). 
    1. Write a program to calculate the sum of each row and column of a 2-D array.
    2. Write a program to find the transpose of a matrix.

7. [Lab 7](https://github.com/shparvez001/NEUB-CSE-06131114-Fall-2025/blob/main/lab-07.md). 
    1. Write a function to check if a number is prime or not. Use this function to find the prime numbers from a to b where a and b will be integer number inputted by user.
    2. Write a recursive function `fibonacci(int n)`, which returns the n-th Fibonacci number. Note that the first two Fibonacci numbers are 0 and 1, respectively.
    3. Write a recursive function `get_gcd(int a, int b)`, that will return the GCD of two integers a and b.
    4. Define a recursive function `print(int n)`, that prints all the odd positive integers up to n. For example, calling `print(99)` will cause the program to print the following sequence: 

        ```1 3 5 7 ….. 99```
 
8. [Lab 8](https://github.com/shparvez001/NEUB-CSE-06131114-Fall-2025/blob/main/lab-08.md). 
    1. Write a program to implement the following functions:
        ```
        int str_len(char str[]);
        void str_cat(char destination[], char source[]);
        void str_cpy(char destination[], char source[]);
        int str_cmp(const char s1[], const char s2[]);
        void str_rev(char s[]);
        ``` 
    2. olve UVA [problem 458](https://onlinejudge.org/index.php?option=com_onlinejudge&Itemid=8&page=show_problem&problem=399). [[PDF](https://onlinejudge.org/external/4/458.pdf)]

9. [Lab 9](https://github.com/shparvez001/NEUB-CSE-06131114-Fall-2025/blob/main/lab-09.md). 
    1. Write a function `swap(int *x, int *y)` that swaps two integers.
    2. Declare an integer array with 5 elements and use a pointer to print and sum the array elements.
    3. Write a program that does the following things
        1. Ask user for n (number of integers).
        2. Allocate memory dynamically using malloc().
        3.	Input and display values using pointers.
        4.	Free the memory.
    4. Write a program to input a string and copy it into another string manually using pointers. Print both strings.

10. [Lab 10](https://github.com/shparvez001/NEUB-CSE-06131114-Fall-2025/blob/main/lab-10.md). 
    1. Create a structure named *Student* with the following members:
        ```
        int id
        char name[50]
        float cgpa
        ```
        Write a program to Declare a variable of type *Student*, Take input from the user, and Display all details in a formatted output
    2. Define a structure *Book* with:
        ```
        char title[50]
        char author[50]
        int price
        ```
        Write a program to Take input for *5 books*, and print each of them.
    3. Create a structure Rectangle with:
        ```
        int width
        int height
        ```
        Write a program with the following functions:
        ```
        int area(struct Rectangle r);          
        void changeSize(struct Rectangle *r);     
        ```
        Inside `main()`:
        * Input width & height
        * Call area() and print the result
        * Call changeSize() (increase width & height by 10)
        * Print updated values

11. [Lab 11](https://github.com/shparvez001/NEUB-CSE-06131114-Fall-2025/blob/main/lab-11.md). 
    1. Creating a simple phone directory application with ability to store the data in a file and able to retrive data from the file.