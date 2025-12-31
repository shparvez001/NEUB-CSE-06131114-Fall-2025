# NEUB CSE-06131114 Fall 2025 Lab 8

## Task 1
Write a program to implement the following functions:
```
int str_len(char str[]);
```
Returns the length of str. The length of a string is determined by the terminating null-character: A C string is as long as the amount of characters between the beginning of the string and the terminating null character. This should not be confused with the size of the array that holds the string. For example:
`
char mystr[100]="test string"; 
`
defines an array of characters with a size of 100 chars, but the C string with which mystr has been initialized has a length of only 11 characters. Therefore, str_len(mystr) returns 11.
```
void str_cat(char destination[], char source[]);
```
Appends a copy of the source string to the destination string. The terminating null character in destination is overwritten by the first character of source, and a new null-character is appended at the end of the new string formed by the concatenation of both in destination.
```
void str_cpy(char destination[], char source[]);
```
Copies the C string pointed by source into the array pointed by destination, including the terminating null character.
```
int str_cmp(const char s1[], const char s2[]);
```
Compares the C string s1 to the C string s2. This function starts comparing the first character of each string. If they are equal to each other, it continues with the following pairs until the characters differ or until a terminanting null-character is reached.
```
void str_rev(char s[]);
```
Reverses the contents of the array s.


## Task 2

Solve UVA [problem 458](https://onlinejudge.org/index.php?option=com_onlinejudge&Itemid=8&page=show_problem&problem=399). [[PDF](https://onlinejudge.org/external/4/458.pdf)] [[Submission link](https://onlinejudge.org/index.php?option=com_onlinejudge&Itemid=8&page=submit_problem&problemid=399&category=0)] 

## Solution
### Task 1

````c
#include <stdio.h>

int str_len(char str[]);
void str_cat(char dest[], char src[]);
void str_cpy(char dest[], char src[]);
int str_cmp(const char s1[], const char s2[]);
void str_rev(char s[]);

int main()
{
	char str[100] = "test string";
	char s1[50] = "Bangla";
	char s2[50] = "desh";
	int len, comp;

	len = str_len(str);
	printf("Length of str: %d\n", len);

	str_cat(s1, s2);
	printf("s1 after concatenate: %s\n", s1);

	comp = str_cmp(str, s1);
	if(comp == 1) puts("str is greater than s1.");
	else if(comp == -1) puts("s1 is greater than str.");
	else puts("s1 and str are equal");

	printf("s1 before reverse: %s\n", s1);
	str_rev(s1);
	printf("s1 after reverse: %s\n", s1);

	return 0;
}

int str_len(char str[])
{
	int len;
	for(len=0; str[len]; len++);
	return len;
}

void str_cat(char dest[], char src[])
{
	int i, j;

	for(i=0; dest[i]; i++);
	for(j=0; src[j]; j++, i++)
		dest[i] = src[j];
	dest[i] = '\0';
}

void str_cpy(char dest[], char src[])
{
	int i;

	for(i=0; src[i]; i++)
		dest[i] = src[i];
	dest[i] = '\0';
}

int str_cmp(const char s1[], const char s2[])
{
	int i;

	for(i=0; s1[i] || s2[i]; i++)
	{
		if(s1[i] > s2[i]) return 1;
		else if(s1[i] < s2[i]) return -1;
	}
	return 0;
}

void str_rev(char s[])
{
	int i, j;
	char temp;

	for(i=0, j=str_len(s)-1; i<j; i++,j--)
	{
		temp = s[i];
		s[i] = s[j];
		s[j] = temp;
	}
}
````

