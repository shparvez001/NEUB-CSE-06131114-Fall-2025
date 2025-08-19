# NEUB CSE-06131114 Fall 2025 Lab 3

## Task 1
Write a program that will generate the Fibonacci series of length n.

_Sample Execution_
```
Enter length: 12
0 1 1 2 3 5 8 13 21 34 55 89
```

## Task 2
Print a 5 × 5 square of *.

_Sample Execution_
```
*****
*****
*****
*****
*****
```

## Task 3
Write a program to print a pyramid with n levels where n will be taken as input.

_Sample Execution_
```
n: 3
  *
 ***
*****
n: 4
   *
  ***
 *****
*******
n: 5
    *
   ***
  *****
 *******
*********
```


## Task 4
Write a program to print a diamond with n levels where n will be taken as input.

_Sample Execution_
```
n: 2
 *
***
 *
n: 3
  *
 ***
*****
 ***
  *
n: 4
   *
  ***
 *****
*******
 *****
  ***
   *
```

## Task 5
Write a program to print the following pattern:

_Sample Execution_
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
n: 5
    a
   bb
  ccc
 dddd
eeeee
```

## Solution
### Task 1
Write a program that will generate the Fibonacci series of length n.


```c
#include<stdio.h>
int main()
{
    int i, n, f0, f1, temp;
    f0=0;
    f1=1;

    printf("Enter length: ");
    scanf("%d", &n);
    for(i=1;i<=n;i++)
    {
        printf("%d ", f0);
        temp=f0+f1;
        f0=f1;
        f1=temp;
    }

    return 0;
}
```

### Task 2
Print a 5 × 5 square of *.

```c
#include<stdio.h>
int main()
{
    int i, j, n=5;
    for(i=1;i<=n;i++)
    {
        for(j=1;j<=n;j++)
        {
            printf("*");
        }
        printf("\n");
    }
    return 0;
}
```

### Task 3
Write a program to print a pyramid with n levels where n will be taken as input.


```c
#include<stdio.h>
int main()
{
    int i, j, n;
    while(1)
    {
        printf("n: ");
        scanf("%d", &n);
        if(n==0)
            break;
        for(i=1; i<=n; i++)
        {
            for(j=1; j<=(n-i); j++)
            {
                printf(" ");
            }
            for(j=1; j<=(2*i-1); j++)
            {
                printf("*");
            }
            printf("\n");
        }
    }

    return 0;
}
```


### Task 4
Write a program to print a diamond with n levels where n will be taken as input.


```c
#include<stdio.h>
int main()
{
    int i, j, n;
    while(1)
    {
        printf("n: ");
        scanf("%d", &n);
        if(n==0)
            break;
        for(i=1; i<=n; i++)
        {
            for(j=1; j<=(n-i); j++)
            {
                printf(" ");
            }
            for(j=1; j<=(2*i-1); j++)
            {
                printf("*");
            }
            printf("\n");
        }
        for(i=n-1; i>=1; i--)
        {
            for(j=1; j<=(n-i); j++)
            {
                printf(" ");
            }
            for(j=1; j<=(2*i-1); j++)
            {
                printf("*");
            }
            printf("\n");
        }
    }

    return 0;
}
```

### Task 5
Write a program to print the following pattern:

```

n: 5
    a
   bb
  ccc
 dddd
eeeee
```
```c
#include<stdio.h>
int main()
{
    int i, j, n;
    while(1)
    {
        printf("n: ");
        scanf("%d", &n);
        for(i=1; i<=n; i++)
        {
            for(j=1;j<=(n-i);j++)
            {
                printf(" ");
            }
            for(j=1;j<=i;j++)
            {
                printf("%c", i+'a'-1);
            }
            printf("\n");
        }
    }
    return 0;
}
```