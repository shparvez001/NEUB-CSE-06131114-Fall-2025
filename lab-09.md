# NEUB CSE-06131114 Fall 2025 Lab 9

## Task 1
Write a function `swap(int *x, int *y)` that swaps two integers.
_Sample Execution_
```
Before swap: a = 5, b = 10
After swap: a = 10, b = 5
```


## Task 2
Declare an integer array with 5 elements and use a pointer to print and sum the array elements.
_Sample Execution_
```
arr[0] = 10    arr[1] = 20    arr[2] = 30    arr[3] = 40    arr[4] = 50
Sum = 150
```

## Task 3
Write a program that does the following things
1. Ask user for n (number of integers).
2. Allocate memory dynamically using malloc().
3.	Input and display values using pointers.
4.	Free the memory.


_Sample Execution_
```
Enter number of elements: 5
Enter 5 integers:
2 5 6 7 9
You entered: 2 5 6 7 9
```

## Task 4
Write a program to input a string and copy it into another string manually using pointers. Print both strings.
_Sample Execution_
```
Enter a string: Hello This is a Test
Copied string: Hello This is a Test
```

## Solution
### Task 1
Write a function `swap(int *x, int *y)` that swaps two integers.

```c
#include <stdio.h>
void swap(int *x, int *y) {
    int temp = *x;
    *x = *y;
    *y = temp;
}

int main() {
    int a = 5, b = 10;
    printf("Before swap: a = %d, b = %d\n", a, b);
    swap(&a, &b);
    printf("After swap: a = %d, b = %d\n", a, b);
}
```


### Task 2
Declare an integer array with 5 elements and use a pointer to print and sum the array elements.

```c
#include <stdio.h>
int main() {
    int arr[5] = {10, 20, 30, 40, 50};
    int *p = arr;
    int sum = 0;

    for (int i = 0; i < 5; i++) {
        printf("arr[%d] = %d\t", i, *(p + i));
        sum += *(p + i);
    }
    printf("\nSum = %d\n", sum);
}
```

### Task 3
Write a program that does the following things
1. Ask user for n (number of integers).
2. Allocate memory dynamically using malloc().
3.	Input and display values using pointers.
4.	Free the memory.


```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    int n;
    printf("Enter number of elements: ");
    scanf("%d", &n);

    int *p = (int*) malloc(n * sizeof(int));
    if (p == NULL) {
        printf("Memory not allocated\n");
        return 1;
    }

    printf("Enter %d integers:\n", n);
    for (int i = 0; i < n; i++)
        scanf("%d", p + i);

    printf("You entered: ");
    for (int i = 0; i < n; i++)
        printf("%d ", *(p + i));

    free(p);
}
```

### Task 4
Write a program to input a string and copy it into another string manually using pointers. Print both strings.

```c
#include <stdio.h>
int main() {
    char str1[50], str2[50];
    char *p1 = str1, *p2 = str2;

    printf("Enter a string: ");
    gets(str1);

    while (*p1 != '\0') {
        *p2 = *p1;
        p1++;
        p2++;
    }
    *p2 = '\0';

    printf("Copied string: %s\n", str2);
}
```