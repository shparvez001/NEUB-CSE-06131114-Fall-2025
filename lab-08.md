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




