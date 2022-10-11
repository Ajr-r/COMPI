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
