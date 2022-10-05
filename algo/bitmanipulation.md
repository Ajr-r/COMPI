# BIT MANUPULATION
The & (bitwise AND) in C or C++ takes two numbers as operands and does AND on every bit of two numbers. The result of AND is 1 only if both bits are 1. 

The | (bitwise OR) in C or C++ takes two numbers as operands and does OR on every bit of two numbers. The result of OR is 1 if any of the two bits is 1. 

The ^ (bitwise XOR) in C or C++ takes two numbers as operands and does XOR on every bit of two numbers. The result of XOR is 1 if the two bits are different. 

The << (left shift) in C or C++ takes two numbers, left shifts the bits of the first operand, the second operand decides the number of places to shift. 

The >> (right shift) in C or C++ takes two numbers, right shifts the bits of the first operand, the second operand decides the number of places to shift. 

The ~ (bitwise NOT) in C or C++ takes one number and inverts all bits of it. 
  

  ```C++
  
  #include <bits/stdc++.h>
using namespace std;
# define C cout
# define l "\n";

//posi-3210
//bin--0101  ex:i=1
int getbit(int x,int i){//to check whether there is a bit in posi i
    return (x&(1<<i))!=0;//1<<i->moves 1 to i posi from right
                        //& operator compares 2 bit if both bit are 1 return 1 else 0
}
int setbit(int x,int i){//sets the bit at posi i to one returns the int value 
    return (x|(1<<i));
}
int clearbit(int x,int i){// unsets the bit in the given posi
    int mask=~(1<<i);
    return mask&x;
}
int updatebit(int x,int i,int n){// removes the bit at the position and sets the n bit at posi i
    int mask=~(1<<i);
    x= mask&x;
    return x|(n<<i);
}
int main(){
    int x=5;//bin->0101
    int i=1;
    C<<getbit(x,i)<<l
    C<<setbit(x,i)<<l
    C<<clearbit(5,2)<<l
    C<<updatebit(5,1,1)<<l


}

  ```
# finding if a number is power of 2
```c++
#include <bits/stdc++.h>
using namespace std;
# define C cout
# define l "\n";
int ispower2(int n){
    if(n==1)return 0;
    return (n&&!(n&n-1));//first n is there if n=0, for any power of 2 in binary form only 1 setbit will be there and n-1 binary form will have right most and after setbit flipped
                        //if doing and operation leads to zero then n is power of 2
}
int main(){
  int n=1;
  C<<ispower2(n)<<l  
}
```
# coun the number of 1s
```c++
#include <bits/stdc++.h>
using namespace std;
# define C cout
# define l "\n";
int count1s(int n){
    int c=0;
    while(n){
        n=n&n-1;//this flip the rightmost and after set bit continously which reduces the number of 1s
        c++;
    }
    return c;
}
int main(){
  int n=8;
  C<<count1s(n)<<l  
}
```
# getting all subsets
```c++
#include <bits/stdc++.h>
using namespace std;
# define C cout
# define l "\n";
void subsets(char a[],int n){
    for(int i=0;i<(1<<n);i++){
        for(int j=0;j<n;j++){
            if(i&(1<<j)){
                C<<a[j]<<" ";
            }
        }
        C<<l
    }
    
}
int main(){
    char a[3]={'a','b','c'};
    subsets(a,3);

}
```
