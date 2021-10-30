#include <iostream>
using namespace std;

struct process
{
int pid, bt, wt, tt;
};

int main() 
{
        struct process x[5],p[10];
        int i,j,k,m,n, tot=0;
        float  wttime=0.0,tottime=0.0 ,a1,a2;
        cout<<"\nEnter the number of process:\t";
        cin>>n;
        for(i=1;i<=n;i++)
        {
        x[i].pid=i;
        cout<<"\nEnter the burst time:\t";
        cin>>x[i].bt;
        tot=tot+x[i].bt;
        }
        cout<<"\n total barst time : \t"<<tot;
        p[0].tt=0;
        k=1;
        cout<<"\n\nEnter the time slice: \t";
        cin>>m;
        for(j=1;j<=tot;j++)
           {
               for(i=1;i<n;i++)
                {
                    if(x[i].bt!=0)
                         {
                             p[k].pid=i;
                             if(x[i].bt-m<0)
                                {
                                    p[k].wt=p[k-1].tt;
                                    p[k].bt=x[i].bt;
                                    p[k].tt=p[k].wt+x[i].bt;
                                    x[i].bt=0;
                                    k++;
                                }
                                else
                                {
                                    p[k].wt=p[k-1].tt;
                                    p[k].tt=p[k].wt+m;
                                    x[i].bt=x[i].bt-m;
                                    k++;
                                }
                         }
                 }
           }     
        cout<<"\n\nProcess id   \twt  \ttt"<<endl;
        for(i=1;i<k;i++)
        {
            cout<<"\n \t"<<p[i].pid<<"       \t"<<p[i].wt<< "     \t"<<p[i].tt<<"\n";
            wttime=wttime+p[i].wt;
            tottime=tottime+p[i].tt;  
        }
        a1=wttime/n;
        a2=tottime/n;
        cout<<"\nAVG1="<<a1<<"\tAVG2="<<a2;
        return 0; 
            
   }
