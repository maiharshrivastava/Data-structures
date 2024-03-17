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

void InsertAtTail(Node* &tail, int d) {
    Node* temp = new Node(d);
    if (tail == nullptr) {
        tail = temp;
    } else {
        tail->next = temp;
        tail = temp;
    }
}

void InsertAtPosition(Node* &tail,Node* &head, int position, int d) {
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

    if (temp -> next == NULL ){
                InsertAtTail(tail,d);

        return;
    }

    Node* nodeToInsert = new Node(d);
    nodeToInsert->next = temp->next;
    temp->next = nodeToInsert;
}

void print(Node* head) {
    Node* temp = head;
    
    while (temp != nullptr) {
        cout << temp->data << " ";
        temp = temp->next;
    }
    cout << endl;
}

int main() {
    Node* node1 = new Node(10);

    // cout << node1->data << endl;
    // cout << node1->next << endl;

    Node* head = node1;
    Node* tail = node1;
    print(head);

    InsertAtTail(tail, 12);
    print(head);
     InsertAtTail(tail, 15);
    print(head);

    InsertAtPosition(tail , head, 3, 22);
    print(head);


    cout << "head " << head -> data << endl;
    cout << "tail " << tail -> data << endl;

    return 0;
}
