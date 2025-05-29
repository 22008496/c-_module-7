
# EX.NO : 7(C)  QUEUE USING LINKED LIST 
 
# PROGRAM STATEMENT: 
 
To write a CPP Program to implement Queue using Linked List, insert float elements in to Queue 
and delete two items from Queue. 
 
# ALGORITHM:   
 
1. Start the program. 
2. Define Node: Create a Node class with data and next pointer. 
3. Push: Insert a new node at the rear of the queue. 
4. Pop: Remove the front node. 
5. Display: Print the queue from front to rear. 
6. Display Front/Rear: Print front and rear node data. 
7. Main: Perform pop(), push(), and display queue operations. 
8. End the program. 
 
# PROGRAM:
```
#include<iostream>
using namespace std;
struct Node
{
    double data;
    Node *next;
};
class Queue
{
    public:
    Node *front,*rear;
    Queue()
    {
        front=rear=NULL;
    }
    void insert(double n);
    void deleteitem();
    void display();
    ~Queue();
};
void Queue::insert(double n)
{
    Node *temp=new Node;
    if(temp==NULL)
    {
        cout<<"Overflow"<<endl;
        return;
    }
    temp->data=n;
    temp->next=NULL;
    if(front==NULL)
    {
        front=rear=temp;
    }
    else
    {
        rear->next=temp;
        rear=temp;
    }
    cout<<n<<" ";
}
void Queue::display()
{
    if(front==NULL)
    {
        cout<<"Underflow."<<endl;
        return;
    }
    Node *temp=front;
    while(temp)
    {
        cout<<temp->data<<" ";
        temp=temp->next;
    }
    cout<<endl;
}
void Queue::deleteitem()
{
    if(front==NULL)
    {
        cout<<"underflow"<<endl;
        return;
    }
    if(front==rear)
        front=rear=NULL;
    else
        front=front->next;
}
Queue::~Queue()
{
    while(front!=NULL)
    {
        Node *temp=front;
        front=front->next;
        delete temp;
    }
    rear=NULL;
}
int main()
{
    int n,i;
    double a[10];
    cin>>n;
    Queue Q;
    Q.display();
    cout<<"Queue :";
    for(i=0;i<n;i++)
    {
        cin>>a[i];
        Q.insert(a[i]);
    }
    cout<<endl;
    Q.deleteitem();
    Q.deleteitem();
    cout<<"After DeQueue :";
    Q.display();
    cout<<"Queue Front : "<<(Q.front)->data<<endl;
    cout<<"Queue Rear : "<<(Q.rear)->data;
    return 0;
}
```
# output:

![image](https://github.com/user-attachments/assets/bf9401fd-22e5-4095-90c0-4237180fa010)

# RESULT: 
 
Thus, the C++ program to implement Queue using Linked List, insert float elements in to Queue and delete two items from Queue is created successfully. 

