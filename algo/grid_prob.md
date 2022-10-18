# infy hard- sheep
<img width="443" alt="Screenshot 2022-10-18 190300" src="https://user-images.githubusercontent.com/100711675/196445000-459429b4-6847-4954-a37a-4214ab00e31d.png">

<img width="445" alt="Screenshot 2022-10-18 190310" src="https://user-images.githubusercontent.com/100711675/196445031-0a9756f8-26b3-44fc-9074-ba6448a33783.png">

<img width="453" alt="Screenshot 2022-10-18 190320" src="https://user-images.githubusercontent.com/100711675/196445053-e0a0003c-0600-4ec8-b9e7-9595c92b147a.png">

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
