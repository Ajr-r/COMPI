# IMPORTANT NOTES
$ odd +/- odd = even,

  even +/- even = even,
  
  odd +/- even = odd,
  
  even +/- odd = odd,
  
  odd x odd = odd,
  
  even x even = even,
  
  odd x even = even,
  
  even x odd = even
  
  
  
$ if n is even the number of even and odd numbers are n/2, if n is odd then count of odd numbers is (n/2)+1 and even is n-n/2+1
  to calculate sum of n odd numbers n*(n+1), if n is even the diff b/w sum of even and odd numbers is n/2 if n is odd then diff is(n+1)/2
  
  
$ max gcd in range of n is n/2

$ if(n&1)==1 its odd else its even

# modulo
```c++
//(a+b)%m=((a%m)+(b%m))%m
//(a*b)%m=((a%m)*(b%m))%m
//(a*b)%m=((a%m)-(b%m)+m)%m
for(int i=0;i<n;i++){
    int sum*=i%m;//same as the formula
    int sum+=i%m;//same as the formula
}

```
# shift operator
```c++
#include <iostream>
using namespace std;
 
int main() {
 
    int x = 19;
    cout<<"x << 1 = "<< (x << 3) <<endl;//multiply x * 2^3
    cout<<"x >> 1 = "<< (x >> 1) <<endl;
    return 0;
}
```


  
  <img width="443" alt="Screenshot 2022-09-14 184750" src="https://user-images.githubusercontent.com/100711675/190165031-91ffd1b0-4902-4cbb-8518-c7058bd5f9bc.png">


```c++

void solve(){
    int x;
    cin>>x;
    if(x%2==0)C<<4<<" "<<x-4;
    else C<<9<<" "<<x-9;   
}

```
# TO FIND SUM TILL N
```C++
 int x=10;
    C<<x*(x+1)/2<<l
```
# LCM AND GCD
```C++
void solve(){
    int x=10,y=20;
    int m=max(x,y);
    while(1){
        if(m%x==0&&m%y==0){
            C<<m<<l
            break;
        }
        m++;
    }
    C<<__gcd(x,y);

}
```
# Balls and boxes
```C++
//if number of balls is equal to or greater than sum of n natural number then it can the boxes can have unique set of balls and with min 1 ball ber box and n is number of boxes
```
# elephant 1,2,3,4,5
```c++

#include<bits/stdc++.h>
using namespace std;
int main()
{
    int n,a;
    cin>>n;
    if(n%5==0)
    {
       a=n/5;
    }
    else
        a=(n/5)+1;
    cout<<a<<endl;
 
}
```

<img width="293" alt="Screenshot 2022-09-24 203849" src="https://user-images.githubusercontent.com/100711675/192105336-0d7d30ef-4a38-4ded-84c0-ba0b00b0f019.png">


```c++
//only works for 2 inputs

def maxHeight(h1, h2):
    return ((h1 * h2) - h1 - h2)
 

lst = input().split(',')
h1 = int(lst[0])
h2 = int(lst[1])
 
print(max(0, maxHeight(h1, h2)))


```
# to find the divisors faster

```c++
	 for(int i=2;i<=sqrt(n);i++){
	     if(n%i==0){
            if(n/i==i){
                v.push_back(i);
                xorsum^=i;
            }
            else{
                v.push_back(i);
                v.push_back(n/i);
                xorsum^=i;
                xorsum^=n/i;
            }
	       
	     }
	 }

```
# to find inside circle in a rightangled triangle
```c++
 return ((P + B - H) * (P + B - H) * (PI / 4));
```
# GFG-doors
Given n doors and n persons. The doors are numbered 1 to n and persons are given id’s numbered 1 to n. Each door can have only 2 status open and closed. Initially all the doors have status closed. Find the final status of all the doors if a person changes the current status of all the doors, i.e. if status open then change to status closed and vice versa, for which he is authorized. A person with id ‘i’ is authorized to change the status of door numbered ‘j’ if ‘j’ is a multiple of ‘i’. 

