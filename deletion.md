# Linked List Operations: Insertion and Deletion

This C++ program demonstrates the management of a singly linked list with capabilities to insert nodes at the head, tail, at a specified position, and delete a node from a specified position. The program also includes a destructor in the `Node` class for automatic cleanup when a node is deleted.

## Features

- Insert at the head of the linked list.
- Insert at the tail of the linked list.
- Insert at a specified position within the list.
- Delete a node from a specified position.
- Automatic memory management for nodes.

## Code

```cpp
#include <iostream>
#include <map>
using namespace std;

class Node {
public:
    int data;
    Node* next;

    // Constructor
    Node(int data) {
        this->data = data;
        this->next = NULL;
    }

    // Destructor
    ~Node() {
        int value = this->data;
        // Memory deallocation
        if (this->next != NULL) {
            delete next;
            this->next = NULL;
        }
        cout << "Memory is freed for node with data " << value << endl;
    }
};

void insertAtHead(Node* &head, int d) {
    Node* temp = new Node(d);
    temp->next = head;
    head = temp;
}

void insertAtTail(Node* &tail, int d) {
    Node* temp = new Node(d);
    tail->next = temp;
    tail = temp;
}

void print(Node* &head) {
    if (head == NULL) {
        cout << "List is empty" << endl;
        return;
    }
    Node* temp = head;
    while (temp != NULL) {
        cout << temp->data << " ";
        temp = temp->next;
    }
    cout << endl;
}

void insertAtPosition(Node* &tail, Node* &head, int position, int d) {
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
    if (temp->next == NULL) {
        insertAtTail(tail, d);
        return;
    }
    Node* nodeToInsert = new Node(d);
    nodeToInsert->next = temp->next;
    temp->next = nodeToInsert;
}

void deleteNode(int position, Node* &head) {
    if (position == 1) {
        Node* temp = head;
        head = head->next;
        temp->next = NULL;
        delete temp;
    } else {
        Node* curr = head;
        Node* prev = NULL;
        int cnt = 1;
        while (cnt < position) {
            prev = curr;
            curr = curr->next;
            cnt++;
        }
        prev->next = curr->next;
        curr->next = NULL;
        delete curr;
    }
}

int main() {
    Node* node1 = new Node(10);
    Node* head = node1;
    Node* tail = node1;

    insertAtTail(tail, 12);
    insertAtTail(tail, 15);
    insertAtPosition(tail, head, 4, 22);
    deleteNode(3, head);

    print(head);

    return 0;
}
```

Feel free to use this code as a reference for implementing linked lists in your C++ projects.