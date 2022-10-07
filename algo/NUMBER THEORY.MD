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
