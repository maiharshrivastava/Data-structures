# Linked List Node Creation and Printing

This C++ code demonstrates the creation of a basic linked list node and printing its data.

## Code Explanation

- The `Node` class represents a node in a linked list.
- It contains three attributes: `data` to store the node's value, `prev` to point to the previous node (not used in this example), and `next` to point to the next node.
- The constructor `Node(int d)` initializes the node with the given data value and sets `prev` and `next` pointers to NULL.
- The `print` function traverses the linked list starting from the provided `head` node and prints the data of each node.

## Code

```cpp
#include <iostream>
using namespace std;

class Node {
public:
    int data;
    Node* prev;
    Node* next;
    
    Node(int d) {
        this->data = d; // Initialize data with the passed parameter
        this->prev = NULL;
        this->next = NULL;
    }
};

void print(Node* head) {
    Node* temp = head;
    while (temp != NULL) {
        cout << temp->data; // Print data followed by space for readability
        temp = temp->next;
    }
    cout << endl;
}

int main() {    
    Node* node1 = new Node(10);
    Node* head = node1;
    print(head);
    return 0;
}
```

This code snippet creates a linked list node with data value `10` and prints its data.
