# 19AI305 - Advanced C Programming - ODD - 2026

# IAPR - Module 10

# EXP.01 :  C PROGRAM TO SEARCH A GIVEN ELEMENT IN THE GIVEN SINGLY LINKED LIST.

## Aim:

To write a Function in C program to search a given element in the given singly linked list.

## Algorithm:

1.	Define the structure for a node in a singly linked list.
2.	Define the search function to find a specific character in the linked list.
3.	Initialize the head of the linked list as needed.
4.	Call the search function and perform other linked list operations as needed.
 
## Program:

```c
struct Node{
    char data;
    struct Node *next;
}*head = NULL;

void search(char data)
{
    struct Node *temp = head;
    int loc =1;
    while(temp!=NULL){
        if(temp->data==data){
            printf("item %c found at location %d\n",data,loc);
            return;
        }
        temp = temp->next;
        loc++;
    }
    printf("Item not found\n");
}
```

## Output:

<img width="741" height="456" alt="image" src="https://github.com/user-attachments/assets/ff505b11-8fb4-483f-a1f4-e118aaa42561" />

## Result:

Thus, the Function in C program to search a given element in the given linked list is verified successfully.

***

# EXP.02 : PROGRAM TO INSERT A NODE IN A LINKED LIST.

## Aim:

To write a Funtion in C program to insert a node in a linked list.

## Algorithm:
1.	Define the structure for a node in a linked list
2.	Define the insert function to insert a new node with character data at the end of the linked list.
3.	Initialize the head of the linked list as needed.
4.	Call the insert function and perform other linked list operations as needed.
 
## Program:

```c
struct Node {
    float data;
    struct Node *next;
};

struct Node *head = NULL;

void insert(float data) {
    struct Node *n = (struct Node*)malloc(sizeof(struct Node));
    n->data = data;
    n->next = NULL;
    
    if (head == NULL) {
        head = n;
        return;
    }
    
    struct Node *temp = head;
    while (temp->next != NULL) {
        temp = temp->next;
    }
    temp->next = n;
}
```

## Output:

<img width="428" height="202" alt="image" src="https://github.com/user-attachments/assets/457c8f00-5112-4bd8-aae9-432ae33c7a33" />

## Result:

Thus, the Funtion in C program to insert a node in a linked list is verified successfully.

***
 
# EXP.03 : PROGRAM TO TRAVERSE A DOUBLY LINKED LIST

## Aim:

To write a Funtion in C program to traverse a doubly linked list.

## Algorithm:

1.	Initialize a temporary pointer (temp) to the head of the list.
2.	Use a while loop to traverse the list until the end (temp == NULL) is reached.
3.	Inside the loop, print the data of the current node.
4.	Move to the next node by updating the temp pointer to point to the next node (temp = temp->next).
 
## Program:

```c
struct Node {
    struct Node *prev;
    struct Node *next;
    int data;
} *head;

void display() {
    struct Node *temp = head;
    while (temp != NULL) {
        printf("%d ", temp->data);
        temp = temp->next;
    }
}
```

## Output:

<img width="465" height="203" alt="image" src="https://github.com/user-attachments/assets/910a6b0d-6894-43a1-9b92-5048f4bf5929" />

## Result:
Thus, the Funtion in C program to traverse a doubly linked list is verified successfully. 

***

# EXP.04 : PROGRAM TO INSERT AN ELEMENT IN DOUBLY LINKED LIST

## Aim:

To write a Funtion in C program to insert an element in doubly linked list.

## Algorithm:

1.	Create a new node (newNode) and allocate memory for it.
2.	Set the data of the new node to the provided value.
3.	If the list is empty, set the new node as the head.
4.	If the list is not empty, traverse the list to find the last node.
5.	Set the new node's prev pointer to the last node and update the last node's next pointer to the new node.
 
## Program:

```c
#include <stdio.h>
#include <stdlib.h>

struct Node {
    struct Node *prev;
    struct Node *next;
    float data;
} *head = NULL;

void insert(float data) {
    struct Node *newNode = (struct Node *)malloc(sizeof(struct Node));
    newNode->data = data;
    newNode->next = NULL;
    newNode->prev = NULL;
    
    if (head == NULL) {
        head = newNode;
        return;
    }
    
    struct Node *temp = head;
    while (temp->next != NULL) {
        temp = temp->next;
    }
    temp->next = newNode;
    newNode->prev = temp;
}
```

## Output:

<img width="646" height="202" alt="image" src="https://github.com/user-attachments/assets/5060218a-8c14-4cac-8feb-24961aeb108d" />

## Result:

Thus, the program to insert an element in doubly linked list is verified successfully.

***

# EXP.05 : C FUNCTION TO DELETE A GIVEN ELEMENT IN THE GIVEN DOUBLY LINKED LIST

## Aim:

To write a C function that deletes a given element from a Doubly linked list.

## Algorithm:

1.	Check if the Linked List is Empty:
o	If the head of the linked list is NULL, print a message indicating the list is empty and exit the function.
2.	Traverse the Linked List:
o	Start from the head node and iterate through the list to find the node that contains the given element (data).
3.	Handle Deletion of the First Node:
o	If the element to be deleted is found in the head node:
	Update the head of the linked list to point to the next node (i.e., head = head->next).
	Free the memory allocated to the node to be deleted.
	Exit the function.
4.	Traverse and Delete from the Middle or End:
o	If the element is not in the head node, continue traversing the list by checking each node’s next pointer.
o	When the node with the element is found, update the previous node’s next pointer to point to the next node of the node to be deleted (prev->next = current->next).
o	Free the memory allocated to the node to be deleted.
5.	Handle the Case when the Element is Not Found:
o	If the element is not found in any node, print a message indicating the element is not present in the list.
6.	End the Function.

## Program:

```c
#include <stdio.h>
#include <stdlib.h>

struct Node {
    struct Node *prev;
    struct Node *next;
    int data;
} *head;

void delete() {
    if (head == NULL) {
        printf("UNDERFLOW\n");
        return;
    }
    struct Node *temp = head;
    head = head->next;
    if (head != NULL) {
        head->prev = NULL;
    }
    free(temp);
    printf("Node deleted\n");
}
```

## Output:

<img width="591" height="628" alt="image" src="https://github.com/user-attachments/assets/27b795bb-317a-46df-a76d-2e981852cb39" />

## Result:
Thus, the function in C program that deletes a given element from a linked list is verified successfully.
