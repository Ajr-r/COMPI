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
