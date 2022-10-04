# BIT MANUPULATION
  

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
