# 19AI305 - Advanced C Programming - ODD - 2026

# IAPR - Module 07

# EXP.01 : C PROGRAM FOR ARRAY OF STRUCTURE TO CHECK ELIGIBILITY FOR THE VACCINE

## Aim:

To write a C program for array of structure to check eligibility for the vaccine person age above 6 years of age.

## Algorithm:

1.	Declare structure eligible with age (integer) and n (character array)
2.	Declare variable e of type eligible
3.	Input age and name using scanf, store in e
4. Conditions:
- If e.age > 6 { Print "Vaccine Eligibility: Yes" }
- Else { Print "Vaccine Eligibility: No" }
5.	Print details (e.age, e.n)
6.	Return 0
 
## Program:

```c

#include <stdio.h>

struct Person {
    int age;
    char name[50];
};

int main() {
    struct Person p[1];
    printf("Enter Your Age: ");
    if (scanf("%d", &p[0].age) == 1) {
        printf("\nEnter Your Name: ");
        scanf("%s", p[0].name);

        printf("Age:%d\n", p[0].age);
        printf("Name:%s\nvaccine:%d\n", p[0].name, p[0].age);

        if (p[0].age > 6) {
            printf("eligibility:yes\n");
        } else {
            printf("eligibility:no\n");
        }
    }

    return 0;
}

```


## Output:

<img width="687" height="250" alt="image" src="https://github.com/user-attachments/assets/6920024c-de5a-432d-8f2a-2505f2bcdba9" />

<img width="640" height="182" alt="image" src="https://github.com/user-attachments/assets/b4625d98-5ce4-4d69-aade-6d9edb895dc6" />


## Result:

Thus, the C program for array of structure to check eligibility for the vaccine person age above 6 years of age is verified successfully. 

*** 

# EXP.02 : C PROGRAM FOR PASSING STRUCTURES AS FUNCTION ARGUMENTS AND RETURNING A STRUCTURE FROM A FUNCTION

## Aim:

To write a C program for passing structure as function and returning a structure from a function.

## Algorithm:

1.	Define structure numbers with members a and b.
2.	Declare variable n of type numbers.
3.	Prompt the user to enter values for a and b.
4.	Input values for a and b into n using scanf.
5.	Call the add function with n as an argument.
6.	Print the result returned by the add function.
7.	Return 0
 
## Program:

```c
#include <stdio.h>

struct numbers {
    int a;
    int b;
};

struct numbers add(struct numbers num);

int main() {
    struct numbers n;

    printf("Enter value for a: ");
    scanf("%d", &n.a);

    printf("Enter value for b: ");
    scanf("%d", &n.b);

    struct numbers result = add(n);

    printf("\n--- Results ---\n");
    printf("Value of a: %d\n", result.a);
    printf("Value of b: %d\n", result.b);

    return 0;
}

struct numbers add(struct numbers num) {
    num.a = num.a + 10;
    num.b = num.b + 20;
    return num;
}

```

## Output:

<img width="652" height="226" alt="image" src="https://github.com/user-attachments/assets/ea676d3b-a16b-4413-9b8b-7da1efec39a5" />

## Result:
Thus, the C program for passing structure as function and returning a structure from a function is verified successfully.

***
 
# EXP.03 : C PROGRAM TO READ A FILE NAME FROM USER AND WRITE THAT FILE USING FOPEN()

## Aim:

To write a C program to read a file name from user and write that File using fopen().

## Algorithm:

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
 
## Program:

```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    FILE *p;
    char name[100];

    printf("Enter the file name: ");
    scanf("%s", name);

    p = fopen(name, "w");
    if (p == NULL) {
        printf("Error opening file.\n");
        exit(1);
    }

    printf("File created successfully.\n");
    printf("File opened successfully.\n");

    fclose(p);
    printf("File closed successfully.\n");

    return 0;
}
```

## Output:

<img width="690" height="190" alt="image" src="https://github.com/user-attachments/assets/8f794b09-6fe5-4771-81f9-e96af8ebf858" />

## Result:

Thus, the C program to read a file name from user and write that File using fopen() is verified successfully.
 
***

# EXP.04 : PROGRAM TO READ A FILE NAME FROM USER, WRITE THAT FILE AND INSERT TEXT IN TO THAT FILE

## Aim:

To write a C program to read a file and insert text in that file.

## Algorithm:

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
 
## Program:

```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    FILE *p;
    char name[100], text[100];
    int num, i;

    printf("Enter the file name: ");
    scanf("%s", name);

    printf("Enter the number of strings: ");
    scanf("%d", &num);

    p = fopen(name, "w");
    if (p == NULL) {
        printf("Error opening file.\n");
        exit(1);
    }

    printf("File opened successfully.\n");

    getchar();
    for (i = 0; i < num; i++) {
        printf("Enter string %d: ", i + 1);
        fgets(text, sizeof(text), stdin);
        fputs(text, p);
    }

    fclose(p);
    printf("Data added successfully.\n");

    return 0;
}
```

## Output:

<img width="695" height="240" alt="image" src="https://github.com/user-attachments/assets/bac0f9f4-c10c-4898-81ca-5e401e45abcc" />

## Result:
Thus, the C program to read a file and insert text in that file is verified successfully

***

# Exp.05 : C PROGRAM TO DISPLAY STUDENT DETAILS USING STRUCTURE

## Aim:

Write a C program to dynamically allocate memory to store information about multiple subjects (name and marks), input the details for each subject, and then display the stored information. Finally, it frees the allocated memory to prevent memory leaks.

## Algorithm:

1. Input the number of subjects.
2. Read the integer value n from the user, which represents the number of subjects.
3. Dynamically allocate memory:
4. Use malloc to allocate memory for n subjects. Each subject has a name (array of characters) and marks (integer).
5. If memory allocation fails (i.e., the pointer s is NULL), display an error message and exit the program.
6. Input the details of each subject
7. Use a for loop to read the name and marks of each subject using scanf. For each subject, store the name as a string and marks as an integer in the dynamically allocated memory.
8. Display the details of each subject
9. Use another for loop to print the name and marks of each subject.
10. Free the allocated memory
11. After all operations are done, call free(s) to release the dynamically allocated memory.
12. Return from the main function
13. End the program by returning 0.

## Program:

```c
#include <stdio.h>
#include <stdlib.h>

struct Subject {
    char name[50];
    int marks;
};

int main() {
    int n, i;

    printf("Enter the number of subjects: ");
    if (scanf("%d", &n) != 1 || n <= 0) {
        return 1;
    }

    struct Subject *s = (struct Subject *)malloc(n * sizeof(struct Subject));
    if (s == NULL) {
        printf("Memory allocation failed.\n");
        return 1;
    }

    for (i = 0; i < n; i++) {
        printf("Enter subject %d name: ", i + 1);
        scanf("%s", (s + i)->name);
        printf("Enter marks for %s: ", (s + i)->name);
        scanf("%d", &(s + i)->marks);
    }

    printf("\n--- Subject Details ---\n");
    for (i = 0; i < n; i++) {
        printf("Subject %d: %s | Marks: %d\n", i + 1, (s + i)->name, (s + i)->marks);
    }

    free(s);
    return 0;
}
```
## Output:

<img width="652" height="498" alt="image" src="https://github.com/user-attachments/assets/5875d268-2053-428e-a8a3-6c30cee71528" />

## Result:
Thus,the C program to dynamically allocate memory to store information about multiple subjects (name and marks), input the details for each subject, and then display the stored information. Finally, it frees the allocated memory to prevent memory leaksis verified successfully.
