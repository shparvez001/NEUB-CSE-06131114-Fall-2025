# NEUB CSE-06131114 Fall 2025 Lab 4

## Task 1
Write a C program that will take 2 numbers as input and print the prime numbers between them. The numbers can be in either order. 

_Sample Execution_
```
? 50 5 
5   7   11   13   17   19   23   29   31   37   41   43   47 
```

## Task 2
Write a C program to take 2 numbers as input and print the HCF and LCM of them. The numbers can be in either order. 

_Sample Execution_
```
? 50 15 
HCF= 5, LCM= 150 
```

## Task 3
Write a C program takes marks of n subjects and print the GPA. Here n will be taken as input. Consider the mark to grade point below. 
80 −100 →4.00,   75−79 → 3.75,   70−74 →3.50,      
65 −69,3.25,    60−64 → 3.00,      55−59 → 2.75,      
50 −54 →2.50,   45−49 →2.75,    40−44 →2.00,     0−39→0.00  

_Sample Execution_
```
How Many Subjects? 5 
Enter mark for subject 1: 5 
Enter mark for subject 2: 60 
Enter mark for subject 3: 70 
Enter mark for subject 4: 80 
Enter mark for subject 5: 90 
GPA is 2.90
```


## Task 4
Write a program to print the following pattern: 

_Sample Execution_
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

## Solution
### Task 1
Write a C program that will take 2 numbers as input and print the prime numbers between them. The numbers can be in either order. 


```c
#include<stdio.h>
int main()
{
    int i, j, a, b, low, high, isPrime;
    printf("? ");
    scanf("%d %d", &a, &b);
    /*
    if(a>b){
        low=b;
        high=a;
    }
    else{
        low=a;
        high=b;
    }*/
    low=(a<b)?a:b;
    high=(a>b)?a:b;

    for(i=low;i<=high;i++)
    {
        isPrime=1;
        for(j=2;j<i;j++)
        {
            if(i%j==0)
                isPrime=0;
        }
        if(isPrime==1)
            printf("%d ", i);
    }

    return 0;
}
```

### Task 2
Write a C program to take 2 numbers as input and print the HCF and LCM of them. The numbers can be in either order. 


```c
#include<stdio.h>
int main()
{
    int a, b, low, high, rem;
    printf("? ");
    scanf("%d %d", &a, &b);
    low=(a<b)?a:b;
    high=(a>b)?a:b;
    rem=low*high;
    while(rem!=0)
    {
        rem=high%low;
        high=low;
        low=rem;
    }

    printf("HCF= %d LCM=%d", high, (a*b)/high);


    return 0;
}
```

### Task 3
Write a C program takes marks of n subjects and print the GPA. Here n will be taken as input. Consider the mark to grade point below. 
80 −100 →4.00,   75−79 → 3.75,   70−74 →3.50,      
65 −69,3.25,    60−64 → 3.00,      55−59 → 2.75,      
50 −54 →2.50,   45−49 →2.75,    40−44 →2.00,     0−39→0.00  


```c
#include<stdio.h>
int main()
{
    int i, n, mark;
    float cgp=0, gpa;
    printf("How Many Subjects? ");
    scanf("%d", &n);
    for(i=1;i<=n;i++)
    {
        printf("Enter mark for subject %d: ", i);
        scanf("%d", &mark);
        if(mark>=80) cgp+=4.00;
        else if(mark>=75) cgp+=3.75;
        else if(mark>=70) cgp+=3.50;
        else if(mark>=65) cgp+=3.25;
        else if(mark>=60) cgp+=3.00;
        else if(mark>=55) cgp+=2.75;
        else if(mark>=50) cgp+=2.50;
        else if(mark>=45) cgp+=2.25;
        else if(mark>=40) cgp+=2.00;
        else              cgp+=0;
    }
    gpa=cgp/n;
    printf("GPA is %.2f", gpa);
    return 0;
}
```


### Task 4
Write a program to print the following pattern: 


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

```c
#include<stdio.h>
int main()
{
    int n, i, j;
    while(1)
    {
        printf("n: ");
        scanf("%d", &n);
        if(n==0) break;
        for(i=1;i<=n;i++)
        {
            for(j=1;j<=n-i;j++)
            {
                printf(" ");
            }
            printf("/");
            for(j=1;j<=(2*i)-2;j++)
            {
                //(i==n)?printf("_"):printf(" ");
                if(i!=n){
                    printf(" ");
                }
                else{
                    printf("_");
                }
            }

            printf("\\");
            printf("\n");
        }

        printf("\n\n");
    }

    return 0;
}
```