```c++

// C++ implementation of
// doors open or closed
#include <bits/stdc++.h>
using namespace std;

// Function to check whether 'n'
// has even number of factors or not
bool hasEvenNumberOfFactors(int n)
{
	int root_n = sqrt(n);//number of doors that are opened 

	// if 'n' is a perfect square
	// it has odd number of factors
	if ((root_n*root_n) == n)
		return false;

	// else 'n' has even
	// number of factors
	return true;
}

// Function to find and print
// status of each door
void printStatusOfDoors(int n)
{
	for (int i=1; i<=n; i++)
	{
		// If even number of factors
		// final status is closed
		if (hasEvenNumberOfFactors(i))
			cout << "closed" << " ";

		// else odd number of factors
		// final status is open
		else
			cout << "open" << " ";
	}
}

// Driver program
int main()
{
	int n = 5;
	printStatusOfDoors(n);
	return 0;
}


```
# GFG fourpoint_ssquare
Given coordinates of four points in a plane. Find if the four points form a square or not.
```
Input:
points=(0,0),(0,1),(1,0),(1,1)
Output:
1
Explanation:
These points form a square.

Input:
points=(0,0),(1,1),(1,0),(0,2)
Output:
0
Explanation:
These four points do not form a square.
```

```c++
  int fourPointSquare(vector<vector<int>> points) {
        // code here
        int a = abs(points[0][0] - points[0][1]);
        int b = abs(points[1][0] - points[1][1]);
        int c = abs(points[2][0] - points[2][1]);
        int d = abs(points[3][0] - points[3][1]);
        if(a==0 && a==b && a==c && a==d) return 0;
        if(a+c == b+d) return 1;
        return 0;
    }
```
# GFG Overlapping rectangles
Given two rectangles, find if the given two rectangles overlap or not. A rectangle is denoted by providing the x and y coordinates of two points: the left top corner and the right bottom corner of the rectangle. Two rectangles sharing a side are considered overlapping. (L1 and R1 are the extreme points of the first rectangle and L2 and R2 are the extreme points of the second rectangle).
```
Input:
L1=(0,10)
R1=(10,0)
L2=(5,5)
R2=(15,0)
Output:
1
Explanation:
The rectangles overlap.
Input:
L1=(0,2)
R1=(1,1)
L2=(-2,0)
R2=(0,-3)
Output:
0
Explanation:
The rectangles do not overlap
```
```c++
  int doOverlap(int L1[], int R1[], int L2[], int R2[]) {
        // code here
     
        if(L1[0]>R2[0]||L2[0]>R1[0]) return 0;
        if(R1[1]>L2[1]||R2[1]>L1[1]) return 0;
        return 1;
    }
```
# sum of prime numbers till n
```c++
// C++ program to find sum of primes in
// range from 1 to n.
#include <bits/stdc++.h>
using namespace std;

// Returns sum of primes in range from
// 1 to n.
int sumOfPrimes(int n)
{
	// Array to store prime numbers
	bool prime[n + 1];

	// Create a boolean array "prime[0..n]"
	// and initialize all entries it as true.
	// A value in prime[i] will finally be
	// false if i is Not a prime, else true.
	memset(prime, true, n + 1);

	for (int p = 2; p * p <= n; p++) {

		// If prime[p] is not changed, then
		// it is a prime
		if (prime[p] == true) {

			// Update all multiples of p
			for (int i = p * 2; i <= n; i += p)
				prime[i] = false;
		}
	}

	// Return sum of primes generated through
	// Sieve.
	int sum = 0;
	for (int i = 2; i <= n; i++)
		if (prime[i])
			sum += i;
	return sum;
}

// Driver code
int main()
{
	int n = 978784;
	cout << sumOfPrimes(n);
	return 0;
}


```
# finding the power N^R where n is the no and r is the reverse output it by mod
https://practice.geeksforgeeks.org/problems/power-of-numbers-1587115620/1?page=1&difficulty[]=0&category[]=Divide%20and%20Conquer&sortBy=submissions
```
Input:
N = 2
Output: 4
Explanation: The reverse of 2 is 2
and after raising power of 2 by 2 
we get 4 which gives remainder as 
4 by dividing 1000000007.

Input:
N = 12
Output: 864354781
Explanation: The reverse of 12 is 21
and 1221 , when divided by 1000000007 
gives remainder as 864354781.
```

