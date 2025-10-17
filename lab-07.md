# NEUB CSE-06131114 Fall 2025 Lab 7

## Task 1
Write a function to check if a number is prime or not. Use this function to find the prime numbers from a to b where a and b will be integer number inputted by user.

## Task 2
Write a recursive function `fibonacci(int n)`, which returns the n-th Fibonacci number. Note that the first two Fibonacci numbers are 0 and 1, respectively.

## Task 3
Write a recursive function `get_gcd(int a, int b)`, that will return the GCD of two integers a and b.

## Task 4
Define a recursive function `print(int n)`, that prints all the odd positive integers up to n. For example, calling `print(99)` will cause the program to print the following sequence:
`1 3 5 7 ….. 99`



## Solution
### Task 1
Write a function to check if a number is prime or not. Use this function to find the prime numbers from a to b where a and b will be integer number inputted by user.

```c
#include<stdio.h>
int isPrime(int n){
    int i;
    if(n<2)
        return 0;
    for(i=2;i*i<n;i++)
    {
        if(n%i==0)
            return 0;
    }
    return 1;

}

int main()
{
    int i, a, b;
    scanf(" %d %d", &a, &b);
    for(i=a;i<=b;i++)
    {
        isPrime(i)?printf("%d\t", i):printf("");
    }
    return 0;
}
```


### Task 2
Write a recursive function `fibonacci(int n)`, which returns the n-th Fibonacci number. Note that the first two Fibonacci numbers are 0 and 1, respectively.

```c
#include<stdio.h>

int fibonacci(int n)
{
    if (n==0)
        return 0;
    else if (n==1)
        return 1;
    else
        return fibonacci(n-1)+fibonacci(n-2);
}

int main()

{
    int n;
    printf("Enter n: ");
    scanf("%d", &n);
//    printf("%d", fibonacci(n));


    printf("Fibonacci series upto %d terms: \n", n);

    for(int i=0; i<n; i++)
    {
        printf("%d ", fibonacci(i));
    }
    printf("\n");

    return 0;
}
```


### Task 3
Write a recursive function `get_gcd(int a, int b)`, that will return the GCD of two integers a and b.

```c
#include<stdio.h>

int gcd(int a, int b);

int main()
{
    int a=125, b=20, hcf;
    hcf=gcd(a, b);
    printf("%d", hcf);
    return 0;
}

int gcd(int a, int b)
{
    if(b==0)
        return a;
    return gcd(b, a%b);
}

//int gcd(int a, int b)
//{
//    if(a%b==0)
//        return b;
//    else{
//        return gcd(b, a%b);
//    }
//}
```


### Task 4
Define a recursive function `print(int n)`, that prints all the odd positive integers up to n. For example, calling `print(99)` will cause the program to print the following sequence:
`1 3 5 7 ….. 99`

```c
#include<stdio.h>

void print(int n)
{
    if (n<1)
        return;
    print(n-2);
    printf("%d\t", n);
}

int main()
{
    int n=99;
    print(n);
    return 0;
}
```

