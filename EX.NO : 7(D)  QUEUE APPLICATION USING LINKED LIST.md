
# EX.NO : 7(D)  QUEUE APPLICATION USING LINKED LIST 
 
# PROGRAM STATEMENT: 
 
write a C++ program to implement FCFS algorithm(no of.process p1,p2 and p3 and its burst time are 10,5 & 8) find out waiting time of the each process & Average waiting time of the process?

 
 
# ALGORITHM:   
 
1. Start the program. 
2. Initialize Variables: Define arrays for burst time (bt), waiting time (wt), and turn-around time (tat). 
3. Input Burst Times: Set burst times for 3 processes (e.g., 10, 5, 8). 
4. Calculate Waiting Times: For each process (except the first), sum the burst times of the previous processes. 
5. Calculate Turnaround Times: Add burst time and waiting time for each process. 
6. Display Results: Print process number, burst time, and waiting time for each process. 
7. End the Program: No average calculation needed. 
 
# PROGRAM: 
```
#include<iostream>
using namespace std;
int findWaitingTime(int processes[], int n,int bt[], int wt[])
{
   wt[0]=0;
   for (int  i = 1; i < n ; i++ )
   {
        wt[i] =  bt[i-1] + wt[i-1] ;
   }
   return 0;
}
 int avgtime(int processes[],int n,int bt[])
 {
     int wt[n],totwt=0;
     findWaitingTime(processes,n,bt,wt);
    cout <<"Processes   BT time   WT time  "<<endl; 
    for (int  i=0; i<n; i++)
    {
        totwt=totwt+wt[i];
        cout<<"       "<<i+1<<"       "<<bt[i]<<"       "<<wt[i]<<endl;
    }
    cout<<"Average waiting time = "<<((float)totwt/(float)n)<<endl;
     return 0;
 }
 
// Driver code
int main()
{
    //process id's
    int processes[] = { 1, 2, 3};
    int n = sizeof processes / sizeof processes[0];
    int bt[]={10,5,8};
    avgtime(processes, n, bt);
    return 0;
}
```

# output:

![image](https://github.com/user-attachments/assets/0f4d19d3-8388-4d65-b162-0e71867f3f87)

# RESULT: 
 
Thus, the C++ program to implement FCFS algorithm(no of.process p1,p2 and p3 and its burst time are 10,5 & 8) find out waiting time of the process is created successfully. 

