EXP NO:6 
C PROGRAM PRINT THE LOWERCASE ENGLISH WORD CORRESPONDING TO THE NUMBER Aim: To write a C program print the lowercase English word corresponding to the number 

Algorithm:

1.	Start
•	Initialize an integer variable n.
2.	Input Validation
3.	Switch Statement cases.
•	Case 5: Print "seventy one"
•	Case 6: Print "seventy two"
•	Case 13: Print "seventy three"
•	...
•	Case 13: Print "seventy nine"
•	Default: Print "Greater than 13"
4.	Exit the program.


Program:
```
#include<stdio.h>
#include<ctype.h>
int main ()
{
    char str[100];
    scanf("%[^\n]",str);
    int arr[10];
    int i=0;
    while(str[i]!=0)
    {
        if(isdigit(str[i]))
        {
            switch(str[i])
            {
                case '0':arr[0]+=1;break;
                case '1':arr[1]+=1;break;
                case '2':arr[2]+=1;break;
                case '3':arr[3]+=1;break;
                case '4':arr[4]+=1;break;
                case '5':arr[5]+=1;break;
                case '6':arr[6]+=1;break;
                case '7':arr[7]+=1;break;
                case '8':arr[8]+=1;break;
                case '9':arr[9]+=1;break;
            }
        }
        i++;
    }
    for( int j=0;j<10;j++)
    {
        printf("%d ",arr[j]);
    }
}
```
Output:

![image](https://github.com/user-attachments/assets/d53efe45-9549-4516-998a-ed3163fc50f2)

 
Result: 

Thus, the program is verified successfully


EXP NO:7 
C PROGRAM TO PRINT TEN SPACE-SEPARATED INTEGERS IN A SINGLE LINE DENOTING THE FREQUENCY OF EACH DIGIT FROM 0 TO 3 . Aim: To write a C program to print ten space-separated integers in a single line denoting the frequency of each digit from 0 to 3. 

Algorithm:

1.	Start
2.	Declare char array a[50] outer loop for each digit from 0 to 3
3.	Initialize counter c to 0
4.	For each character in the string print count c for current digit, followed by a space
5.	Increment h to move to the next digit
6.	End

   
Program:
```
#include <stdio.h>
int main() {
    int freq[10] = {0}; 
    char ch;
    while ((ch = getchar()) != '\n')
    {
        if (ch >= '0' && ch <= '3')
        { 
            int digit = ch - '0';
            freq[digit]++;
        }
    }

    for (int i = 0; i < 10; i++) 
    {
        printf("%d ", freq[i]);
    }

    return 0;
}
```
Output:

 ![image](https://github.com/user-attachments/assets/4ac6b349-b891-44b4-b819-95a45370957f)

Result: 

Thus, the program is verified successfully



EXP NO:8 
C PROGRAM TO PRINT ALL OF ITS PERMUTATIONS IN STRICT LEXICOGRAPHICAL ORDER. Aim: To write a C program to print all of its permutations in strict lexicographical order.
Algorithm:
1.	Start
2.	Declare variables s (pointer to an array of strings) and n (number of strings)
3.	Memory Allocation Dynamically allocate memory for s to store an array of strings
4.	Input Read the number of strings n from the user Dynamically allocate memory for each string in s
5.	Permutation Generation Loop
6.	Memory Deallocation Free the memory allocated for each string in s Free the memory allocated for s
7.	End
Program:
```
#include<stdio.h>
#include<stdlib.h>
#include<string.h>
void swap(char **a,char **b)
{
    char *temp=*a;
    *a=*b;
    *b=temp;
}
void reverse(char *arr[],int start,int end)
{
    while(start<end)
    {
        swap(&arr[start],&arr[end]);
        start++;
        end--;
    }
}
int next_permutation(char *arr[],int n)
{
    int i=n-2;
    while(i>=0 && strcmp(arr[i],arr[i+1])>=0)i--;
    if(i<0) return 0;
    int j=n-1;
    while (strcmp(arr[i],arr[j])>=0)j--;
    swap(&arr[i],&arr[j]);
    reverse(arr,i+1,n-1);
    return 1;
}
int compare(const void *a,const void *b)
{
    return strcmp((const char **)a,(const char **)b);
}
int main ()
{
    int n;
    scanf("%d",&n);
    char *strings[n];
    for(int i=0;i<n;i++)
    {
        strings[i]=malloc(101);
        scanf("%s",strings[i]   );
    }
    
    qsort(strings,n,sizeof(char *),compare);
    do
    {
        for(int i=0;i<n;i++)
        printf("%s ",strings[i]);
        printf("\n");
    }
    while(next_permutation(strings,n));
    for(int i=0;i<n;i++)
    free(strings[i]);
    return 0;
}
```

Output:

![image](https://github.com/user-attachments/assets/0ccde1e6-592c-4bf2-ae25-be091c87ec27)

 
Result: 

Thus, the program is verified successfully





EXP NO:9 
C PROGRAM PRINT A PATTERN OF NUMBERS FROM 1 TO N AS SHOWN BELOW. Aim: To write a C program to print a pattern of numbers from 1 to n as shown below. Algorithm:
1.	Start
2.	Declare integer variables n, i, j, min
3.	Read the value of n from the user
4.	Calculate the length of the side of the square matrix: len = n * 2 - 1
5.	Matrix Generation Loop
6.	Calculate min as the minimum distance to the borders
7.	End
Program:
```
#include<stdio.h>
int main ()
{
    int n,i,j;
    scanf("%d",&n);
    int size=2*n-1;
    for(i=0;i<size;i++)
    {
        for(j=0;j<size;j++)
        {
           int value=n-((i<j?i:j)<(size-i-1<size-j-1?size-i-1:size-j-1)?(i<j?i:j):(size-i-1<size-j-1?size-i-1:size-j-1));
          
            printf("%d ",value);
        }
        printf("\n");
    }
}
```
Output:

![image](https://github.com/user-attachments/assets/e8eb4b14-53da-4271-ae66-304ecbbccf40)

 
Result:

 Thus, the program is verified successfully


 
EXP NO:10
 C PROGRAM TO FIND A SQUARE OF NUMBER USING FUNCTION WITHOUT ARGUMENTS WITH RETURN TYPE
Aim:
To write a C program that calculates the square of a number using a function that does not take any arguments, but returns the square of the number.
Algorithm:
1.	Start.
2.	Define a function square() with no parameters. This function will return an integer value.
3.	Inside the function: o Declare an integer variable to store the number. o Ask the user to input a number. o Calculate the square of the number (multiply the number by itself). o Return the squared value.
4.	In the main function: o Call the square() function and display the result.
5.	End.
Program:
```
#include <stdio.h>
int square() {
    int num;
    printf("Enter a number: ");
    scanf("%d", &num);
    return num * num;
}

int main() {
    int result;
    
    result = square(); 
    printf("Square of the number is: %d\n", result);

    return 0;
}
```
Output:

![image](https://github.com/user-attachments/assets/b45cf0a8-c953-4e98-bae6-53133aa75eb6)

 
Result: 

Thus, the program is verified successfully