```c++
    long long power(int N,int R)
    {
       //Your code here
       if(R==0) return 1;//base case
    
    long long temp=power(N,R/2)%mod;//recursive call -> it divides the power by 2
      long long s=(temp*temp)%mod;// when r is even for that loop it return this
      if(R&1>0)return N*s%mod;//if r is odd multiply s with n to get the odd power equivalent
      else return s;
   
       
    }

```
# finding nth fib adn returning its last number faster
```
Input:
N = 5
Output:
5
Explanation:
5th Fibonacci number is 5

Input:
N = 14
Output:
7
Explanation:
14th Fibonacci number is 377
It's last digit is 7
```

```c++
    int fib(int N){
        //code here
        if(N==0)return 0;
          if(N==1)return 1;
            if(N==2)return 1;
        
        long long i=1;
       long long j=1;
        long long t;
        
         for(int k=3;k<=N;k++){
            t=(i+j)%10;
            i=j;
            j=t;
         }
        return t;
    }

```
# GFG message
There are N students in a class, each in possession of a different funny story. 

They want to share funny stories with each other by sending electronic messages. Assume that a sender includes all the funny stories he or she knows at the time the message is sent and that a message may only have one addressee. What is the minimum number of messages they need to send to guarantee that every one of them gets all the funny stories?

```
Input:
2
Output:
2
Explanation:
Person 1 sends a message to 
Person 2, Person 2 sends
message to Person 1.
A total of 2 messages are sent.

Input:
1
Output:
0
Explanation:
No messages are sent
```

```c++
  int minimumMessages(int N){
        // code here 
       return 2*(N-1);//all n-1 guys send message to one guy and that one guy send back all messages -> 2*(n-1) 
    }

```
# finding if a number is in the fubnocci series in O(1)
```c++
#include <bits/stdc++.h>
# define C cout
# define l "\n";
#define ll long long 
#define ld long double 
using namespace std; 
using namespace std;
int main() { 
    int n=377;
     int x=(5*(n*n))-4;//formula
     int y=(5*(n*n))+4;//formula
     if(x==(sqrt(x)*sqrt(x))||y==(sqrt(y)*sqrt(y))) C<<"YES"<<l//checking whether the number obtained is a perfect square or not
     else C<<"NO"<<l<img width="587" alt="Screenshot 2022-10-14 135457" src="https://user-images.githubusercontent.com/100711675/195799868-f8e22152-a7c5-4851-b42c-15e3ce64e5ae.png">

}
```


# infy
<img width="587" alt="Screenshot 2022-10-14 135457" src="https://user-images.githubusercontent.com/100711675/195799996-a8c6a5c1-1c34-42ec-b1e4-36c9223b714a.png">




<img width="591" alt="Screenshot 2022-10-14 135505" src="https://user-images.githubusercontent.com/100711675/195799887-747a9322-5d5d-476c-bf4c-8d27c9167c3d.png">

```c++
#include <bits/stdc++.h>
# define C cout
# define l "\n";
#define ll long long 
#define ld long double 
using namespace std; 
int mod=1000000007;

ll solve(ll n,ll a,ll b,ll c,ll d){
  ll ans=0;
  if(n==0)return 4;
   ll temp1;
  ll temp2;
  while(n>0){
    if(n%2==0){
      ans=((a+c)%mod+(b+d)%mod+a%mod+b%mod)%mod;
     
       temp1=a%mod;
       temp2=b%mod;
      a=(a+c)%mod;
      b=(b+d)%mod;
      c=temp1%mod;
      d=temp2%mod;       
    }
    else{
        ans=((a+b)%mod+(c+d)%mod+a%mod+c%mod)%mod;
     
       temp1=a%mod;
       temp2=c%mod;
      a=(a+b)%mod;
      c=(c+d)%mod;
      b=temp1%mod;
      d=temp2%mod;

    }
    n--;
  }
  return ans;
}
int main() { 
  ll n;
  cin>>n;
    if(n>=0)C<<solve(n,1,1,1,1)<<l 
    else C<<"-1"<<l
}



```
# codechef

