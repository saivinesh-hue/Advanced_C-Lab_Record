# 19AI305 - Advanced C Programming - ODD - 2026

# IAPR - Module 08

# EXP.01 :  C PROGRAM PRINT THE LOWERCASE ENGLISH WORD CORRESPONDING TO THE NUMBER TO A GIVEN NUMBER USING SWITCH-CASE STATEMENT

## Aim:

To write a C program to print the lowercase English word corresponding to a given number using a switch-case statement.

## Algorithm:

1. Start
2. Variable Declaration: Initialize an integer variable n.
3. Input Validation: Read the integer value n from the user.
4. Switch Statement: Match n against the following cases:
- Case 1: Print "one"
- Case 2: Print "two"
- Case 3: Print "three"
- Case 4: Print "four"
- Case 5: Print "five"
- Case 6: Print "six"
- Case 7: Print "seven"
- Case 8: Print "eight"
- Case 9: Print "nine"
- Default: Print "Greater than 9"
5. Exit the program.
 
## Program:

```c
#include <stdio.h>

int main() {
    int n;

    if (scanf("%d", &n) != 1) {
        return 1;
    }

    switch (n) {
        case 1:
            printf("one\n");
            break;
        case 2:
            printf("two\n");
            break;
        case 3:
            printf("three\n");
            break;
        case 4:
            printf("four\n");
            break;
        case 5:
            printf("five\n");
            break;
        case 6:
            printf("six\n");
            break;
        case 7:
            printf("seven\n");
            break;
        case 8:
            printf("eight\n");
            break;
        case 9:
            printf("nine\n");
            break;
        default:
            printf("Greater than 9\n");
            break;
    }

    return 0;
}
```

## Output:

<img width="661" height="121" alt="image" src="https://github.com/user-attachments/assets/4edc7e56-601e-47bf-9f60-6e2b5b2ad424" />

## Result:

Thus, the C program to print the lowercase English word corresponding to a given number using a switch-case statement is verified successfully

***
 
# EXP.02  : C PROGRAM TO PRINT TEN SPACE-SEPARATED INTEGERS IN A SINGLE LINE DENOTING THE FREQUENCY OF EACH DIGIT FROM 0 TO 9 

## Aim:

To write a C program to print ten space-separated integers in a single line denoting the frequency of each digit from 0 to 9.

## Algorithm:

1.	Start
2.	Declare char array a[50] outer loop for each digit from 0 to 9
3.	Initialize counter c to 0
4.	For each character in the string print count c for current digit, followed by a space
5.	Increment h to move to the next digit
6.	End
 
## Program:

```C
#include <stdio.h>
int main()
{
    int c[10]={0},ch;
    while((ch=getchar())!='\n' && ch != EOF) if(ch>='0' && ch<='9') c[ch-'0']++;
    for(int i=0;i<10;i++) printf("%d ",c[i]);
    return 0;
}
```

## Output:

<img width="660" height="105" alt="image" src="https://github.com/user-attachments/assets/14573bcf-1a08-465b-9d75-fd8ccfd305e7" />

## Result:

Thus, the C program to print ten space-separated integers in a single line denoting the frequency of each digit from 0 to 9 is verified successfully

***

# EXP.03 : C PROGRAM TO PRINT ALL OF ITS PERMUTATIONS IN STRICT LEXICOGRAPHICAL ORDER

## Aim:

To write a C program to print all of its permutations in strict lexicographical order.

## Algorithm:

1.	Start
2.	Declare variables s (pointer to an array of strings) and n (number of strings)
3.	Memory Allocation
Dynamically allocate memory for s to store an array of strings
4.	Input : Read the number of strings n from the user Dynamically allocate memory for each string in s
5.	Permutation Generation Loop
6.	Memory Deallocation
Free the memory allocated for each string in s Free the memory allocated for s
7.	End
 
## Program:

