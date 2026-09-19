# 19AI305 - Advanced C Programming - ODD - 2026

# IAPR - Module 11

# EXP.01 : C PROGRAM TO CREATE A FUNCTION TO FIND THE GREATEST NUMBER

## Aim:

To write a C program to create a function to find the greatest number.

## Algorithm:

1.	Include the necessary header #include <stdio.h>.
2.	Use a series of if and else if statements to compare the values and return the maximum among them.
3.	Declare variables n1, n2, n3, n4, and greater to store user input and the result.
4.	Use scanf to take four integers as input.
5.	Call the max_of_four function with the input integers and store the result in the greater variable
 
## Program:

```c
#include <stdio.h>

int max_of_four(int a, int b, int c, int d){
    int max = a;
    if(max<b) max=b;
    if(max<c) max=c;
    if(max<d) max=d;
    return max;
}
int main()
{
    int a,b,c,d;
    if(scanf("%d\n%d\n%d\n%d",&a,&b,&c,&d)==4) printf("%d",max_of_four(a,b,c,d));
    return 0;
}
```

## Output:

<img width="315" height="292" alt="image" src="https://github.com/user-attachments/assets/8252a30c-c316-4bb8-ab0e-a7eeda470e8e" />

## Result:

Thus, the C program that create a function to find the greatest number is verified successfully.

***
 
# EXP.02 : C PROGRAM TO PRINT THE MAXIMUM VALUES FOR THE AND, OR AND  XOR COMPARISONS

## Aim:

To write a C program to print the maximum values for the AND, OR and XOR comparisons

## Algorithm:

1.	Define a function calculate_the_max that takes two integers n and k as parameters.
2.	Declare variables a, o, and x to store the maximum values for AND, OR, and XOR operations, respectively.
3.	Use nested loops to iterate through pairs of integers (i, j) from 1 to n.
4.	Within the loops, check conditions for AND, OR, and XOR operations and update the corresponding maximum values (a, o, x).
5.	Declare variables n and k to store user input.
6.	Use scanf to take two integers as input.
7.	Call the calculate_the_max function with input values.
 
##  Program:

```c
#include <stdio.h>

void cal_max(int n, int k){
    int max_and = 0, max_or = 0, max_xor = 0;
    for(int a=1;a<n;a++){
        for(int b=a+1;b<=n;b++){
            int cur_and = a&b;
            int cur_or = a|b;
            int cur_xor = a^b;
            
            if(cur_and < k && cur_and > max_and) max_and = cur_and;
            if(cur_or < k && cur_or > max_or) max_or = cur_or;
            if(cur_xor < k && cur_xor > max_xor) max_xor = cur_xor;
        }
    }
    printf("%d\n%d\n%d",max_and,max_or,max_xor);
}

int main()
{
    int a,b;
    scanf("%d %d",&a,&b);
    cal_max(a,b);
    return 0;
}
```

## Output:

<img width="318" height="333" alt="image" src="https://github.com/user-attachments/assets/542591e6-df42-4b7c-bdd9-9fffd1259362" />

## Result:

Thus, the C program to print the maximum values for the AND, OR and XOR comparisons is verified successfully.

***

# EXP.03 : C PROGRAM TO WRITE THE LOGIC FOR THE REQUESTS

## Aim:

To write a C program to write the logic for the requests.

## Algorithm:

1.	Declare variables noshel and noque to store the number of shelves and the number of queries, respectively.
2.	Use scanf to take two integers as input for the number of shelves and queries.
3.	Declare a 2D array shelarr to represent shelves and books, and an array nobookarr to store the number of books on each shelf.
4.	Declare variables k and c to keep track of the book index and the total number of books.
5.	Use a for loop to iterate over the queries.
 
## Program:

