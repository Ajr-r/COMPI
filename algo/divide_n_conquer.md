# GFG Subarray with given sum
Given an unsorted array A of size N that contains only non-negative integers, find a continuous sub-array which adds to a given number S.
In case of multiple subarrays, return the subarray which comes first on moving from left to right.
https://practice.geeksforgeeks.org/problems/subarray-with-given-sum-1587115621/1
```
Input:
N = 5, S = 12
A[] = {1,2,3,7,5}
Output: 2 4
Explanation: The sum of elements 
from 2nd position to 4th position 
is 12.

Input:
N = 5, S = 12
A[] = {1,2,3,7,5}
Output: 2 4
Explanation: The sum of elements 
from 2nd position to 4th position 
is 12.
```
```c++
//follow the exact condition sequence
 vector<int> subarraySum(int arr[], int n, long long s)
    {
        // Your code here
        vector <int> v;
        int sum=0,j=0;
        for(int i=0;i<n;i++){
            sum+=arr[i];
            if(sum==s){//this condition block is optional 
                v.push_back(j+1);
                v.push_back(i+1);
                return v;
            }
            while(sum>s&&j<i){
                sum-=arr[j];
                j++;
            }
             if(sum==s){
                v.push_back(j+1);
                v.push_back(i+1);
                return v;
            }
            
        }
       v.push_back(-1);
       return v;
    
    }

```
# GFG finding an element in sorted and rotated array
Given a sorted and rotated array A of N distinct elements which is rotated at some point, and given an element key. The task is to find the index of the given element key in the array A.

https://practice.geeksforgeeks.org/problems/search-in-a-rotated-array4618/1?page=1&difficulty[]=0&category[]=Divide%20and%20Conquer&sortBy=submissions
```
Input:
N = 9
A[] = {5, 6, 7, 8, 9, 10, 1, 2, 3}
key = 10
Output:
5
Explanation: 10 is found at index 5.

Input:
N = 4
A[] = {3, 5, 1, 2}
key = 6
Output:
-1
Explanation: There is no element that has value 6.

```

```c++
    int search(int a[], int l, int h, int key){
        // l: The starting index
        // h: The ending index, you have to search the key in this range
        
        while(l<=h)
        {
            int mid=(l+h)/2;
            if(a[mid]==key) return mid;
            if(a[mid]>=a[l]){
                if(key>=a[l]&&key<=a[mid]){
                    h=mid-1;
                }
                else l=mid+1;
            }
            else{
                 if(key>=a[mid]&&key<=a[h]){
                    l=mid+1;
                }
                else h=mid-1;
                
            }
            
        }
        return -1;
    
      
   
    }


```
# GFG sliding doors
given and array and k find the maximum subset with k number of elements

```c++
#include <bits/stdc++.h>
# define C cout
# define l "\n";
#define ll long long 
#define ld long double 
using namespace std; 
int main()
{
    int n=9;
    int a[] = { 1, 4, 2, 10, 2, 3, 1, 0, 20 };
    int k = 4;
    int sum=0;
    for(int i=0;i<k;i++)sum+=a[i];//adds element till k
    int msum=-1;
     for(int i=k;i<n;i++){//adds element for index k as well as removes element from start--the sum of k elemenst move like sliding door
        sum+=a[i];
        sum-=a[i-k];
        msum=max(msum,sum);

     }
     C<<sum<<l
 
    
}


```
#GFG Hereos vs villains


<img width="449" alt="Screenshot 2022-10-13 111209" src="https://user-images.githubusercontent.com/100711675/195511398-89d1a078-05c7-4b7f-9c1a-7e84837970f8.png">


<img width="453" alt="Screenshot 2022-10-13 111223" src="https://user-images.githubusercontent.com/100711675/195511406-9d28dc9d-5d92-4b8e-8fae-17ea8aa6d91f.png">


```c++


#include <bits/stdc++.h>
# define C cout
# define l "\n";
#define ll long long 
#define ld long double 
using namespace std; 
using namespace std;

int main() {
  int nvil,nhero,hh;
  cin>>nvil>>nhero>>hh;
  int a[nvil];
  int vsum=0;
  for(int i=0;i<nvil;i++){
    cin>>a[i];
    vsum+=a[i];
  }
  int hsum=nhero*hh;
  int c=0;
  for(int i=0;i<nvil;i++){
      if(vsum<=hsum){
        break;
      }
      vsum-=a[i];
      c++;
  }
 
C<<c<<l
}

```
GFG-Meduim
Given an array A[] and positive integer K, the task is to count total number of pairs in the array whose sum is divisible by K.
```
Input : 
A[] = {2, 2, 1, 7, 5, 3}, K = 4
Output : 5
Explanation : 
There are five pairs possible whose sum
is divisible by '4' i.e., (2, 2), 
(1, 7), (7, 5), (1, 3) and (5, 3)

Input : 
A[] = {5, 9, 36, 74, 52, 31, 42}, K = 3
Output : 7 
Explanation : 
There are seven pairs whose sum is divisible by 3, 
i.e, (9, 36), (9,42), (74, 52), (36, 42), (74, 31), 
(31, 5) and (5, 52

```
```c++
    long long countKdivPairs(int a[], int n, int k)
    {
        //code here
        long long ans=0;
        map <int,int> m;
        for(int i=0;i<n;i++){
            int r=a[i]%k;
            if(r!=0)
            ans+=m[k-r];
            else ans+=m[0];
            m[r]++;
            
        }
        return ans;
    }
```
