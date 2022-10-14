# finding fib with dp// memoization
```c++
#include <bits/stdc++.h>
# define C cout
# define l "\n";
#define ll long long 
#define ld long double 
using namespace std; 
const int NE=1e5+2;//10^5+2
long long dp[NE];//create a dp array / lookup table
int fib(int n){
    if(n==1||n==2)return 1;
    if(dp[n]!=-1)return dp[n];//if fin number is calculated for nth value it will take from the array
    dp[n]= fib(n-1)+fib(n-2);//if not in array it will do normal recusrion n set the fib value for n
    return dp[n];
}
int main()
{
    memset(dp,-1,sizeof(dp));
    dp[1]=1;//using this no need for base case in recusion
    dp[2]=1;
   C<<fib(8)<<l
   
}

``` 
# finding fib with dp// tabulation
```c++


#include <bits/stdc++.h>
# define C cout
# define l "\n";
#define ll long long 
#define ld long double 
using namespace std; 
const int NE=1e5+2;


int main()
{
   int n=12;
   int dp[n+1];
   dp[0]=0;
   dp[1]=1;
   dp[2]=1;
   for(int i=3;i<=n;i++){
    dp[i]=dp[i-1]+dp[i-2];
   }
C<<dp[n]<<l
       
   
   
    
    
}



```
# frog

<img width="575" alt="Screenshot 2022-10-14 221846" src="https://user-images.githubusercontent.com/100711675/195899820-88df06ff-3b86-4b87-b59c-7ecb9612c53d.png">


```
5 3
10 30 40 50 20
o->30

3 1
10 20 10
o->20

2 100
10 10
o->0

10 4
40 10 20 70 80 10 20 70 80 60
o->40
```
```c++
#include <bits/stdc++.h>
# define C cout
# define l "\n";
#define ll long long 
#define ld long double 
using namespace std;
const int NE=1e5+10;
int a[NE];
int dp[NE];
int k;
int frog(int n){
  if(n==0)return 0;
  int cost=INT_MAX;
  if(dp[n]!=-1)return dp[n];
 for(int i=1;i<=k;i++){
  if(n-i>=0){
  cost=min(cost,frog(n-i)+abs(a[n]-a[n-i]));// for frog 1 (moves allowed is 1 and 2) just use two recussive calls like n-1 and n-2
  }
 }
  dp[n]=cost;
  return dp[n];

}
int main()
{ 
	int n;
  cin>>n>>k;
  memset(dp,-1,sizeof(dp));
  for(int i=0;i<n;i++)cin>>a[i];	
  C<<frog(n-1);
}
	



```

