
# Steps to for recursive solution



<img width="303" alt="Screenshot 2022-09-06 141636" src="https://user-images.githubusercontent.com/100711675/188590509-3e3140cd-700e-4be8-96d5-6b3655363bf7.png">



# FACTORAIL

 ```C++
#include <bits/stdc++.h>
# define c cout
# define nl "\n"
using namespace std;

int fact(int n){
    if(n<=0){
        return 1;
    }
    return n*fact(n-1);

     }
 
 ```
  <img width="637" alt="Screenshot 2022-08-28 165810" src="https://user-images.githubusercontent.com/100711675/187071813-c00705c3-fa01-47e9-a29c-93f5b8a36e3a.png">

 ```c++    
     
int fib(int m ){
    if(m==0||m==1){
        return m;
    }

    return fib(m-1)+fib(m-2);
}
int main(){
    int n=5;
    int m=4;
    c<<fact(n)<<nl;
    c<<fib(m)<<nl;
}
 
 ```
 # RECURSION-REVERSING A STRING 
```C++
#include <bits/stdc++.h>
# define c cout
# define nl "\n"
using namespace std;
void reverse(string s){
	if(s.size()==0){
		return;
	}
	string ros=s.substr(1);
	reverse(ros);
	c<<s[0]<<nl;

}
 
int main()
{ 
	string s="goku";
	
	reverse(s);
}
----------------------------------------------
string rev(string s,int n,string r){
    if(n>2){
        return "";
    }
    char t=s[n];
    r=rev(s,n+1,r);
    return r+t;
}

int main()
{
    string s="abc";
    int n=s.size()-1;
    string y="";
     y=rev(s,0,y);
     C<<y<<l

}
```
# TOWER OF HANOI
```c++
#include <bits/stdc++.h>
using namespace std;
# define C cout
# define l "\n";
//if the number disk to be moved at any point is odd the top most disk will move to dest , if even it will move to help...imagine with 2 disks
void towerofhanoi(int n,char src,char dest,char help){
    if(n==0) return;
    C<<n<<" "<< " source "<<src<<" "<<" destination "<<dest<<" "<<" helper "<<help<<l
    towerofhanoi(n-1,src,help,dest);

    C<<"move "<<n<< " from "<<src<<" to "<<dest<<l

         C<<n<<" "<< " source "<<src<<" "<<" destination "<<dest<<" "<<" helper "<<help<<l



    towerofhanoi(n-1,help,dest,src); // again same as the void towerofhanoi(int n,char src,char dest,char help){
}

int main()
{   
    ios_base::sync_with_stdio(false);
    cin.tie(NULL);
    towerofhanoi(3,'a','c','b');
    return 0;
}


```
```
3  source a  destination c  helper b
2  source a  destination b  helper c
1  source a  destination c  helper b
move 1 from a to c
1  source a  destination c  helper b
move 2 from a to b
2  source a  destination b  helper c
1  source c  destination b  helper a
move 1 from c to b
1  source c  destination b  helper a
move 3 from a to c
3  source a  destination c  helper b
2  source b  destination c  helper a
1  source b  destination a  helper c
move 1 from b to a
1  source b  destination a  helper c
move 2 from b to c
2  source b  destination c  helper a
1  source a  destination c  helper b
move 1 from a to c
1  source a  destination c  helper b

```
# TO REMOVE DUPLICATES
```C++
#include <bits/stdc++.h>
# define C cout
# define l "\n";
#define ll long long 
#define ld long double 
using namespace std;
string removedup(string s){
    if(s.length()==0){
        return "";
    }
    char ch=s[0];
    string ans =removedup(s.substr(1));//GOES TILL THE END OF THE STRING AND IN EVERY LOOP THE LETTER IS STORED IN CH AFTER HITTING THE BASE CONDTION WHILE COMMING BACK IT GOES THROUGHT THE IF LOOP
    if(ch==ans[0]){
        return ans;
    }
    return ch+ans;
}
void solve(){
    string s="aaaabbbccc";
    string y=removedup(s);
    C<<y<<l
}
 

  


   



  
 
int main()
{ 
	ios_base::sync_with_stdio(false);
    cin.tie(NULL);
	ll t=1;
	
	while(t--){
		solve();
	}

	return 0;
	
	
}
	

```
# STEPS RECURSIVE
```C++
#include <bits/stdc++.h>
# define C cout
# define l "\n";
#define ll long long 
#define ld long double 
using namespace std;
int steps(int n){
    if(n==1||n==2){
        return n;
    }
    else if(n==3) return 4;// as caluclate there 4 possiblites to climb if there are 3 stairs
    return steps(n-1)+steps(n-2)+steps(n-3);//these possiblilties again branch out like what if you took 1 step initally or 2 step initally
}

void solve(){
    int n=2;
    C<<steps(n)<<l


  
}

int main()
{ 
	ios_base::sync_with_stdio(false);
    cin.tie(NULL);
	ll t=1;
	
	while(t--){
		solve();
	}

	return 0;
	
	
}
	


```
# No. of paths till last grid in matrix
```c++
#include <bits/stdc++.h>
# define C cout
# define l "\n";
#define ll long long 
#define ld long double 
using namespace std;


int path(int n ,int m){
    if(n==1||m==1)return 1;
    return path(n,m-1)+path(m,n-1);
}

void solve(){
    C<<path(4,4)<<l
    
    


  
}

int main()
{ 
	ios_base::sync_with_stdio(false);
    cin.tie(NULL);
	ll t=1;
	
	while(t--){
		solve();
	}

	return 0;
	 
	
}
	


```
# Knapsack
# normal approch

