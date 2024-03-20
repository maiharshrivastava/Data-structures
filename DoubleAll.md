# Linked List Operations

This C++ program demonstrates basic operations on a doubly linked list:

- Printing the linked list
- Getting the length of the linked list
- Inserting a node at the head
- Inserting a node at the tail
- Inserting a node at a specified position

## Code

```cpp
#include<iostream>
using namespace std;

class Node{
public:
    int data;
    Node* prev;
    Node* next;
    
    Node(int d){
        this->data = d; // Initialize data with the passed parameter
        this->prev = NULL;
        this->next = NULL;
    }
};

void print(Node* head){
    Node* temp = head;
    while(temp != NULL){
        cout << temp->data << " "; // Print data followed by space for readability
        temp = temp->next;
    }
    cout << endl;
}

int getLength(Node* head){
    int len = 0;
    Node* temp = head;
    while(temp != NULL){
        len++;
        temp = temp->next;
    }
    return len;
}

void insertAtHead(Node* &head, int d){
    Node* temp = new Node(d);
    temp->next = head;
    if (head != NULL) // Check if head is not NULL to avoid accessing NULL pointer
        head->prev = temp; // Set the previous pointer of the current head to the new node
    head = temp;
}

void insertAtTail(Node* &tail, int d){
    Node* temp = new Node(d);
    if (tail != NULL) { // Check if tail is not NULL to avoid accessing NULL pointer
        tail->next = temp;
        temp->prev = tail;
    }
    tail = temp;
}

void insertAtPosition(Node* &head, Node* &tail, int position, int d){
    if(position == 1){
        insertAtHead(head, d);
        if (tail == NULL) // If tail is NULL, set it to head since there's only one node
            tail = head;
        return;
    }
    Node* temp = head;
    int cnt = 1;
    
    while(cnt < position-1 && temp != NULL){ // Make sure temp is not NULL to avoid accessing NULL pointer
        temp = temp->next;
        cnt++;
    }
    
    if(temp == NULL || temp->next == NULL){ // Check if temp or temp->next is NULL
        insertAtTail(tail, d);
        return;
    }
    
    Node* nodeToInsert = new Node(d);
    nodeToInsert->next = temp->next;
    temp->next->prev = nodeToInsert;
    temp->next = nodeToInsert;
    nodeToInsert->prev = temp;
}

int main(){    
    Node* node1 = new Node(10);
    Node* head = node1;
    Node* tail = node1;
    
    print(head);
    cout << "Length: " << getLength(head) << endl;
    
    insertAtHead(head, 11);
    print(head);
    
    insertAtHead(head, 13);
    print(head);
    
    insertAtHead(head, 8);
    print(head);
    
    insertAtTail(tail, 25);
    print(head);
    
    insertAtPosition(head, tail, 2, 100);
    print(head);

    return 0;
}
