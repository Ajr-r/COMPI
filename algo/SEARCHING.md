
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
GFG 3 element sum to 0
```
Given an array arr[] of n integers. Check whether it contains a triplet that sums up to zero. 
Input: n = 5, arr[] = {0, -1, 2, -3, 1}
Output: 1
Explanation: 0, -1 and 1 forms a triplet
with sum equal to 0.
Input: n = 3, arr[] = {1, 2, 3}
Output: 0
Explanation: No triplet with zero sum exist

```
```c++

    bool findTriplets(int arr[], int n)
{
    sort(arr,arr+n);
    for(int i=0;i<n;i++){
        int x=-arr[i];
        int j=i+1;
        int k=n-1;
        while(j<k){
            if(arr[j]+arr[k]==x)return 1;
            else if(arr[j]+arr[k]<x)j++;
            else k--;
        }
    }
    return 0;
   
}
```
