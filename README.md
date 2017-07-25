# Jesse-and-Cookies-Hackerrank-Solution
Solution for Jesse and Cookies solution using Min Heap implemented using Priority Queue

#include <cmath>
#include <cstdio>
#include <vector>
#include <iostream>
#include <algorithm>
#include <bits/stdc++.h>
using namespace std;


int main() {
    long N,K;
    cin>>N>>K;
    priority_queue<long,vector<long>,greater<long> >pq;
    long arr[N];
    for(int i=0;i<N;i++){
        cin>>arr[i];
        pq.push(arr[i]);
    }
    long cnt=0;
    if(pq.top()< K){
        while(pq.top() < K){
            if(pq.size() >1){
        long x=pq.top();
        pq.pop();
        long y=pq.top();
        pq.pop();
        long sweet=x+(2*y);
        pq.push(sweet);
            cnt++;
        }
            else break;
        }
        if((pq.size() > 1) || (pq.size()==1 && pq.top() >= K))
            cout<<cnt<<"\n";
        else
           cout<<-1<<"\n";            
        }
    else
        cout<<0<<"\n";  
    return 0;
}
