# infy hard- sheep

<img width="465" alt="Screenshot 2022-10-15 201801" src="https://user-images.githubusercontent.com/100711675/196444401-7e27bb8a-cd61-49b3-a50d-f342b53e2362.png">

<img width="474" alt="Screenshot 2022-10-15 222804" src="https://user-images.githubusercontent.com/100711675/196444414-6819c7b1-a90a-4e52-82a0-f647c20208dd.png">

<img width="575" alt="Screenshot 2022-10-17 120359" src="https://user-images.githubusercontent.com/100711675/196444425-ccf41eab-a336-4ea9-b0ea-9da0618ad538.png">

```
1
3
1 0 1
o->2

2
2
1 1
1 1
o->1

5
5
1 1 0 0 0
0 1 0 0 1
1 0 0 1 1
0 0 0 0 0
1 0 1 0 1
o->6
```
```c++
#include <bits/stdc++.h>
# define C cout
# define l "\n";
#define ll long long 
#define ld long double 
using namespace std;
const int NE=10000;
ll a[NE][NE];
bool herd(int i,int j,int r,int c){
    // C<<"dasd"<<l
    // C<<i<<" "<<j<<l
    if(i<0||j<0)return false;
    if(i>=r||j>=c||a[i][j]==0||a[i][j]==-1)return false;
    a[i][j]=-1;
    herd(i+1,j,r,c);    
    herd(i,j+1,r,c);
    herd(i-1,j,r,c);
    herd(i,j-1,r,c);
    return true;
}
int main() {
    int r,c;
    cin>>r>>c;
    int count=0;
    for(int i=0;i<r;i++){
        for(int j=0;j<c;j++){
            cin>>a[i][j];

    }
    }
      for(int i=0;i<r;i++){
        for(int j=0;j<c;j++){
            if(herd(i,j,r,c)){
                // C<<"if"<<l
                count++;
                }
    }
    }
    // C<<"------------------"<<l

    //  for(int i=0;i<r;i++){
    //     for(int j=0;j<c;j++){
    //         cout<<a[i][j]<<" ";

    // }
    // C<<l
    //  }
     C<<count<<l
    
  
   
}


```
