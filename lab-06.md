# NEUB CSE-06131114 Fall 2025 Lab 6

## Task 1
Write a program to calculate the sum of each row and column of a 2-D array.

_Sample Execution_
```
The matrix elements are:
    3       5       9
    8       3       0
    6       8       5
Sum of row 1: 17
Sum of row 2: 11
Sum of row 3: 19
Sum of column 1: 17
Sum of column 2: 16
Sum of column 3: 14


```

## Task 2
Write a program to find the transpose of a matrix.

_Sample Execution_
```
Original matrix:
        8       0       5
        6       3       6
        0       5       5

Transpose matrix:
        8       6       0
        0       3       5
        5       6       5

```



## Solution
### Task 1
Write a program to calculate the sum of each row and column of a 2-D array.

```c
#include <stdio.h>
#include <stdlib.h>
#include <time.h>

int main()
{
    int a[3][3];
    int i, j, sum;

    printf("The matrix elements are:\n");
    srand( time(0) );
    for(i=0; i<3; i++)
    {
        for(j=0; j<3; j++)
        {
            a[i][j] = rand() % 10;
            printf("\t%d", a[i][j]);
        }
        printf("\n");
    }

    for(i=0; i<3; i++)
    {
        sum = 0;
        for(j=0; j<3; j++)
        {
            sum += a[i][j];
        }
        printf("Sum of row %d: %d\n", i+1, sum);
    }

    for(j=0; j<3; j++)
    {
        sum = 0;
        for(i=0; i<3; i++)
        {
            sum += a[i][j];
        }
        printf("Sum of column %d: %d\n", j+1, sum);
    }

    return 0;
}
```

### Task 2
Write a program to find the transpose of a matrix.

```c
#include <stdio.h>
#include <stdlib.h>
#include <time.h>

int main()
{
    int m[3][3];
    int mT[3][3]; /// transpose of m
    int i, j;

    printf("Original matrix:\n");
    srand( time(0) );
    for(i=0; i<3; i++)
    {
        for(j=0; j<3; j++)
        {
            m[i][j] = rand() % 10;
            printf("\t%d", m[i][j]);
        }
        printf("\n");
    }

    printf("\nTranspose matrix:\n");
    for(i=0; i<3; i++)
    {
        for(j=0; j<3; j++)
        {
            mT[i][j] = m[j][i];
            printf("\t%d", mT[i][j]);
        }
        printf("\n");
    }

    return 0;
}
```

