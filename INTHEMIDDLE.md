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
    tail->next = temp;
    tail = temp;
}

void print(Node* &head) {
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
    
    cout << node1->data << endl;
    cout << node1->next << endl;
    
    Node* head = node1;
    Node* tail = node1;
    print(head);
    
    InsertAtTail(tail, 12);
    print(head);
     
    InsertAtTail(tail, 15);
    print(head);
    
    InsertAtPosition(head, 3, 22);
        print(head);

    return 0;
}
