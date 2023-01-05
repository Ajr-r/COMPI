# GFG
Given an array of N integers arr[] where each element represents the max length of the jump that can be made forward from that element. Find the minimum number of jumps to reach the end of the array (starting from the first element). If an element is 0, then you cannot move through that element.

Note: Return -1 if you can't reach the end of the array.
```
Input:
N = 11 
arr[] = {1, 3, 5, 8, 9, 2, 6, 7, 6, 8, 9} 
Output: 3 
Explanation: 
First jump from 1st element to 2nd 
element with value 3. Now, from here 
we jump to 5th element with value 9, 
and from here we will jump to the last. 


Input :
N = 6
arr = {1, 4, 3, 2, 6, 7}
Output: 2 
Explanation: 
First we jump from the 1st to 2nd element 
and then jump to the last element.
```
```c++
#include <bits/stdc++.h>
# define C cout
# define l "\n";
#define ll long long 
#define ld long double 
using namespace std;
    int minJumps(int a[], int n){
		if(a[0]==0)return -1;
		if(n<=1)return 0;
		int maxr=a[0];
		int steps=a[0];
		int jumps=1;
		int i=1;
		while(i<n){//goes till the end of the array
			if(i==n-1)return jumps;
			maxr=max(maxr,i+a[i]);
			steps--;
			if(steps==0){
				jumps++;
				if(maxr==i)return -1;
				steps=maxr-i;
			}
			i++;
		}
	return 0;   
    }
void solve(){	
	int n=6;
	int a[n]={1, 4, 3, 2, 6, 7} ;
	C<<minJumps(a,n)<<l
 
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
# GFG Kadane's Algorithm
```
Given an array Arr[] of N integers. Find the contiguous sub-array(containing at least one number) which has the maximum sum and return its sum.

Input:
N = 5
Arr[] = {1,2,3,-2,5}
Output:
9
Explanation:
Max subarray sum is 9
of elements (1, 2, 3, -2, 5) which 
is a contiguous subarray.

Input:
N = 4
Arr[] = {-1,-2,-3,-4}
Output:
-1
Explanation:
Max subarray sum is -1 
of element (-1)

```
```c++
    long long maxSubarraySum(int a[], int n){
        
        // Your code here
        long long m=INT_MIN;
        long long sum=0;
        for(int i=0;i<n;i++){
            sum+=a[i];
            m=max(m,sum);
            if(sum<0)sum=0;

        }
        return m;
    }
```
# GFG Leaders in an array
```
Given an array A of positive integers. Your task is to find the leaders in the array. An element of array is leader if it is greater than or equal to all the elements to its right side. The rightmost element is always a leader. 

Input:
n = 6
A[] = {16,17,4,3,5,2}
Output: 17 5 2
Explanation: The first leader is 17 
as it is greater than all the elements
to its right.  Similarly, the next 
leader is 5. The right most element 
is always a leader so it is also 
included.

Input:
n = 5
A[] = {1,2,3,4,0}
Output: 4 0

```
```c++
    vector<int> leaders(int a[], int n){
        // Code here
         vector <int> v;
         v.push_back(a[n-1]);
         int m=a[n-1];
         for(int i=n-2;i>=0;i--){
             if(a[i]>=m){
                 v.push_back(a[i]);
                 m=a[i];
             }
         }
         reverse(v.begin(),v.end());
         return v;
     
    }

```
