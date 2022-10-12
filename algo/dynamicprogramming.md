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
