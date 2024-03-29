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
#LIS 

<img width="465" alt="Screenshot 2022-10-15 201801" src="https://user-images.githubusercontent.com/100711675/195992710-ca90389b-c94a-4321-9468-35b7809587fa.png">


```c++
#include <bits/stdc++.h>
# define C cout
# define l "\n";
#define ll long long 
#define ld long double 
using namespace std; 
const int NE=1e5+2;
vector <int> dp(NE,-1);
vector <int> v;
int lis(int n){
  if(dp[n]!=-1)return dp[n];
  int ans=1;
  for(int i=0;i<n;i++){//iterates from 0 to n on the array if a[i] is smaller than a[n] it will search for next smaller than a[i]
    if(v[i]<v[n]){
      ans=max(ans,lis(i)+1);
    }
  }
  dp[n]=ans;
  return dp[n];
}
int main() {
	// your code goes here
  int n;
  cin>>n;
  for(int i=0;i<n;i++){
    int y;
    cin>>y;
    v.push_back(y);
  }
    int m=0;
  for(int i=0;i<n;i++){
    m=max(m,lis(i));

  }
  C<<m<<l

   
}

```
# coin change

<img width="474" alt="Screenshot 2022-10-15 222804" src="https://user-images.githubusercontent.com/100711675/195998739-1c8974a5-f228-4cf1-9736-dce70dbb270e.png">

```c++
#include <bits/stdc++.h>
# define C cout
# define l "\n";
#define ll long long 
using namespace std; 
const int NE=1e5+2;//dont use this in leet code or inside class instead use dp array
vector <int> dp(NE,-1);
    int cc(vector<int>& coins, int amount) {
  
  if(dp[amount]!=-1)return dp[amount];
      if(amount==0)return 0;
      int ans=INT_MAX;
      for(int i:coins){
        if(amount-i>=0){
          ans=min(ans+0ll,cc(coins,amount-i)+1ll);//adding long long to avoid int overflow

        }
      }
      dp[amount]=ans;
     return dp[amount];
    }
     int coinChange(vector<int>& coins, int amount) {
      int c=cc(coins,amount);
      if(c==INT_MAX)return -1;
      else return c;
        
    }
int main() {
	// your code goes here
  vector <int> v={2};
  C<<coinChange(v,3)<<l
}

```

# knapsack dp

<img width="575" alt="Screenshot 2022-10-17 120359" src="https://user-images.githubusercontent.com/100711675/196105288-cf315446-1416-4986-bc01-334dc582265e.png">

https://atcoder.jp/contests/dp/tasks/dp_d
```
3 8
3 30
4 50
5 60
o->90

5 5
1 1000000000
1 1000000000
1 1000000000
1 1000000000
1 1000000000
0->5000000000

6 15
6 5
5 6
6 4
6 6
3 5
7 2
0->17

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
ll dp[105][100005];
ll knap(ll v[],ll wt[],ll n,ll w){
  if(dp[n][w]!=-1)return dp[n][w];
  if(n==0)return 0;
  if(w-wt[n-1]<0)return knap(v,wt,n-1,w);
  ll ans=max(knap(v,wt,n-1,w),knap(v,wt,n-1,w-wt[n-1])+v[n-1]);
  dp[n][w]=ans;
  return dp[n][w];
}
int main(){
  memset(dp,-1,sizeof(dp));
  ll n,w;
  cin>>n>>w;
  ll v[n];
  ll wt[n];
  for(ll i=0;i<n;i++){
    cin>>wt[i];
    cin>>v[i];

  }
  C<<knap(v,wt,n,w);
 
}

```
# rod cutting
Given a rod of length N inches and an array of prices, price[]. pricei denotes the value of a piece of length i. Determine the maximum value obtainable by cutting up the rod and selling the pieces.
https://practice.geeksforgeeks.org/problems/rod-cutting0840/1
```
Input:
N = 8
Price[] = {1, 5, 8, 9, 10, 17, 17, 20}
Output:
22
Explanation:
The maximum obtainable value is 22 by
cutting in two pieces of lengths 2 and 
6, i.e., 5+17=22.

Input:
N=8
Price[] = {3, 5, 8, 9, 10, 17, 17, 20}
Output: 24
Explanation: 
The maximum obtainable value is 
24 by cutting the rod into 8 pieces 
of length 1, i.e, 8*3=24. 
```
```c++
int dp[1005];
class Solution{
  public:
    int func(int len,int n,int price[]){
        if(dp[len]!=-1)return dp[len];
        if(len==0)return 0;
        int ans=0;
        for(int i=0;i<n;i++){
            if(len-(i+1)>=0){
                ans=max(ans,func(len-(i+1),n,price)+price[i]);
            }
        }
        return dp[len]=ans;
        
    }
    int cutRod(int price[], int n) {
        //code here
        memset(dp,-1,sizeof(dp));
        return func(n,n,price);
     
        
    }
};

```
