GFG-EASY
Given an array arr[] of N positive integers. Push all the zeros of the given array to the right end of the array while maitaining the order of non-zero elements.
```
Input:
N = 5
Arr[] = {3, 5, 0, 0, 4}
Output: 3 5 4 0 0
Explanation: The non-zero elements
preserve their order while the 0
elements are moved to the right.

Input:
N = 4
Arr[] = {0, 0, 0, 4}
Output: 4 0 0 0
Explanation: 4 is the only non-zero
element and it gets moved to the left.
```
```c++
//istead moving zeros we will move the numbers to the front, j will keep the index of first occuring 0
	void pushZerosToEnd(int arr[], int n) {
	    // code here
	    int j=0;
	    for(int i=0;i<n;i++){
        if(arr[i]!=0)swap(arr[j++],arr[i]);
	}
	}

```
GFG-Basic-rotatem array
Given an array of size N. The task is to rotate array by D elements where D ≤ N.
```
Input:
N = 7
Arr[] = {1, 2, 3, 4, 5, 6, 7}
D = 2
Output: 3 4 5 6 7 1 2
Explanation: 
Rotate by 1: [2, 3, 4, 5, 6, 7, 1]
Rotate by 2: [3, 4, 5, 6, 7, 1, 2]

Input:
N = 4
Arr[] = {1, 3, 4, 2}
D = 3
Output: 2 1 3 4


```
```c++
    void leftRotate(int arr[], int n, int d) {
        // code here
     reverse(arr,arr+d);
     reverse(arr+d,arr+n);
     reverse(arr,arr+n);
    }
```
# GFG rotate array
```
Given an array of size n and multiple values around which we need to left rotate the array. How to quickly print multiple left rotations?
Input : 
arr[] = {1, 3, 5, 7, 9}
k1 = 1
k2 = 3
k3 = 4
k4 = 6
Output : 
3 5 7 9 1
7 9 1 3 5
9 1 3 5 7
3 5 7 9 1

Input : 
arr[] = {1, 3, 5, 7, 9}
k1 = 14 
Output : 
9 1 3 5 7

```
```c++
// C++ Implementation For Print Left Rotation Of Any Array K
// Times

#include <bits/stdc++.h>
#include <iostream>
using namespace std;
// Function For The k Times Left Rotation
void leftRotate(int arr[], int k, int n)
{

	// Stl function rotates takes three parameters - the
	// beginning,the position by which it should be rotated
	// ,the end address of the array
	// The below function will be rotating the array left	
	// in linear time (k%arraySize) times
	rotate(arr, arr + (k % n), arr + n);
	
	// Print the rotated array from start position
	for (int i = 0; i < n; i++)
		cout << arr[i] << " ";
	cout << "\n";
}
// Driver program
int main()
{
	int arr[] = { 1, 3, 5, 7, 9 };
	int n = sizeof(arr) / sizeof(arr[0]);
	int k = 2;

	// Function Call
	leftRotate(arr, k, n);


	return 0;
}


```
# GFG key pair
```
Given an array Arr of N positive integers and another number X. Determine whether or not there exist two elements in Arr whose sum is exactly X.
Input:
N = 6, X = 16
Arr[] = {1, 4, 45, 6, 10, 8}
Output: Yes
Explanation: Arr[3] + Arr[4] = 6 + 10 = 16

Input:
N = 5, X = 10
Arr[] = {1, 2, 4, 3, 6}
Output: Yes
Explanation: Arr[2] + Arr[4] = 4 + 6 = 10

```
```c++
	bool hasArrayTwoCandidates(int arr[], int n, int x) {
	    // code here
	 set <int> s;
	 for(int i=0;i<n;i++){
	     if(s.find(x-arr[i])!=s.end())return 1;
	     s.insert(arr[i]);
	 }
	 return 0;
	}
```
# GFG dupes
```
Given a sorted array A[] having 10 elements which contain 6 different numbers in which only 1 number is repeated five times. Your task is to find the duplicate number using two comparisons only.
Input: 
A[] = {1, 1, 1, 1, 1, 5, 7, 10, 20, 30}
Output: 1

Input: 
A[] = {1, 2, 3, 3, 3, 3, 3, 5, 9, 10}
Output: 3


```
```c++
   if(A[4]==A[3])return A[4];
   return A[5];

```
# GFG longest incresing subarray
```
Given an array containing n numbers. The problem is to find the length of the longest contiguous subarray such that every element in the subarray is strictly greater than its previous element in the same subarray.'

Input:
n = 9
a[] = {5, 6, 3, 5, 7, 8, 9, 1, 2}
Output:
5

Input:
n = 10
a[] = {12, 13, 1, 5, 4, 7, 8, 10, 10, 11}
Output:
4

```
```c++
  long int lenOfLongIncSubArr(long int a[], long int n) {
        if(n==1)return 1;
       int c=0;
        int j=1;
        int m=INT_MIN;
        for(int i=0;i<n;i++){
            if(j==n)break;
            if(a[j]>a[i]){
                c++;
                m=max(m,c);
            }
            else{
                c=0;
            }
            j++;
        }
        if(m==INT_MIN)return 1;
        return m+1;
    }
```
# GFG type of array-basic
```
You are given an array of size N having no duplicate elements. The array can be categorized into the following:
1.  Ascending
2.  Descending
3.  Descending Rotated
4.  Ascending Rotated
Your task is to return which type of array it is and the maximum element of that array.
Input :
N = 5 
A[] = { 2, 1, 5, 4, 3}
Output :
5 3
Explanation:
Descending rotated with maximum
element 5 
Input :
N = 5
A[] = { 3, 4, 5, 1, 2}
Output : 
5 4
Explanation:
Ascending rotated with maximum element 5 

```
```c++
    pair<long long, int> maxNtype(long long a[], long long n)
    {
        //code here.
      int inc=0,dec=0;
      int j=1;
      int m=*max_element(a,a+n);
      for(int i=0;i<n;i++){
         if(j==n)break;
         if(a[j]>a[i])inc++;
         else dec++;
         j++;
      }
      if(inc==0||dec==0){
          if(inc==0) return {m,2};
          else return {m,1};
      }
      if(inc>dec)return {m,4};
      else return {m,3};
    }

```
# GFG min dist b/w 2 numbers
```
You are given an array A, of N elements. Find minimum index based distance between two elements of the array, x and y.
Input:
N = 4
A[] = {1,2,3,2}
x = 1, y = 2
Output: 1
Explanation: x = 1 and y = 2. There are
two distances between x and y, which are
1 and 3 out of which the least is 1.

Input:
N = 7
A[] = {86,39,90,67,84,66,62}
x = 42, y = 12
Output: -1
Explanation: x = 42 and y = 12. We return
-1 as x and y don't exist in the array.
```
```c++
   int minDist(int a[], int n, int x, int y) {
        // code here
        int c=0;
        int mi=INT_MAX;

       int xi=-1; 
       int yi=-1;
        for(int i=0;i<n;i++){
            if(a[i]==x){
                xi=i;
                
            }
            if(a[i]==y){
                yi=i;
            }
            if(xi!=-1&&yi!=-1)mi=min(abs(xi-yi),mi);
        }
        if(mi!=INT_MAX)return mi;
        return -1;
        
           
            
     
    }
```
