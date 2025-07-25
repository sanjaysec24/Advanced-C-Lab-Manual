EXP NO:1 C PROGRAM FOR ARRAY OF STRUCTURE TO CHECK ELIGIBILITY FOR THE VACCINE.

Aim:
To write a C program for array of structure to check eligibility for the vaccine person age above 6 years of age.

Algorithm:
1.	Declare structure eligible with age (integer) and n (character array)
2.	Declare variable e of type eligible
3.	Input age and name using scanf, store in e
4.	If e.age <= 6
-	Print "Vaccine Eligibility: No"
Else
-	Print "Vaccine Eligibility: Yes"
5.	Print details (e.age, e.n)
6.	Return 0
 
Program:
```
#include <stdio.h>
struct Person
{
    char name[50];
    int age;
};
void checkEligibility(struct Person people[], int n) 
{
    printf("\n--- Vaccine Eligibility ---\n");
    for (int i = 0; i < n; i++)
    {
        printf("Name: %s\n", people[i].name);
        printf("Age: %d\n", people[i].age);
        if (people[i].age >= 6) 
        {
            printf("Status: Eligible for vaccine.\n");
        }
        else
        {
            printf("Status: Not eligible for vaccine.\n");
        }
        printf("---------------------------\n");
    }
}

int main() 
{
    struct Person people[100];
    int n;
    printf("Enter number of people: ");
    scanf("%d", &n);
    for (int i = 0; i < n; i++) 
    {
        printf("\nEnter details for person %d:\n", i + 1);
        printf("Name: ");
        scanf(" %[^\n]", people[i].name);  
        printf("Age: ");
        scanf("%d", &people[i].age);
    }
    checkEligibility(people, n);

    return 0;
```
Output:


