
# EX.NO : 7(A)  STACK USING LINKED LIST 
 
# PROGRAM STATEMENT: 
 
To write a CPP Program to insert five special character elements in to stack using linked list. 
 
# ALGORITHM:   
 
1. Start the program/ 
2. Define a stack of type char to hold elements. 
3. Input the number of elements (n) to be pushed onto the stack. 
4. Use a loop to input n characters and push them onto the stack. 
5. Output the current size of the stack using s.size(). 
6. Output the top element of the stack using s.top(), then pop the element and repeat for the second pop operation. 
7. After two pop operations, output the new top element and the size of the stack. 
8. End the program. 
 
# PROGRAM:
```
#include <iostream>
#include <list>
using namespace std;

template <typename T>
class Stack {
public:
    list<T> l;
    int cs = 0;

    void push(T d) {
        cs++;
        l.push_front(d);
    }

    void pop() {
        if (cs <= 0) {
            cout << "Stack empty" << endl;
        } else {
            cs--;
            l.pop_front();
        }
    }

    bool empty() {
        return cs == 0;
    }

    T top() {
        return l.front();
    }

    int size() {
        return cs;
    }

    void print() {
        for (auto x : l) {
            cout << x << endl;
        }
    }
};

int main() {
    Stack<char> s;
    int n;
    char x;

    cin >> n;

    for (int i = 0; i < n; i++) {
        cin >> x;
        s.push(x);
    }

    cout << "Current size of the stack is " << s.size() << endl;
    cout << "The top element of the stack is " << s.top() << endl;

    s.pop(); // 1st pop
    cout << "The top element after 1 pop operation is " << s.top() << endl;

    s.pop(); // 2nd pop
    cout << "The top element after 2 pop operations is " << s.top() << endl;

    cout << "Size of the stack after 2 pop operations is " << s.size() << endl;


    return 0;
}
```

# output:

![image](https://github.com/user-attachments/assets/0b288e03-30e4-4949-8a74-6052780221b0)

# RESULT: 
 
Thus, the C++ program to insert five special character elements in to stack using linked list is created successfully. 

