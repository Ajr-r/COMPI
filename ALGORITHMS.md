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
                e=mid-1;
            }
            else{
                s=mid+1;
            }
        }
    }
    cout<<"end";
}
```
