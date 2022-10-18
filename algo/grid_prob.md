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
#infy forest

<img width="579" alt="Screenshot 2022-10-18 194710" src="https://user-images.githubusercontent.com/100711675/196456351-c7d3c4b8-0bdf-4ece-b473-89f13cd5c9e6.png">

<img width="627" alt="Screenshot 2022-10-18 194724" src="https://user-images.githubusercontent.com/100711675/196456409-f99c0a0d-2b2a-4870-906c-102db64d9848.png">

```

5
T T T W W
T W W T T
T W W T T
T W T T T
W W T T T

o->10
```
```c++
#include <bits/stdc++.h>
# define C cout
# define l "\n";
#define ll long long 
#define ld long double 
using namespace std;
const int NE=10000;
char a[NE][NE];
int ci=0;
int herd(int i,int j,int n,int ans){
    if(i<0||j<0)return 0;
    if(i>=n||j>=n||a[i][j]=='W'||a[i][j]=='Q')return 0;
    ci++; 
    a[i][j]='Q';
    herd(i+1,j,n,ans);    
    herd(i,j+1,n,ans);
    herd(i-1,j,n,ans);
    herd(i,j-1,n,ans);
    return ans;
}
int main() {
    int n;
    cin>>n;
    int count=0;
    for(int i=0;i<n;i++){
        for(int j=0;j<n;j++){
            cin>>a[i][j];
    }
    }
    int ans=-1;
      for(int i=0;i<n;i++){
        for(int j=0;j<n;j++){
           herd(i,j,n,0);
           ans=max(ans,ci);
           ci=0;
    }
    }
     if(ans)C<<ans<<l
     else C<<-1<<l   
}


```