```c
#include <stdio.h>
#include <stdlib.h>

int* tot_num_books;
int** tot_num_pages;

int main()
{
    int tot_num_shelves;
    if(scanf("%d",&tot_num_shelves)!=1) return 1;
    
    int tot_num_queries;
    if(scanf("%d",&tot_num_queries)!=1) return 1;
    
    tot_num_books = (int*)calloc(tot_num_shelves,sizeof(int));
    tot_num_pages = (int**)calloc(tot_num_shelves,sizeof(int*)); 
    
    for(int i=0;i<tot_num_shelves;i++) tot_num_pages[i] = NULL;
    
    while(tot_num_queries--){
        int type_of_query;
        if(scanf("%d",&type_of_query)!=1) break;
        
        if(type_of_query == 1){
            int x,y;
            if(scanf("%d %d",&x,&y) != 2) break;
            
            tot_num_books[x]++;
            tot_num_pages[x] = (int*)realloc(tot_num_pages[x],tot_num_books[x]*sizeof(int));
            tot_num_pages[x][tot_num_books[x]-1] = y;
        }
        else if(type_of_query == 2){
            int x,y;
            if(scanf("%d %d",&x,&y) != 2) break;
            printf("%d\n",tot_num_pages[x][y]);
        }
        else{
            int x;
            if(scanf("%d",&x) != 1) break;
            printf("%d\n",tot_num_books[x]);
        }
    }
    
    if(tot_num_books){
        free(tot_num_books);
    }
    
    for(int i=0;i<tot_num_shelves;i++){
        if(tot_num_pages[i]){
            free(tot_num_pages[i]);
        }
    }
    
    if(tot_num_pages) free(tot_num_pages);
    
    return 0;
}
```

## Output:

<img width="325" height="202" alt="image" src="https://github.com/user-attachments/assets/8b1e5e84-8a7d-466b-b898-5c9d1a0e9553" />

## Result:

Thus, the C program to write the logic for the requests is verified successfully.

***
 
# EXP.04 : C PROGRAM PRINT THE SUM OF THE INTEGERS IN THE ARRAY.

## Aim:

To write a C program print the sum of the integers in the array.

## Algorithm:

1.	Declare a variable n to store the number of integers.
2.	Use scanf to take an integer n as input.
3.	Declare an array a of size n to store the integers.
4.	Declare a variable sum and initialize it to zero.
5.	Use a for loop to iterate n times:
6.	Use scanf to input each integer and add it to the sum.
7.	Print the final sum using printf.

## Program:

```c
#include <stdio.h>
#include <stdlib.h>
int main()
{
    int n,sum = 0;
    scanf("%d",&n);
    int *a = (int*)malloc(n*sizeof(int));
    for(int i=0;i<n;i++){
        scanf("%d",&a[i]);
        sum+=a[i];
    }
    printf("%d",sum);
    return 0;
}
```

## Output:

<img width="465" height="195" alt="image" src="https://github.com/user-attachments/assets/80d6a236-a7ac-46e5-bd9f-ba76cc855641" />

## Result:

Thus, the C program prints the sum of the integers in the array is verified successfully.

***
 
# EXP.05 : C PROGRAM TO COUNT THE NUMBER OF WORDS IN A SENTENCE

## Aim:

To write a C program that counts the number of words in a given sentence.

## Algorithm:

1.	Input the sentence: Take a sentence from the user.
2.	Initialize a counter variable: This will keep track of the number of words.
3.	Process each character of the sentence:
o	Iterate through the sentence, checking each character.
o	If a character is not a space, it may belong to a word. If it's the first non-space character after a space or at the start, increment the word count.
4.	Handle spaces and punctuation: Skip over spaces, punctuation marks, and consider each word as a sequence of characters separated by spaces.
5.	Display the result: After processing the sentence, output the total word count.

## Program:

```c
#include <stdio.h>
#include <ctype.h>

int main() {
    char str[1000];
    int count = 0, in_word = 0;

    if (fgets(str, sizeof(str), stdin) == NULL) {
        return 0;
    }

    for (int i = 0; str[i] != '\0'; i++) {
        if (!isspace((unsigned char)str[i]) && !ispunct((unsigned char)str[i])) {
            if (!in_word) {
                count++;
                in_word = 1;
            }
        } else {
            in_word = 0;
        }
    }

    printf("%d\n", count);
    return 0;
}
```

## Output:
<img width="627" height="127" alt="image" src="https://github.com/user-attachments/assets/04b22bbd-412c-4e7d-93d1-5421d7b46314" />

## Result:

Thus, the C program that counts the number of words in a given sentence is verified successfully.
