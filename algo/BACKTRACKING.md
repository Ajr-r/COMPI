# Rat in a maze

```
input:-
1 0 1 0 1
1 1 1 1 1
0 1 0 1 0
1 0 0 1 1
1 1 1 0 1

output:-
1 0 0 0 0
1 1 1 1 0
0 0 0 1 0
0 0 0 1 1
0 0 0 0 1
```
```c++
#include <bits/stdc++.h>
using namespace std;
# define C cout
# define l "\n";
const int m=5;
bool issafe(int** a,int x,int y,int n){
    if(x<n&&y<n&&a[x][y]==1)return 1;
    return 0;
}

bool ratinmaze(int** a,int** s,int x,int y,int n){
    if(x==(n-1)&&y==(n-1)){
        s[x][y]=1;
        return true;
    }

    if(issafe(a,x,y,n)){
        s[x][y]=1;
        if(ratinmaze(a,s,x+1,y,n)){
            C<<x<<" "<<y<<l
            return true;
        }
        if(ratinmaze(a,s,x,y+1,n)){
                      C<<x<<" "<<y<<l
            return true;
        }
        s[x][y]=0;
        return false;

    }
    return false;



}


void solve(){
    int n=5;
    int** a=new int*[n];
    for(int i=0;i<n;i++){
        a[i]=new int[n];
    }
    for(int i=0;i<n;i++){
        for(int j=0;j<n;j++){
            cin>>a[i][j];
        }
    } 
    int** s=new int*[n];
    for(int i=0;i<n;i++){
        s[i]=new int[n];
    }
    for(int i=0;i<n;i++){
        for(int j=0;j<n;j++){
          s[i][j]=0;
        }
    } 
        
    ratinmaze(a,s,0,0,n);
    C<<"------------------------"<<l
    for(int i=0;i<n;i++){
        for(int j=0;j<n;j++){
                C<<s[i][j]<<" ";
                }  
                      C<<l
    }
   
   
}
int main()
{   
    ios_base::sync_with_stdio(false);
    cin.tie(NULL);
    int t=1;
    while(t--){
        solve();
    }

    return 0;
}


```
