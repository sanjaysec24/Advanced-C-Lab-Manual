EXP NO:21
 C PROGRAM TO CREATE A FUNCTION TO FIND THE GREATEST NUMBER 
Aim: To write a C program to create a function to find the greatest number
Algorithm:
1.	Include the necessary header #include <stdio.h>.
2.	Use a series of if and else if statements to compare the values and return the maximum among them.
3.	Declare variables n1, n2, n3, n4, and greater to store user input and the result.
4.	Use scanf to take four integers as input.
5.	Call the max_of_four function with the input integers and store the result in the greater variable
Program:

#include<stdio.h>
int max_of_four(int a,int b,int c,int d)
{
    if(a>b && a>c &&a>d)return a;
    else if(b>a &&b>c && b>d)return b;
    else if(c>a &&c>b && c>d)return c;
    else return d;
}
int main ()
{
    int a,b,c,d;
    scanf("%d %d %d %d",&a,&b,&c,&d);
    int max=max_of_four(a,b,c,d);
    printf("%d",max);
}

Output

![image](https://github.com/user-attachments/assets/ef931ffd-bf48-4b68-a973-7972313fd7c5)

 
Result: 
Thus, the program that create a function to find the greatest number is verified successfully.

EXP NO:22 
C PROGRAM TO PRINT THE MAXIMUM VALUES FOR THE AND, OR AND XOR COMPARISONS 
Aim: To write a C program to print the maximum values for the AND, OR and XOR comparisons
Algorithm:
1.	Define a function calculate_the_max that takes two integers n and k as parameters.
2.	Declare variables a, o, and x to store the maximum values for AND, OR, and XOR operations, respectively.
3.	Use nested loops to iterate through pairs of integers (i, j) from 1 to n.
4.	Within the loops, check conditions for AND, OR, and XOR operations and update the corresponding maximum values (a, o, x).
5.	Declare variables n and k to store user input.
6.	Use scanf to take two integers as input.
7.	Call the calculate_the_max function with input values.
Program:

#include<stdio.h>
int main()
{
    int n,k;
    scanf("%d %d",&n,&k);
    int max_and=0;
    int max_or=0;
    int max_xor=0;
    for(int i=1;i<n;i++)
    {
        for(int j=i+1;j<=n;j++)
        {
            int reand=i&j;
            int reor=i|j;
            int rexor=i^j;
            if(reand<k)
            {
                if(reand>max_and)
                {
                    max_and=reand;
                }
            }
            if(reor<k)
            {
                if(reor>max_or)
                {
                    max_or=reor;
                }
            }
            if(rexor<k)
            {
                if(rexor>max_xor)
                {
                    max_xor=rexor;
                }
            }
        }
    }
    printf("%d \n",max_and);
    printf("%d\n",max_or);
    printf("%d",max_xor);
}

Output: 

 ![image](https://github.com/user-attachments/assets/2cd7bbab-8c01-483a-b899-0b368b864338)

Result:
 Thus, the program to print the maximum values for the AND, OR and XOR comparisons is verified successfully.

EXP NO:23 
C PROGRAM TO WRITE THE LOGIC FOR THE REQUESTS 
Aim: To write a C program to write the logic for the requests
Algorithm:
1.	Declare variables noshel and noque to store the number of shelves and the number of queries, respectively.
2.	Use scanf to take two integers as input for the number of shelves and queries.
3.	Declare a 2D array shelarr to represent shelves and books, and an array nobookarr to store the number of books on each shelf.
4.	Declare variables k and c to keep track of the book index and the total number of books.
5.	Use a for loop to iterate over the queries.
Program:

#include <stdio.h>
#include <stdlib.h>

int main() {
    int n, q;
    scanf("%d", &n);
    scanf("%d", &q);
    int** shelves = (int*)malloc(n * sizeof(int));
    int* book_counts = (int*)calloc(n, sizeof(int)); 
    for (int i = 0; i < n; i++) {
        shelves[i] = NULL; 
    }
    for (int i = 0; i < q; i++) {
        int type;
        scanf("%d", &type);
        if (type == 1) {
            int x, y;
            scanf("%d %d", &x, &y);
            book_counts[x]++;
            shelves[x] = (int*)realloc(shelves[x], book_counts[x] * sizeof(int));
            shelves[x][book_counts[x] - 1] = y;
        } 
        else if (type == 2) {
            int x, y;
            scanf("%d %d", &x, &y);
            printf("%d\n", shelves[x][y]);
        } 
        else if (type == 3) {
            int x;
            scanf("%d", &x);
            printf("%d\n", book_counts[x]);
        }
    }
    
    for (int i = 0; i < n; i++) {
        free(shelves[i]);
    }
    free(shelves);
    free(book_counts);
    
    return 0;
}

Output:

 ![image](https://github.com/user-attachments/assets/5fb0b684-71c5-4715-aeb7-69c8b9829c3a)

Result:

 Thus, the program to write the logic for the requests is verified successfully.

EXP NO:24 
C PROGRAM PRINT THE SUM OF THE INTEGERS IN THE ARRAY.
 Aim: To write a C program print the sum of the integers in the array.
Algorithm:
1.	Declare a variable n to store the number of integers.
2.	Use scanf to take an integer n as input.
3.	Declare an array a of size n to store the integers.
4.	Declare a variable sum and initialize it to zero.
5.	Use a for loop to iterate n times:
6.	Use scanf to input each integer and add it to the sum.
7.	Print the final sum using printf.
Program:

#include<stdio.h>
int main ()
{
    int n;
    scanf("%d",&n);
    int arr[n];
    int sum=0;
    for(int i=0;i<n;i++)
    {
        scanf("%d",&arr[i]);
        sum=sum+arr[i];
    }
    printf("%d",sum);
}

Output: 

 ![image](https://github.com/user-attachments/assets/dc8caef2-2be2-4ff0-b6b0-c89ff38cc1ce)

Result: 

Thus, the program prints the sum of the integers in the array is verified successfully.

EXP NO 25: 
C PROGRAM TO COUNT THE NUMBER OF WORDS IN A SENTENCE
Aim:
To write a C program that counts the number of words in a given sentence.
Algorithm:
1.	Input the sentence: Take a sentence from the user.
2.	Initialize a counter variable: This will keep track of the number of words.
3.	Process each character of the sentence: o Iterate through the sentence, checking each character. o If a character is not a space, it may belong to a word. If it's the first non-space character after a space or at the start, increment the word count.
4.	Handle spaces and punctuation: Skip over spaces, punctuation marks, and consider each word as a sequence of characters separated by spaces.
5.	Display the result: After processing the sentence, output the total word count.
Program:

#include <stdio.h>
#include <ctype.h>

int main()
{
    char sentence[1000];
    int i = 0, words = 0, inWord = 0;

    printf("Enter a sentence: ");
    fgets(sentence, sizeof(sentence), stdin);

    while (sentence[i] != '\0') 
    {
        if (isspace(sentence[i])) 
        {
            inWord = 0;
        } else if (inWord == 0) 
        {
            inWord = 1;
            words++;
        }
        i++;
    }

    printf("Number of words: %d\n", words);

    return 0;
}

Output: 

 ![image](https://github.com/user-attachments/assets/efc7a3d8-f00b-4164-87fc-a315f75ba918)

Result:
Thus, the program that counts the number of words in a given sentence is verified successfully.
