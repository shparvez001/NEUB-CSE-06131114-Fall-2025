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



