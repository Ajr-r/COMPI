#   BINARY SEARCH
```C++
#include <iostream>

using namespace std;
 
int main()

{int n=6;
 int ar[n]={1,2,3,4,5,6};
 int key=10;
 int e=n;
 int s=0;

    while(s<=e){
        int mid=(e+s)/2;
        if (ar[mid]==key){
            cout<<mid+1<<endl;
            break;
        }
        else{
            if(ar[mid]>key){
                e=mid-1;//adding 1 here so that if the element if not found e will be reduced less than s and the while loop will terminate same for s but oppo
            }
            else{
                s=mid+1;
            }
        }
    }
    cout<<"end";
}
```
# SELECTION SORT
```C++

#include <iostream>

using namespace std;
 
int main(){
    int n=6;
    int ar[n]={6,5,4,3,2,1};
    for(int i=0;i<n-1;i++){
        for(int j=i+1;j<n;j++){
            if(ar[i]>ar[j]){
                swap(ar[i],ar[j]);
            }
        }
    }
   
    for(int r:ar){
        cout<<r<<" ";
    }

}
```
#  bubble sort
```c++
#include <iostream>

using namespace std;
 
int main(){
    int n=6;
    int ar[n]={6,5,4,3,2,1};
    for(int i=1;i<n;i++){
        for(int j=0;j<n-i;j++){
            if(ar[j]>ar[j+1]){
                swap(ar[j],ar[j+1]);
            }
        }
    }
   
    for(int r:ar){
        cout<<r<<" ";
    }

}
```
# FINDIND A ELEMENT IN 2D SORTED ARRAY
```C++
#include <bits/stdc++.h>
using namespace std;
int main() {
    int n1=3;
    int n2=4;
    int k=0;
   int m1[n1][n2]={{1,2,3,4},
                {5,6,7,8},
                {9,10,11,12},};
    int r=0,c=n2-1;
    bool f=0;
    while(r<n1&&c>=0){//only works for sorted 2d array and choose r n c as only top right corner or bottom left corner element
        if(m1[r][c]==k){
            f=1;
            break;
        }
        else if(m1[r][c]>k){
            c--;
        }
        else{
            r++;
        }
    }
    if(f)
    cout<<"found";
    else
    cout<<"not found";
}


```
# SPIRAL MATRIX
```C++
#include <bits/stdc++.h>
using namespace std;
int main() {
    int r=5;
    int c=6;
    int k=0;
    cout<<(r*c)<<"\n";
   int m1[r][c]={{1,5,7,9,10,11},
                {6,10,12,13,20,21},
                {9,25,29,30,32,41},
                {15,55,59,63,68,70},
                {40,70,79,81,95,105}};
    int rs=0,re= r-1,cs=0,ce=c-1;
    int count=0;
    
    while(rs<=r){
        //from top left to right
       
        for(int i=cs;i<=ce;i++){
            if(count>=r*c){//to restrict other elements from printing
                break;
            }
            cout<<m1[rs][i]<<" ";
            count++;
            
        }
        rs++;
        //from top to down
        for(int i=rs;i<=re;i++){
             if(count>=r*c){
                break;
            }
            cout<<m1[i][ce]<<" ";
            count++;
            
            
        }
        ce--;
        //from down right to left
          for(int i=ce;i>=cs;i--){
            
         if(count>=r*c){
                break;
            }
            cout<<m1[re][i]<<" ";
            count++;
            
        }
        re--;
         //from down to up
          for(int i=re;i>=rs;i--){
            if(count>=r*c){
                break;
            }
            cout<<m1[i][cs]<<" ";
            count++;
            
        
        }
        cs++;
       
    }
    cout<<"\n";
    cout<<count;           
   
}

```
# RECURSION
Steps to for recursive solution



<img width="303" alt="Screenshot 2022-09-06 141636" src="https://user-images.githubusercontent.com/100711675/188590509-3e3140cd-700e-4be8-96d5-6b3655363bf7.png">





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
	


```
# TOWER OF HANOI
```C++
#include <bits/stdc++.h>
using namespace std;
# define C cout
# define l "\n";

void towerofhanoi(int n,char src,char dest,char help){
    if(n==0) return;
    towerofhanoi(n-1,src,help,dest);
    C<<"move from "<<src<<" to "<<dest<<l
    towerofhanoi(n-1,help,dest,src);
}

int main()
{   
    ios_base::sync_with_stdio(false);
    cin.tie(NULL);
    towerofhanoi(3,'a','c','b');
    return 0;
}

```
# TO FIND SUM TILL N
```C++
 int x=10;
    C<<x*(x+1)/2<<l
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