<img width="362" alt="Screenshot 2022-10-15 143448" src="https://user-images.githubusercontent.com/100711675/195978512-0b5efdf0-5db9-464e-bf9e-65569c0c8892.png">

<img width="364" alt="Screenshot 2022-10-15 143457" src="https://user-images.githubusercontent.com/100711675/195978514-d1fa1d6d-0569-4132-b66b-6df63e7ae2cd.png">

```c++
#include <bits/stdc++.h>
using namespace std;
# define C cout
# define l "\n";
#define ll long long 
#define ld long double 
void solve(){
float x;
cin>>x;
C<<x-1<<l
   
}

int main()
{   int t=1;
  
    while(t--){
        solve();
    }

}

```
#codchef

<img width="364" alt="Screenshot 2022-10-15 144703" src="https://user-images.githubusercontent.com/100711675/195978927-5c24f8a9-4121-4f2a-88a9-a20b82ef6443.png">

<img width="361" alt="Screenshot 2022-10-15 144711" src="https://user-images.githubusercontent.com/100711675/195978928-935dc727-3197-4738-996f-e2269908fffd.png">


```c++
#include <iostream>
using namespace std;

int main() {
	// your code goes here
	int t;
	cin>>t;
	while(t--){
	    int x,y;
	    cin>>x>>y;
	    if(x==1||y==1)cout<<"NO"<<endl;
        else if(x%2==0&&y%2==0)cout<<"YES"<<endl;
	    else  if(x%2==0&&y%2!=0||x%2!=0&&y%2==0)cout<<"YES"<<endl;
	    else   cout<<"NO"<<endl;
	}
	return 0;
}

````
#codechef

<img width="363" alt="Screenshot 2022-10-15 150306" src="https://user-images.githubusercontent.com/100711675/195979499-ba6ab1cc-fe8c-49a8-b9f1-ac3684bea88a.png">



<img width="359" alt="Screenshot 2022-10-15 150313" src="https://user-images.githubusercontent.com/100711675/195979501-dd7a24cf-7472-409d-8aa7-e449a2d3915f.png">


```c++

#include <bits/stdc++.h>
using namespace std;
#define ll long long 
const int NE=1e5+2;
int dp[NE];
int main() {
	// your code goes here
	ll t;
	cin>>t;
	while(t--){
    int x,y,z;
    cin>>x>>y>>z;
    if(x-y==0)cout<<"YES"<<endl;
    else if(abs(x-y)%z==0&&(abs(x-y)/z)%2==0)cout<<"YES"<<endl;
    else cout<<"NO"<<endl;
   

	
	}
	return 0;
}
```
# codeforces

<img width="479" alt="Screenshot 2022-10-15 191014" src="https://user-images.githubusercontent.com/100711675/195989550-749d7b87-a337-468b-85e1-ca1c06f5fd64.png">


```c++


#include <bits/stdc++.h>
using namespace std;
# define C cout
# define l "\n";
 
