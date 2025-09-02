# NEUB CSE-06131114 Fall 2025 Lab 2

## Task 1
Write a program to input 2 numbers and print the one that is higher. 

_Sample Execution_
```
Enter 2 numbers: 51 65 
65 is bigger
```


## Task 2
Write a program to print 100 to 1 with space in between them.

_Sample Execution_
```
100 99 98 97 96 95 94 93 92 91 90 89 88 87 86 85 84 83 82 81 
80 79 78 77 76 75 74 73 72 71 70 69 68 67 66 65 64 63 62 61 60 
59 58 57 56 55 54 53 52 51 50 49 48 47 46 45 44 43 42 41 40 39 
38 37 36 35 34 33 32 31 30 29 28 27 26 25 24 23 22 21 20 19 18 
17 16 15 14 13 12 11 10 9 8 7 6 5 4 3 2 1 
```


## Task 3
Write a program to add the digits of a number.

_Sample Execution_
```
Enter a number: 69837 
The sum of the digits of this number is: 33
```



## Task 4
Write a program to reverse a number.

_Sample Execution_
```
Enter a number: 126584 
The reverse number is: 485621 
```

## Task 5
Write a program to print the numbers from 1 to 100 on the screen. Skip those numbers which are divisible by 3 or 5 but not by both. 

_Sample Execution_
```
0 1 2 4 7 8 11 13 14 15 16 17 19 22 23 26 28 29 30 31 32 34 37 
38 41 43 44 45 46 47 49 52 53 56 58 59 60 61 62 64 67 68 71 73 
74 75 76 77 79 82 83 86 88 89 90 91 92 94 97 98
```



## Solution
### Task 1
Write a program to input 2 numbers and print the one that is higher. 

```c
#include<stdio.h>

int main()
{
    int a, b;
    printf("Enter 2 numbers: ");
    scanf("%d %d", &a, &b);
    //This can be done either by ternary operator or by if-else 
    //(a>b)?printf("%d is bigger", a):printf("%d is bigger", b); 
    if(a>b)
    {
        printf("%d is bigger", a);
    }
    else
    {
        printf("%d is bigger", b);
    }
    return 0;
}
```

### Task 2
Write a program to print 100 to 1 with space in between them.

```c
#include<stdio.h>

int main()
{
    int a=100;
    while(a>0)
    {
        printf("%d ", a);
        a--;
    }

    return 0;
}

```


### Task 3
Write a program to add the digits of a number.

```c
#include<stdio.h>

int main()
{
    int n, sum=0;
    printf("Enter a number: ");
    scanf("%d", &n);
    while(n>0)
    {
        sum+=n%10; 
        n/=10; 
        //same outcome is possible without using compound assignment. To do that use the following 2 lines of code
        //sum=sum+n%10;
        //n=n/10;
    }
    printf("The sum of the digits of this number is: %d", sum);
    return 0;
}

```


### Task 4
Write a program to reverse a number.

```c
#include<stdio.h>

int main()
{
    int n, reverse=0;
    printf("Enter a number: ");
    scanf("%d", &n);
    while(n>0)
    {
        reverse=reverse*10+(n%10);
        n=n/10;
    }
    printf("The reverse Number is: %d", reverse);
    return 0;
}
```

### Task 5
Write a program to print the numbers from 1 to 100 on the screen. Skip those numbers which are divisible by 3 or 5 but not by both. 

```c
#include<stdio.h>

int main()
{
    int i=1, n=100;
    while(i<=n)
    {
        if(!((i%3==0 || i%5==0) && i%15!=0))
        {
            printf("%d ", i);
        }
        i++;
    }

    return 0;
}
```
