# NEUB CSE-06131114 Fall 2025 Lab 5

## Task 1
Write a program that will declare a n-element integer array where n should be taken as input. Fill the array with integers taken from the user and show the sum and average of the integers. 

_Sample Execution_
```
How many numbers? 3
Enter a[ 0 ]: 25
Enter a[ 1 ]: 26
Enter a[ 2 ]: 32
The sum is: 83. The average is 27.00.

```

## Task 2
Write a program that will declare a 10-element integer array. The array will be filled up by random integers in the range [0, 100]. Use the library functions `rand()` and `srand()` defined in `stdlib.h` to perform the task. After that, determine the maximum element, minimum element and the average of the numbers.

_Sample Execution_
```
The array is:
52 88 17 23 58 36 24 93 15 62
Maximum: 93
Minimum: 15
Average: 46.80
```

## Task 3
Write a program that will read the marks of 40 students in an array and determine the frequency of grades. The marks will be in the range [25, 99].

_Sample Execution_
```
The marks are:
96      44      48      26      62      91      99      30      49      71	    84      41      84      68      28      32      89      38      34      34  	43      45      99      29      47      96      60      93      77      43		 26      54      61      43      93      92      69      60      97      68

GRADE   FREQUENCY
=====   =========
A+      12
A       1
A-      1
B+      3
B       4
B-      0
C+      1
C       4
D       5
F       9
```


## Task 4
Write a program to sort an array of 20 integers using the **_Bubble Sort_** algorithm.

_Sample Execution_
```
Original array is:
62 45 34 88 59 85 33 45 9 34 62 11 36 90 30 65 65 81 39 61

Sorted array is:
9 11 30 33 34 34 36 39 45 45 59 61 62 62 65 65 81 85 88 90
```

## Solution
### Task 1
Write a program that will declare a n-element integer array where n should be taken as input. Fill the array with integers taken from the user and show the sum and average of the integers. 

```c
#include<stdio.h>

int main()
{
	int i, n, sum = 0;
	float average;
	printf("How many numbers? ");
	scanf("%d", &n);
	int a[n];

	for(i=0; i<n; i++)
	{
		printf("Enter a[ %d ]: ", i);
		scanf("%d", &a[i]);
		sum += a[i];
	}
    average= sum/n;
	printf("The sum is: %d. The average is %.2f.\n", sum, average);

	return 0;
}
```

### Task 2
Write a program that will declare a 10-element integer array. The array will be filled up by random integers in the range [0, 100]. Use the library functions `rand()` and `srand()` defined in `stdlib.h` to perform the task. After that, determine the maximum element, minimum element and the average of the numbers.

```c
#include<stdio.h>
#include<stdlib.h> /// rand() and srand() are defined here
#include<time.h>	/// time() is defined here

int main()
{
	int a[10];
	int i, max, min, sum;
	float average;

	srand( time(0) );
	printf("The array is:\n");
	for(i=0; i<10; i++)
	{
		a[i] = rand() % 100;
		printf("%d ", a[i]);
	}
	printf("\n");

	max=min=a[0];
	sum=0;
	for(i=0;i<10;i++){
        (a[i] > max)? max=a[i]:0;
        (a[i] < min)? min=a[i]:0;
        sum+=a[i];
	}

	average = sum / 10.0;
	printf("Maximum: %d\n", max);
	printf("Minimum: %d\n", min);
	printf("Average: %.2f\n", average);

	return 0;
}
```

### Task 3
Write a program that will read the marks of 40 students in an array and determine the frequency of grades. The marks will be in the range [25, 99].

```c
#include <stdio.h>
#include <stdlib.h>
#include <time.h>

int main()
{
	int a[40];
	int grades[10] = {0}; //1st element is of A+, next is A, and so on..
	int i;

	srand( time(0) );
	printf("The marks are:\n");
	for(i=0; i<40; i++)
	{
		a[i] = (rand() % 75) + 25;
		printf("%d\t", a[i]);
	}
	printf("\n");

	for(i=0; i<40; i++)
	{
		if(a[i] >= 80) grades[0]++;
		else if(a[i]>=75) grades[1]++;
		else if(a[i]>=70) grades[2]++;
		else if(a[i]>=65) grades[3]++;
		else if(a[i]>=60) grades[4]++;
		else if(a[i]>=55) grades[5]++;
		else if(a[i]>=50) grades[6]++;
		else if(a[i]>=45) grades[7]++;
		else if(a[i]>=40) grades[8]++;
		else grades[9]++;
	}

	printf("\nThe frequency of grades:\n\n");
	printf("GRADE\tFREQUENCY\n");
	printf("=====\t=========\n");
	printf("A+\t%d\n", grades[0]);
	printf("A \t%d\n", grades[1]);
	printf("A-\t%d\n", grades[2]);
	printf("B+\t%d\n", grades[3]);
	printf("B \t%d\n", grades[4]);
	printf("B-\t%d\n", grades[5]);
	printf("C+\t%d\n", grades[6]);
	printf("C \t%d\n", grades[7]);
	printf("D \t%d\n", grades[8]);
	printf("F \t%d\n", grades[9]);

	return 0;
}
```


### Task 4
Write a program to sort an array of 20 integers using the **_Bubble Sort_** algorithm.

```c
#include <stdio.h>
#include <stdlib.h>
#include <time.h>

#define size 20

int main()
{
	int a[size];
	int i, j, temp;

	srand( time(0) );

	printf("Original array is:\n");
	for(i=0; i<size; i++)
	{
		a[i] = rand() % 100;
		printf("%d ", a[i]);
	}

	/// Bubble sort
	for(i=0; i<size; i++)
	{
		for(j=1; j<size-i; j++)
			if(a[j-1] > a[j])
			{
				temp = a[j-1];
				a[j-1] = a[j];
				a[j] = temp;
			}
	}
	printf("\nThe sorted array is:\n");
	for(i=0; i<size; i++)
		printf("%d ", a[i]);

	return 0;
}
```