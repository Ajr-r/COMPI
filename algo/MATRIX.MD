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
# TRANSPOSE OF A MATRIX
```C++
#include <bits/stdc++.h>
using namespace std;
int main() {
   int ar[3][3]={{1,2,3},
                {1,2,3},
                {1,2,3}};
    for(int i=0;i<3;i++){

    for(int j=i;j<3;j++){///j=i because to traverse only top right triangle ex:-1,2,3,2,3,3
        if(i!=j){
            swap(ar[i][j],ar[j][i]);
        }
    }
    }
    for(int i=0;i<3;i++){

    for(int j=0;j<3;j++){
     
            cout<<ar[i][j]<<" ";
   
    }
        cout<<"\n";
    }

}

```
# ADDING 2 MATRIX
```C++
#include <bits/stdc++.h>
using namespace std;
int main() {
    int n1=3;
    int n2=4;
    int n3=3;
   int m1[n1][n2]={{2,4,1,2},
                {8,4,3,6},
                {1,7,9,5},};
    int m2[n2][n3]={{1,2,3},
                    {4,5,6},
                    {7,8,9},  
                    {4,5,6},}  ;
    int ans[n1][n3];
    for(int i=0;i<n1;i++){
        for(int j=0;j<n3;j++){
            ans[i][j]=0;

            for(int k=0;k<n2;k++){//common row ex:-n2
                ans[i][j]+=m1[i][k]*m2[k][j];

    }
        }

}
 for(int i=0;i<n1;i++){
        for(int j=0;j<n3;j++)
            cout<<ans[i][j]<<" ";
            cout<<"\n";
}
}

```
