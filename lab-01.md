# NEUB CSE-06131114 Fall 2025 Lab 1

## Task 1
Write a program which will print your name in one line and your id in another line.

## Task 2
Write a program to print the following pattern:

_Sample Execution_
```
* 
** 
*** 
**** 
*****
```

## Task 3
Write a program that asks the user to enter two numbers, obtains the two numbers from the user and prints the sum, product, difference and quotient of the two numbers.

_Sample Execution_
```
Enter 1st number: 25 
Enter 2nd number: 5 
Sum: 30 
Product: 125 
Difference: 20 
Quotient: 5
```

## Task 4
Write a program that takes a lower-case letter from the user and convert it into an upper-case letter. 

_Sample Execution_
```
Sample Output: 
Enter a lower-case letter: a 
The upper-case equivalent is: A 
```
(You need some knowledge about ASCII for writing this program. Google it if you are not familiar with ASCII) 


## Solution
### Task 1
Write a program which will print your name in one line and your id in another line.
```c
#include<stdio.h>
int main()
{
    printf("Shahadat Hussain Parvez\n2010338004");
    //printf("2010338004");

    return 0;
}
```

### Task 2
Write a program to print the following pattern:
```c
#include<stdio.h>
int main()
{
    printf("*\n**\n***\n****\n*****");

    return 0;
}
```


### Task 3
Write a program that asks the user to enter two numbers, obtains the two numbers from the user and prints the sum, product, difference and quotient of the two numbers.
```c
#include<stdio.h>
int main()
{
    int A, B;
    printf("Enter 1st number: ");
    scanf("%d", &A);
    printf("Enter 2nd number: ");
    scanf("%d", &B);
    printf("Sum: %d\n", A+B);
    printf("Product: %d\n", A*B);
    printf("Difference: %d\n", A-B);
    printf("Quotient: %d\n", A/B);

    return 0;
}
```


### Task 4
Write a program that takes a lower-case letter from the user and convert it into an upper-case letter. 
```c
#include<stdio.h>
int main()
{
    char inp;
    printf("Enter a Character in lowercase: ");
    scanf("%c", &inp);
    printf("The Uppercase of the character is %c", inp-32);

    return 0;
}
```