```c
#include <stdio.h>
#include <stdlib.h>

int next_per(int n, char **s){
    int strcmp(const char*, const char*);
    int i = n-2, j = n-1;
    while(i>=0 && strcmp(s[i],s[i+1]) >=0) i--;
    if(i<0) return 0;
    while(strcmp(s[i],s[j])>=0) j--;
    char *t = s[i]; s[i]=s[j]; s[j] = t;
    for(int a=i+1,b=n-1;a<b;a++,b--) t=s[a],s[a]=s[b],s[b]=t;
    return 1;
}

int main()
{
    int n;
    printf("Enter the Number of Strings: ");
    if(scanf("%d",&n)!=1) return 0;

    char **s = malloc(n*sizeof(char*));

    printf("\nEnter the Strings: \n");
    for(int i=0;i<n;i++){
        s[i] = malloc(11*sizeof(char));
        scanf("%s",s[i]);
    }

    printf("\nThe Lexicological Oredr:\n");
    do{
        for(int i = 0; i<n ; i++){
            printf("%s%c",s[i],(i==n-1)?'\n':' ');
        }
    }while(next_per(n,s));

    for(int i=0;i<n;i++) free(s[i]);
    free(s);
    return 0;
}
```

## Output:

<img width="672" height="347" alt="image" src="https://github.com/user-attachments/assets/817391d7-4a40-42fe-8bd1-f9c3c9b141c0" />

## Result:

Thus, the C program to print all of its permutations in strict lexicographical order is verified successfully.

***
 
# EXP.04 : C PROGRAM PRINT A PATTERN OF NUMBERS FROM 1 TO N

## Aim:

To write a C program to print a pattern of numbers from 1 to n given below:


<img width="150" height="265" alt="image" src="https://github.com/user-attachments/assets/73c1f0bd-a7e5-4438-87ed-043e4083f683" />


## Algorithm:

1.	Start
2.	Declare integer variables n, i, j, min
3.	Read the value of n from the user
4.	Calculate the length of the side of the square matrix: len = n * 2 - 1
5.	Matrix Generation Loop
6.	Calculate min as the minimum distance to the borders
7.	End
 
## Program:

```c
#include <stdio.h>
int main()
{
    int n,m;
    printf("Enter the Value of N: ");
    scanf("%d",&n);
    m = 2*n - 1;
    printf("\nThe Pattern: \n");
    for(int i=0;i<m;i++){
        for(int j=0;j<m;j++){
            int a = i < m-i ? i : m-1-i;
            int b = j < m-j ? j : m-1-j;
            printf("%d ",n-(a<b ? a : b));
        }
        printf("\n");
    }
    return 0;
}
```

## Output:

<img width="652" height="313" alt="image" src="https://github.com/user-attachments/assets/3128b6a5-1465-41e6-9935-a3f431bff201" />

## Result:

Thus, the C program to print a given pattern of numbers from 1 to n is verified successfully.

***

# EXP.05 : C PROGRAM TO FIND A SQUARE OF NUMBER USING FUNCTION WITHOUT ARGUMENTS WITH RETURN TYPE

## Aim:

To write a C program that calculates the square of a number using a function that does not take any arguments, but returns the square of the number.

## Algorithm:

1.	Start.
2.	Define a function square() with no parameters. This function will return an integer value.
3.	Inside the function:
o	Declare an integer variable to store the number.
o	Ask the user to input a number.
o	Calculate the square of the number (multiply the number by itself).
o	Return the squared value.
4.	In the main function:
o	Call the square() function and display the result.
5.	End.

## Program:

```c
#include <stdio.h>

int square() {
    int num;
    printf("Enter a number: ");
    scanf("%d", &num);
    return num * num;
}

int main() {
    int result = square();
    printf("Square of the number is: %d\n", result);
    return 0;
}
```

## Output:

<img width="643" height="126" alt="Screenshot 2026-09-13 115658" src="https://github.com/user-attachments/assets/393c3ff8-e6d7-4276-94c2-85bce440bed9" />


## Result:

Thus, the C program that calculates the square of a number using a function that does not take any arguments, but returns the square of the number is verified successfully.
