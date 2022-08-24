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
