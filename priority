#include <iostream>
using namespace std;
struct process
{
int pid;  int bt;   int wt;  int tt; int prior;
} p[10],temp;

int main() {
int i,j,n, totwt, tottt;
float avg1,avg2;
cout<<"\nEnter the number of process:\t";
cin>>n;
for(i=1;i<=n;i++)
{
p[i].pid=i;
cout<<"\nEnter the burst time:\t";
cin>>p[i].bt;
cout<<"\nEnter the priority:\t";
cin>>p[i].prior;
}
for(i=1;i<n;i++){
for(j=i+1;j<=n;j++)
{
if(p[i].bt>p[j].prior)
{
temp.pid=p[i].pid;
p[i].pid=p[j].pid;
p[j].pid=temp.pid;

temp.bt=p[i].bt;
p[i].bt=p[j].bt;
p[j].bt=temp.bt;

temp.prior=p[i].prior;
p[i].prior=p[j].prior;
p[j].prior=temp.prior;
}
}
}
p[1].wt=0;
p[1].tt=p[1].bt+p[1].wt;
i=2;
while(i<=n){
p[i].wt=p[i-1].bt+p[i-1].wt;
p[i].tt=p[i].bt+p[i].wt; 
i++;
}
i=1;
totwt=tottt=0;
cout<<"\nProcess id \tbt \twt \ttt";
while(i<=n){
cout<<"\n\t"<<p[i].pid<<"\t"<<p[i].bt<<"\t"<<p[i].wt<<"\t"<<p[i].tt<<"\n";
totwt=p[i].wt+totwt;
tottt=p[i].tt+tottt;  
i++;     
}
avg1=totwt/n;
avg2=tottt/n;
cout<<"\nAVG1="<<avg1<<"\tAVG2="<<avg2;
return 0; 
    
}
