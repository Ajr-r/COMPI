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


