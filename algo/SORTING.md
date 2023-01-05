# SELECTION SORT
```C++

#include <iostream>

using namespace std;
 
int main(){
    int n=6;
    int ar[n]={6,5,4,3,2,1};
    for(int i=0;i<n-1;i++){
        for(int j=i+1;j<n;j++){
            if(ar[i]>ar[j]){
                swap(ar[i],ar[j]);
            }
        }
    }
   
    for(int r:ar){
        cout<<r<<" ";
    }

}
```
#  bubble sort
```c++
#include <iostream>

using namespace std;
 
int main(){
    int n=6;
    int ar[n]={6,5,4,3,2,1};
    for(int i=1;i<n;i++){
        for(int j=0;j<n-i;j++){
            if(ar[j]>ar[j+1]){
                swap(ar[j],ar[j+1]);
            }
        }
    }
   
    for(int r:ar){
        cout<<r<<" ";
    }

}
```
# GFG Top K Frequent Elements in Array-easy
```
Given a non-empty array of integers, find the top k elements which have the highest frequency in the array. If two numbers have the same frequency then the larger number should be given preference. 

Note: Print the elements according to the frequency count (from highest to lowest) and if the frequency is equal then larger number will be given preference.

Input:
N = 6
nums = {1,1,1,2,2,3}
k = 2
Output: {1, 2}

Input:
N = 8
nums = {1,1,2,2,3,3,3,4}
k = 2
Output: {3, 2}
Explanation: Elements 1 and 2 have the
same frequency ie. 2. Therefore, in this
case, the answer includes the element 2
as 2 > 1.

```
```c++
   static bool compare(pair<int,int> p1,pair<int,int> p2){//p1 is the second men in the array...if want ascending then interchange p1 and p2
        if(p1.second==p2.second)return p1.first>p2.first;
        return p1.second>p2.second;
    }
    vector<int> topK(vector<int>& nums, int k) {
        // Code here
        vector <int> v;
        map <int,int>m;
        for(int i:nums)m[i]++;
        vector <pair<int,int>> f(m.begin(),m.end());//can directly store data to vector like this
        sort(f.begin(),f.end(),compare);//using user defined sort func
        for(int i=0;i<k;i++)v.push_back(f[i].first);
        return v;
        
    }
```
