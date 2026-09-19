# 19AI305 - Advanced C Programming - ODD - 2026

# IAPR - Module 09

# EXP.01 : C PROGRAM TO DISPLAY STACK ELEMENTS USING AN ARRAY

## Aim:

To write Function in C program to display stack elements using an array.

## Algorithm:

1.	Include Necessary Header Files
2.	Declare Global Variables
3.	Define the Display Function
4.	Main Function (or Other Relevant Code)
5.	Initialize the stack and top as needed.
6.	Perform stack operations (push, pop, etc.).
7.	Use the display function to visualize the stack's contents
 
## Program:

```c
int top;
float stack[50];
void display()
{
    for(int i=top;i>=0;i--){
        printf("%.1f\n",stack[i]);
    }
}
```

## Output:

<img width="396" height="197" alt="image" src="https://github.com/user-attachments/assets/11a362bf-2ad8-46f9-8a77-fabe77278f51" />

## Result:

Thus, the Function in C program to display stack elements using an array is verified successfully.

*** 
 
# EXP.02 : PROGRAM TO PUSH THE GIVEN ELEMENT INTO A STACK USING ARRAY.

## Aim:

To write a Function in C program to push the given element into a stack using array.

## Algorithm:

1.	Declare global variables for the stack size, top index, and the stack itself.
2.	Define the push function to add a floating-point number to the stack.
3.	Initialize the stack size, top index, and the stack itself.
4.	Call the push function as needed.
 
## Program:

```c
int size=3,top=-1,stack[100];
void push (int data)
{
    if(top==size-1){
        printf("stack is full\n");
    } else{
        top++;
        stack[top]=data;
    }
}
```

## Output:

<img width="362" height="197" alt="image" src="https://github.com/user-attachments/assets/aafb26e4-0fac-477c-925f-7cb255eec70d" />

## Result:
Thus, the Function in C program to push the given element in to a stack using array is verified successfully

***

# EXP.03 : C PROGRAM TO DISPLAY QUEUE ELEMENTS USING ARRAY.

## Aim:

To write a Function in C program to display queue elements using array

## Algorithm:

1.	Declare global variables for the queue, rear, front, and iteration.
2.	Define the display function to print the elements of the queue.
3.	Initialize the queue, rear, and front as needed.
4.	Call the display function and perform other queue operations as needed.
 
## Program:

```c
int front,rear;
char queue[50];
void display()
{
    if(front==-1){
        printf("No elements to display");
    }
    else{
        for(int i=front;i<=rear;i++){
            printf("%c\n",queue[i]);
        }
    }
}
```

## Output:

<img width="670" height="482" alt="image" src="https://github.com/user-attachments/assets/6e0e1ec7-0049-4d93-afeb-0004bc9333fc" />

## Result:

Thus, the Function in C program to display queue elements using array is verified successfully.

***

# EXP.04 : C PROGRAM TO INSERT ELEMENTS IN QUEUE USING ARRAY.

## Aim:

To write a Function in C program to insert elements in queue using array.

## Algorithm:

1.	Declare global variables for the size, rear, front, and the queue itself.
2.	Define the enqueue function to add a float to the queue.
3.	Initialize the rear, front, and size of the queue as needed.
4.	Call the enqueue function as needed.

## Program:

```c
int size=10, rear=-1, front=-1;
float queue[50];
void enqueue(float data)
{
    if(rear==size-1){
        return;
    } else{
        if(front==-1) front=0;
    }
    rear=rear+1;
    queue[rear]=data;
}
```

## Output:

<img width="715" height="195" alt="image" src="https://github.com/user-attachments/assets/37341b09-6714-4bdf-b1c5-3acd7aff9839" />

## Result:
Thus, the Function in C program to insert elements in queue using array is verified successfully.

***

# EXP.05 : C FUNCTION TO DELETE ELEMENTS IN QUEUE USING ARRAY

## Aim:

To create a function in C that deletes an element from a queue implemented using an array.

## Algorithm:

1.	Check if the Queue is Empty
o	If the front pointer is -1, it means the queue is empty, and there are no elements to delete. Print a message indicating that the queue is empty.
2.	Delete the Front Element
o	If the queue is not empty, the element at the front index is deleted.
o	Increment the front pointer by 1 to remove the element and point to the next element in the queue.
3.	Check if the Queue Becomes Empty After Deletion:
o	After deletion, check if the front pointer has passed the rear pointer (front > rear). If this is true, reset both front and rear to -1, indicating that the queue is now empty.
4.	End the Function.

## Program:

```c
int front, rear;
void dequeue()
{
    if(front==-1||front>rear){
        printf("No elements to display\n");
    }
    else{
        front++;
    }
    if(front>rear){
        front=rear=-1;
    }
}
```
## Output:

<img width="712" height="227" alt="image" src="https://github.com/user-attachments/assets/e81302fe-55c6-40dd-9780-e40d6a2dff88" />

## Result:

Thus, the Function in C that deletes an element from a queue implemented using an array is verified successfully.
