# 19AI305 - Advanced C Programming - ODD - 2026

# IAPR - Module 12

# EXP.01 : PROGRAM TO DISPLAY STACK ELEMENTS USING LINKED LIST

## Aim:

To write a Function in C program to display stack elements using linked list.

## Algorithm:

1.	Define a structure Node with two members: data to store the integer value and next to point to the next node in the linked list.
2.	Declare a global variable head representing the starting node of the linked list.
3.	Define a function display to print the elements of the linked list.
4.	Declare a pointer p and initialize it with the head of the linked list.
5.	Use a while loop to traverse the linked list:
6.	Print the data of the current node.
7.	Move to the next node using the next pointer.
 
## Program:

```c
struct Node   
{  
char data;  
struct Node *next;  
}*head;  
void display()  
{  
    struct Node *ptr;  
    ptr=head;  
    while(ptr!=NULL)  
    {  
        printf("%c\n",ptr->data);  
        ptr=ptr->next;  
    }  
}
```

## Output:

<img width="370" height="436" alt="image" src="https://github.com/user-attachments/assets/b9a9dcae-a40e-4d73-9aa6-96f2f8164d9c" />

## Result:

Thus, the Function in C program to display stack elements using linked list is verified successfully. 

***

# EXP.02 : PROGRAM TO POP AN ELEMENT FROM THE GIVEN STACK USING LINKED LIST

## Aim:

To write a Funtion in C program to pop an element from the given stack using liked list.

## Algorithm:

1.	Check for Empty Stack
2.	If head is equal to NULL, Print "Stack is empty."
3.	Else Proceed to the next step.
4.	Set head to point to the next node in the stack.
 
## Program:

```c
struct Node   
{  
char data;  
struct Node *next;  
}*head;  
void pop()  
{  
    struct Node *ptr;  
    if(head==NULL)  
    {  
        printf("stack is empty");  
    }  
    else  
    {  
        ptr=head;  
        head=ptr->next;  
        free(ptr);  
    }  
}
```

## Output:

<img width="868" height="557" alt="image" src="https://github.com/user-attachments/assets/33f3acd5-0401-44dc-9bff-13271c6a3886" />

## Result:

Thus, the Function in C program to pop an element from the given stack using liked list is verified successfully.

***
 
# EXP.03 : PROGRAM TO DISPLAY QUEUE ELEMENTS USING LINKED LIST.

## Aim:

To write a Function in C program to display queue elements using linked list.

## Algorithm:

1.	Check if Queue is Empty
2.	Display Queue Elements
3.	Print the data of the current node pointed to by front
4.	Update front to point to the next node.
5.	End the display function.
 
## Program:

```c
struct Node
{
   float data;
   struct Node *next;
}*front=NULL,*rear=NULL;
void display()
{
   if(front==NULL)
   {
      printf("queue is empty\n");
      return;
   }
   else
   {
      printf("queue elements:\n");
      struct Node *temp=front;
      while(temp->next!=NULL)
      {
          printf("%0.2f\n",temp->data);
          temp=temp->next;
      }
      printf("%0.2f\n",temp->data);
   }
}
```

## Output:

<img width="575" height="487" alt="image" src="https://github.com/user-attachments/assets/6539afea-78fe-49cd-a354-2fbaf66dbd23" />

## Result:

Thus, the Function in C program to display queue elements using linked list is verified successfully.

***
 
# EXP.04 : PROGRAM TO INSERT ELEMENTS IN QUEUE USING LINKED LIST

## Aim:

To write a Function C program to insert elements in queue using linked list

## Algorithm:

1.	Allocate Memory for New Node
2.	Set Data and Next Pointer
3.	Check if Queue is Empty
4.	Set both front and rear to point to the new node p.
5.	Set the next pointer of the current rear to point to the new node p.
6.	End of Enqueue Operation
 
## Program:

```c
struct Node
{
   int data;
   struct Node *next;
}*front=NULL,*rear=NULL;
void enqueue(int data)
{
    struct Node *newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = data;
    newNode->next = NULL;
    if(rear==NULL){
        front = rear = newNode;
    }
    else{
        rear->next = newNode;
        rear = newNode;
    }
}
```

## Output:

<img width="547" height="482" alt="image" src="https://github.com/user-attachments/assets/8dd00607-6782-48b9-83cf-0132a24b4baa" />

## Result:

Thus, the Function in C program to insert elements in queue using linked list is verified successfully.

***

# EXP.05 : FUNCTION TO FIND THE PEEK OF QUEUE USING LINKED LIST

## Aim:

To write a function in C program to retrieve the "peek" (the front element) of a queue implemented using a linked list.

## Algorithm:

1.	Check if the queue is empty:
o	If the queue is empty (i.e., the front pointer is NULL), return an error or a message indicating that the queue is empty.
2.	Access the front element:
o	If the queue is not empty, return the data stored in the front node of the linked list (i.e., the element at the head of the queue).

## Program:

```c
struct Node
{
   float data;
   struct Node *next;
}*front=NULL,*rear=NULL;
void peek()
{
    if(front==NULL){
        printf("Queue is Empty\n");
        return;
    }
    printf("%0.2f\n", front->data);
}
```
## Output:

<img width="430" height="508" alt="image" src="https://github.com/user-attachments/assets/e849565f-a798-4381-973c-241e2e9d9584" />

## Result:

Thus, the Function in C program to retrieve the "peek" (the front element) of a queue implemented using a linked list is verified successfully.
