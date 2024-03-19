# Linked List Insertion at Head, Tail, and Position

This code demonstrates a linked list implementation in C++. It provides functionality to insert nodes at the head, tail, and at a specified position in the linked list.

## Code 

```cpp
#include <iostream>
using namespace std;

class Node {
public:
    int data;
    Node* next;
    
    Node(int data) {
        this->data = data;
        this->next = nullptr;
    }
};

void insertAtHead(Node* &head, int d) {
    Node* temp = new Node(d);
    temp->next = head;
    head = temp;
}

void InsertAtTail(Node* &tail, int d) {
    Node* temp = new Node(d);
    tail->next = temp;
    tail = temp;
}

<<<<<<< HEAD
void InsertAtPosition(Node* &tail, Node* &head, int position, int d) {
    if (position == 1) {
        insertAtHead(head, d);
        return;
    }

    Node* temp = head;
    int cnt = 1;
    while (cnt < position - 1) {
        temp = temp->next;
        cnt++;
    }

    if (temp->next == nullptr) {
        InsertAtTail(tail, d);
        return;
    }

    Node* nodeToInsert = new Node(d);
    nodeToInsert->next = temp->next;
    temp->next = nodeToInsert;
}

void print(Node* head) {
=======
void print(Node* &head) {
>>>>>>> 4d2ed9ca8df88763fb830e59c0be509c25a8eaba
    Node* temp = head;
    
    while(temp != NULL) {
        cout << temp->data << " ";
        temp = temp->next;
    }
    cout << endl;
}

void InsertAtPosition(Node* &head,int position, int d){
    Node* temp = head;
    int cnt = 1;
    
    while(cnt < position -1){
        temp = temp-> next;
        cnt++;
    }
    
    Node* nodeToInsert = new Node(d);
    
    nodeToInsert -> next = temp -> next;
    
    temp -> next = nodeToInsert;
    
    
    
}





int main() {
    Node* node1 = new Node(10);
<<<<<<< HEAD

=======
    
    cout << node1->data << endl;
    cout << node1->next << endl;
    
>>>>>>> 4d2ed9ca8df88763fb830e59c0be509c25a8eaba
    Node* head = node1;
    Node* tail = node1;
    print(head);
    
    InsertAtTail(tail, 12);
    print(head);
<<<<<<< HEAD
    
    InsertAtTail(tail, 15);
    print(head);

    InsertAtPosition(tail, head, 3, 22);
    print(head);

    cout << "head " << head->data << endl;
    cout << "tail " << tail->data << endl;
=======
     
    InsertAtTail(tail, 15);
    print(head);
    
    InsertAtPosition(head, 3, 22);
        print(head);
>>>>>>> 4d2ed9ca8df88763fb830e59c0be509c25a8eaba

    return 0;
}
