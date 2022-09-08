# SPIRAL MATRIX
```C++
#include <bits/stdc++.h>
using namespace std;
int main() {
    int r=5;
    int c=6;
    int k=0;
    cout<<(r*c)<<"\n";
   int m1[r][c]={{1,5,7,9,10,11},
                {6,10,12,13,20,21},
                {9,25,29,30,32,41},
                {15,55,59,63,68,70},
                {40,70,79,81,95,105}};
    int rs=0,re= r-1,cs=0,ce=c-1;
    int count=0;
    
    while(rs<=r){
        //from top left to right
       
        for(int i=cs;i<=ce;i++){
            if(count>=r*c){//to restrict other elements from printing
                break;
            }
            cout<<m1[rs][i]<<" ";
            count++;
            
        }
        rs++;
        //from top to down
        for(int i=rs;i<=re;i++){
             if(count>=r*c){
                break;
            }
            cout<<m1[i][ce]<<" ";
            count++;
            
            
        }
        ce--;
        //from down right to left
          for(int i=ce;i>=cs;i--){
            
         if(count>=r*c){
                break;
            }
            cout<<m1[re][i]<<" ";
            count++;
            
        }
        re--;
         //from down to up
          for(int i=re;i>=rs;i--){
            if(count>=r*c){
                break;
            }
            cout<<m1[i][cs]<<" ";
            count++;
            
        
        }
        cs++;
       
    }
    cout<<"\n";
    cout<<count;           
   
}

```
