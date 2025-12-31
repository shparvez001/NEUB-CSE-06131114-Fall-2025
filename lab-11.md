# NEUB CSE-06131114 Fall 2025 Lab 11

In this week’s lab class, we will create a *“Computerized Telephone Directory”* for the students of CSE department.
At first you have to define a structure called `phone_directory` as:
````
struct phone_directory {
	int id;
	char name[80];
	char number[25];
};
````

After that, you have to declare an array of structure of type `phone_directory`:
````
phone_directory phone[400];
````
Then your program should perform the following activities:
1.	Make a new entry to the telephone directory
2.	Search for a person’s phone number (given student id)
3.	Load the directory from the disk to the array of structure.
4.	Save the directory (array of structure) to the disk.
5.	Exit from the program.

See the sample output below for further clarification:
````
Welcome to Computerized Telephone Directory
-------------------------------------------
1. Enter names and numbers
2. Find numbers
3. Save directory to disk
4. Load directory from disk
5. Quit
Enter your choice: 4

Load complete.


Press any key to continue ...

Welcome to Computerized Telephone Directory
-------------------------------------------
1. Enter names and numbers
2. Find numbers
3. Save directory to disk
4. Load directory from disk
5. Quit
Enter your choice: 2

Enter ID: 33
Name: Aonmoy Sarker
Number: 01775481289

Press any key to continue ...

...(etc.)
````



* A sample phone-book is provided to you (phone.txt).


## Solution
````c
#include <stdio.h>
#include <string.h>
#include <stdlib.h>

#define MAX 400

struct phone_directory {
	int id;
	char name[80];
	char number[25];
} phone[MAX];

int loc=0;

int menu(void);
void enter(void);
void load(void);
void save(void);
void find(void);

int main()
{
	int choice;

	do {
		choice = menu();
		switch(choice) {
			case 1: enter();
			break;
			case 2: find();
			break;
			case 3: save();
			break;
			case 4: load();
		}
		if(choice != 5) {
			printf("\n\nPress any key to continue ...");
			getchar();
		}
	} while(choice!=5);

	return 0;
}

/* Get menu choice. */
int menu(void)
{
	int i;
	char str[80];

	printf("\033c");
	printf("\n\nWelcome to Computerized Telephone Directory\n");
	printf("-------------------------------------------\n");
	printf("1. Enter names and numbers\n");
	printf("2. Find numbers\n");
	printf("3. Save directory to disk\n");
	printf("4. Load directory from disk\n");
	printf("5. Quit\n");

	do {
		printf("Enter your choice: ");
		fgets(str, 80, stdin);
		i = atoi(str);
		printf("\n");
	} while (i<1 || i>5);
	return i;
}

void enter(void)
{
	printf("Enter ID: ");
	scanf("%d", &loc);
	getchar();
	printf("Enter name: ");
	scanf("%[^\n]", phone[loc].name);
	getchar();
	printf("Enter number: ");
	scanf("%[^\n]", phone[loc].number);
	getchar();
}

void find(void)
{
	char temp[80];

	printf("Enter ID: ");
	fgets(temp, 80, stdin);
	loc = atoi(temp);

	printf("Name: %s\nNumber: %s\n", phone[loc].name, phone[loc].number);
}

void load(void)
{
	FILE *fp;

	if((fp = fopen("phone.txt", "r"))==NULL) {
		printf("Cannot open file.\n");
		exit(1);
	}

	while(!feof(fp)) {
		fscanf(fp, "%d", &loc);
		fscanf(fp, "%[^\n]%s", phone[loc].name, phone[loc].number);
	}
	puts("Load complete.");
	fclose(fp);
}

void save(void)
{
	FILE *fp;
	int i;

	if((fp = fopen("phone2.txt", "w"))==NULL) {
		printf("Cannot open file.\n");
		exit(1);
	}

	for(i=0; i<MAX; i++) {
		if(strlen(phone[i].name))
			fprintf(fp, "%d\n%s\n%s\n\n", i, phone[i].name, phone[i].number);
	}
	fclose(fp);
	puts("Save complete.");
}
````
