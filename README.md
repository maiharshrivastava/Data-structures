# Basic LinkedList 

This C++ program demonstrates the creation of a basic linked list. It consists of a `Node` class representing individual nodes in the linked list and a `main` function that creates a single node and prints its data and the value of its `next` pointer.

## Code Explanation

The following code creates a basic linked list node using the `Node` class and prints its data and the value of its `next` pointer:

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

int main() {
    Node* node1 = new Node(10);
    cout << node1->data << endl;
    cout << node1->next << endl;
    return 0;
}


Explanation:
- The `Node` class defines the structure of a node in the linked list. It has two public member variables: `data` to store the value of the node, and `next` to point to the next node in the list.
- In the `main` function, a new node `node1` is created with data `10` using the `Node` constructor.
- The `data` member of `node1` is printed to the console.
- The `next` pointer of `node1` is printed to the console. This will likely print a memory address, as it points to another `Node` object or is `NULL` if it's the last node in the list.