int main()
{
    long long n;
    cin >> n;
    if(n%2==0)C<<n/2<<l
    else C<<((n+1)/2)*-1<<l
 
  

```
# infy chem

<img width="454" alt="Screenshot 2022-10-17 173022" src="https://user-images.githubusercontent.com/100711675/196172186-8edf0d0e-ee51-421d-a452-64e4eb38d052.png">


<img width="442" alt="Screenshot 2022-10-17 173031" src="https://user-images.githubusercontent.com/100711675/196172202-83ee05fe-4c0b-40e1-ba39-5be5f5ecde81.png">

```c++
int samChemicals(vector<int> phValue){
    sort(phValue.begin(),phValue.end());
    int sum=1;
    for(int i:phValue){
        if(i<=sum)sum+=i;  
    }
    return sum;
}

```
# hackwithinfy

Paper Sheets 
Sam is handed a rectangular piece of paper with the dimensions h*w, where h denotes height and w denotes width. Sam wants to fold the paper in the fewest possible moves such that its dimensions are h1*w1. The paper could only be folded parallel towards its edges, and the dimensions should be integers after folding. If h=8 and w=4, for example, fold the paper till it's h1, w1 = 6,1. First, fold the long edge 6 units to the side, resulting in a 6*4 paper. And then, Fold the page in three folds along the width 2 units edge to achieve a 6*1 page.

Input Format

First line contains an integer denotes h 

Seconds line contains an integer denotes w 

Third line contains an integer denotes h1

Fourth line contains an integer denotes w1

Constraints

1 <= h, w, h1, w1 <= 10^15

h1 <= h

w1 <= w

Output Format

Print the minimum moves required.

Sample Input:
```
2

3

2

2

0->1

```
```c++
#include <bits/stdc++.h>
# define C cout
# define l "\n";
#define ll long long 
#define ld long double 
using namespace std;
int main() {
    int h,w,h1,w1;
    cin>>h>>w>>h1>>w1;
    int moves=0;
    while(w>w1){
        moves++;
        if(w&1>0){
            w=(w+1)/2;
        }
        else w=w/2;
    }
    while(h>h1){
        moves++;
        if(h&1>0){
            h=(h+1)/2;
        }
        else h=h/2;
    }
    C<<moves<<l
}


```
# infy playstation

<img width="628" alt="Screenshot 2022-10-19 120755" src="https://user-images.githubusercontent.com/100711675/196615438-80f252ba-2b76-470d-b746-0fd0a7e9f3ec.png">


<img width="626" alt="Screenshot 2022-10-19 120813" src="https://user-images.githubusercontent.com/100711675/196615444-a43092c5-72d3-44f7-8b81-ae7399f09244.png">


```c++
#include<bits/stdc++.h>
using namespace std;

double maxProb(int x,int y,int n,int w,double p1,double p2,vector< vector<double>>&dp)
{
if(w<=0)
{
return 1.0;
}
if(n==0&& w>0)
{
return 0.0;
}
if(dp[n][w]!=-1.0)
{
return dp[n][w];
}
double ans1=(maxProb(x,y,n-1,w-x,p1,p2,dp)*p1)+((1.0-p1)*maxProb(x,y,n-1,w,p1,p2,dp));
ans1=max(ans1,(maxProb(x,y,n-1,w-y,p1,p2,dp)*p2)+((1.0-p2)*maxProb(x,y,n-1,w,p1,p2,dp)));


dp[n][w] =ans1;
return dp[n][w];
}
int main()
{
int t;
cin>>t;
while(t--)
{
int x,y,n,w,prod1,prod2;
cin>>x>>y>>n>>w>>prod1>>prod2;
double p1=0.01*prod1;
double p2=0.01*prod2;
vector<vector<double>> dp(n+1,vector<double>(w+1,-1.0));
double ans=maxProb(x,y,n,w,p1,p2,dp);
ans*=100;
cout<<fixed<<setprecision(6)<<ans<<endl;
}

}
```
Leetcode-easy
Given an array of size N-1 such that it only contains distinct integers in the range of 1 to N. Find the missing element.
```
Input:
N = 5
A[] = {1,2,3,5}
Output: 4
Input:
N = 10
A[] = {6,1,2,8,3,4,7,10,5}
Output: 9
```

```c++
// User function template for C++

class Solution{
  public:
    int MissingNumber(vector<int>& array, int n) {
        // Your code goes here
        int sum=(n*(n+1))/2;
        for(int i=0;i<n-1;i++)
        {
            sum=sum-array[i];
        }
        return sum;
    }
};
```
