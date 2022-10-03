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
# N Queen
```c++

#include <bits/stdc++.h>
using namespace std;
# define C cout
# define l "\n";
bool issafe(int** a,int x,int n,int col){
    
    for(int i=x;i>=0;i--){
        if(a[i][col]==1)return false;
    }
    int i=x;
    int y=col;
    while(i>=0&&y>=0){
        if(a[i][y]==1)return false;
        i--;
        y--;
    }
    i=x;
    y=col;
     while(i>=0&&y<n){
        if(a[i][y]==1)return false;
        i--;
        y++;
    }
    return true;
}

bool queen(int** a,int x,int n){
    if(x>=n) return true;
    
    for(int col=0;col<n;col++){
        if(issafe(a,x,n,col)){
            a[x][col]=1;
            
            if(queen(a,x+1,n))return true;
            a[x][col]=0;

        }
    }
    return false;
}

int main(){
    int n;
    cin>>n;
    int** a=new int*[n];
    for(int i=0;i<n;i++){
        a[i]=new int[n];
        for(int j=0;j<n;j++){
            a[i][j]=0;
        }
    }
    queen(a,0,n);
    for(int i=0;i<n;i++){
        for(int j=0;j<n;j++){
           C<<a[i][j]<<" ";
        }
        C<<l
    }

}

```