![image](https://github.com/user-attachments/assets/b5c020ce-5649-4075-973a-d44f2480463c)

Result:


Thus, the program is verified successfully. 



EXP NO:2 C PROGRAM FOR PASSING STRUCTURES AS FUNCTION ARGUMENTS AND RETURNING A STRUCTURE FROM A FUNCTION
Aim:
To write a C program for passing structure as function and returning a structure from a function

Algorithm:
1.	Define structure numbers with members a and b.
2.	Declare variable n of type numbers.
3.	Prompt the user to enter values for a and b.
4.	Input values for a and b into n using scanf.
5.	Call the add function with n as an argument.
6.	Print the result returned by the add function.
7.	Return 0
 
Program:
```
#include<stdio.h>
struct number
{
    int num1;
    int num2;
};
struct result
{
    int add;
};
struct result process(struct number num)
{
    struct result res;
    res.add=num.num1+num.num2;
    return res;    
};
int main()
{
  struct number num;
  scanf("%d %d ",&num.num1,&num.num2);
  struct result result;
  result=process(num);
  printf("%d",result.add);
  return 0;
}
```
Output:

![image](https://github.com/user-attachments/assets/f4be3a7a-fe8b-442b-b4da-25dce990bc90)

Result:


Thus, the program is verified successfully


 
EXP.NO:3 C PROGRAM TO READ A FILE NAME FROM USER AND WRITE THAT FILE USING FOPEN()

Aim:
To write a C program to read a file name from user

Algorithm:
1.	Include the necessary header file stdio.h.
2.	Begin the main function.
3.	Declare a file pointer p.
Declare a character array name to store the file name.
4.	Prompt the user to enter a file name.
Use scanf to input the file name into the name array.
5.	Print a message indicating that the file with the specified name has been created successfully.
6.	Use fopen to open a file with the name provided by the user in write mode ("w").
-	If successful, continue to the next step.
-	If unsuccessful, print an error message and exit the program with a non-zero status.
1.	Print a message indicating that the file has been opened successfully.
2.	Use fclose to close the file.
3.	Print a message indicating that the file has been closed.
4.	End the main function.
5.	Return 0 to indicate successful program execution.
 
Program:
```
#include <stdio.h>
int main ()
{
    char str[50];
    scanf("%s",str);
    FILE *ptr;
    ptr=fopen(str,"w");
    printf("%s File Created Successfully\n",str);
    if(ptr!=NULL)
    {
        printf("%s File Opened\n",str);
    }
    fclose(ptr);
    printf("%s File Closed",str);
}
```
Output:


![image](https://github.com/user-attachments/assets/5ec9d0ca-5439-4482-a73e-2d8caec59000)


Result:

Thus, the program is verified successfully
 


EXP NO:4   PROGRAM TO READ A FILE NAME FROM USER, WRITE THAT FILE AND INSERT TEXT IN TO THAT FILE
Aim:
To write a C program to read, a file and insert text in that file
Algorithm:
1.	Include the necessary header file stdio.h.
2.	Begin the main function.
3.	Declare a file pointer p.
Declare character arrays name and text. Declare an integer variable num.
4.	Prompt the user to enter a file name and the number of strings.
Use scanf to input the file name into the name array and the number of strings into the num variable.
5.	Use fopen to open a file with the name provided by the user in write mode ("w").
-	If successful, continue to the next step.
-	If unsuccessful, print an error message and exit the program with a non-zero status.
6.	Print a message indicating that the file has been opened successfully.
1.	Use a loop to input strings from the user and write them to the file using fputs.
2.	Use fclose to close the file.
3.	Print a message indicating that data has been added successfully.
4.	End the main function.
5.	Return 0 to indicate successful program execution.
 
Program:
```
#include <stdio.h>
int main ()
{
    char str[50];
    scanf("%s",str);
    FILE *ptr;
    ptr=fopen(str,"w");
    printf("%s Opened\n",str);
    int a;
    float b;
    scanf("%d",&a);
    for(int i=0;i<b;i++)
    {
        scanf("%f",&b);
    }
    printf("Data added Successfully\n");
    fclose(ptr);
}

```
Output:


![image](https://github.com/user-attachments/assets/894782cb-f65d-462f-987d-708ee68b6bf2)


Result:

Thus, the program is verified successfully



Ex No 5 : C PROGRAM TO DISPLAY STUDENT DETAILS USING STRUCTURE

Aim:
The aim of this program is to dynamically allocate memory to store information about multiple subjects (name and marks), input the details for each subject, and then display the stored information. Finally, it frees the allocated memory to prevent memory leaks.

Algorithm:
1.Input the number of subjects.

2.Read the integer value n from the user, which represents the number of subjects.

3.Dynamically allocate memory:

4.Use malloc to allocate memory for n subjects. Each subject has a name (array of characters) and marks (integer).

5.If memory allocation fails (i.e., the pointer s is NULL), display an error message and exit the program.

6.Input the details of each subject

7.Use a for loop to read the name and marks of each subject using scanf. For each subject, store the name as a string and marks as an integer in the dynamically allocated memory.

8.Display the details of each subject

9.Use another for loop to print the name and marks of each subject.

10.Free the allocated memory

11.After all operations are done, call free(s) to release the dynamically allocated memory.

12.Return from the main function

13.End the program by returning 0.

Program:
```
#include <stdio.h>
#include <stdlib.h>
struct Subject 
{
    char name[50];
    int marks;
};
int main() 
{
    int n, i;
    struct Subject *s;
    printf("Enter the number of subjects: ");
    scanf("%d", &n);
    s = (struct Subject *)malloc(n * sizeof(struct Subject));
    if (s == NULL) 
    {
        printf("Memory allocation failed.\n");
        return 1; 
    }
    for (i = 0; i < n; i++)
    {
        printf("\nEnter details for subject %d:\n", i + 1);
        printf("Subject Name: ");
        scanf(" %[^\n]", s[i].name); 
        printf("Marks: ");
        scanf("%d", &s[i].marks);
    }
    printf("\n--- Subject Details ---\n");
    for (i = 0; i < n; i++) {
        printf("Subject %d: %s - %d marks\n", i + 1, s[i].name, s[i].marks);
    }
    free(s);
    return 0;
}

```
Output:

![image](https://github.com/user-attachments/assets/70d97d72-b281-4ad8-b369-c7059080c4c2)


Result:

Thus, the program is verified successfully
