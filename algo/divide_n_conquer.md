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
