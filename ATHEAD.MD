

# **Basic Linked List Implementation (Insertion at Head)**

This C++ program demonstrates a basic implementation of a singly linked list. It defines a `Node` class representing individual nodes in the linked list and provides functions to insert a new node at the head of the list (`insertAtHead`) and print the elements of the list (`print`).

## **Code Explanation**

The following code demonstrates the creation of a linked list, insertion of elements at the head, and printing the elements:

```cpp
#include <iostream>
using namespace std;

class Node {
public:
    int data;
    Node* next;
    
    Node(int data) {
        this->data = data;
        this->next = NULL;
    }
};

void insertAtHead(Node* &head, int d) {
    Node* temp = new Node(d);
    temp->next = head;
    head = temp;
}

void print(Node* &head) {
    Node* temp = head;
    
    while(temp != NULL) {
        cout << temp->data << " ";
        temp = temp->next;
    }
    cout << endl;
}

int main() {
    Node* node1 = new Node(10);
    
    cout << node1->data << endl;
    cout << node1->next << endl;
    
    Node* head = node1;
    print(head);
    
    insertAtHead(head, 12);
    print(head);
     
    insertAtHead(head, 15);
    print(head);

    return 0;
}
```

**Explanation:**
- The `Node` class defines the structure of a node in the linked list. Each node contains an integer value (`data`) and a pointer to the next node (`next`).
- The `insertAtHead` function inserts a new node with the given data at the beginning of the linked list.
- The `print` function traverses the linked list and prints the data of each node.


---

Let me know if you need further assistance!