```c++
#include <bits/stdc++.h>
# define C cout
# define l "\n";
# define ll long long 
# define ld long double 
using namespace std;



void solve(){
       int val[] = { 100,50,150};
    int wt[] = { 10, 20, 30 };
    int w=50;
    int sum=0;
    int n=3;
        for(int i=1;i<n;i++){
        for(int j=0;j<n-i;j++){
            if(val[j]<val[j+1]){
                swap(val[j],val[j+1]);
                swap(wt[j],wt[j+1]);
            }
        }
    }
    for(int i=0;i<3;i++){
        if(wt[i]<=w){
            sum+=val[i];
            w-=wt[i];
        }
    }
  C<<sum<<l


  
}

int main()
{ 
	ios_base::sync_with_stdio(false);
    cin.tie(NULL);
	ll t=1;
	
	while(t--){
		solve();
	}

	return 0;
	 
	
}
	


```
# recursive approach
```c++

#include <bits/stdc++.h>
# define C cout
# define l "\n";
# define ll long long 
# define ld long double 
using namespace std;
int knap(int val[],int wt[],int w,int n){
    if(w==0||n==0)return 0;
    if(wt[n-1]>w)return knap(val,wt,w,n-1);
    return max(knap(val,wt,w-wt[n-1],n-1)+val[n-1],knap(val,wt,w,n-1));

}



void solve(){
 
     int val[] = { 100,50,150};
    int wt[] = { 10, 20, 30 };
    int w=50;
    C<<knap(val,wt,w,3)<<l
  
}

int main()
{ 
	ios_base::sync_with_stdio(false);
    cin.tie(NULL);
	ll t=1;
	
	while(t--){
		solve();
	}

	return 0;
	 
	
}
	



```
# printing all subsubtrings

```c++


#include <bits/stdc++.h>
using namespace std;
# define C cout
# define l "\n";
#define ll long long 
#define ld long double 
void wy(string s,string ans){
    if(s.size()==0){
        C<<ans<<l
        return ;
    }
    char ch=s[0];
    wy(s.substr(1),ans);
    wy(s.substr(1),ans+ch);
    

   
}


int main()
{
  string s="abc";
wy(s,"");
    

    


  
}
```
# permutaion
```c++
void permu(string s,string ans){
    if(s.size()==0){
        C<<ans<<l
        return ;
    }
    for(int i=0;i<s.size();i++){
        char ch=s[i];//fixes one char for every loop
        string ros=s.substr(0,i)+s.substr(i+1);
        permu(ros,ans+ch);
    }
}

void solve(){
    string s="abc";
    permu(s,"");

}

```
