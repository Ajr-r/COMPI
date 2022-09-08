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
