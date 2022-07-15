# INTRO CODE
```C++  
#include <iostream>//Used to include header files---input output stream
#define g "abc"//same like const
#include "t.cpp"//adding other cpp files
#include "g.cpp"
using namespace t;//adding namespace for ez use 
int f=100;//declaring golbal variable
using namespace std;
string name="arjith";
int main() {
   bool r=false;
   string name="sanjith";
   const int num1=10; //cannot change value after defined
    int num2=50;
    char gender ;
    cout<<"variable from t file : "<<tr<<endl;//with namespace
    cout<<"variable from g file : "<<y::tr<<endl;//without namespace

    cout<<g<<endl;//endl to go to next line
    f=7;//changing global variable
    cout<<::f<<endl;//::to access global variable if globlal and local has same name
    
 
       
       cout<<"enter a name"<<endl;
       cin>>name;//used itt get input from the user
       cout<<"Hi "<<name;
}

```
# DECISION STATMENTS
```C++
#include<iostream>
using namespace std;
int main(){
    int i =-1;
    if(i>=1){
        if(i>5){
            cout<<"i is greater than 5"<<endl;
        }
        else{

    cout<<"i is greater than 1"<<endl;
        }

    }
    else if(i==0){
        cout<<"i is 0";
    }

    else{
        cout<<"in else block"<<endl;
    }

    if(true){
        cout<<"dd"<<endl;
    }

switch (1)
    {

case 1:
    cout<<"you chose option 1";
    break;
case 2:
    cout<<"you chose option 2";
    break;
case 3:
    cout<<"you chose option 3";
    break;
case 4:
    cout<<"you chose option 4";
    break;
default:
    cout<<"you did'nt choose any option";
    break;
    }

}


```
# ITERATION STATEMENTS
```C++
#include<iostream>
using namespace std;
int main(){
    int i =0;
    while(i<10){
        cout<<"hi "<<i<<endl;
        i+=1;
    }
    do{
        cout<<"gg"<<endl;
        i--;
    }while(i>1);
    
    for(int g=1;g<10;g++){
        cout<<g<<endl;
    }

}
```
# ARRAY POINTERS AND REF
```C++
#include<iostream>
using namespace std;


int main()
{

    int art[2][2]={1,2,3,4};//2 dim array no need for brackets
    cout<<art[1][1]<<endl;

    int ar[5]={1,2,3,4,5};//1 dim array
    for(int i=0;i<5;i++){
        cout<<ar[i]<<" ";
    }
    cout<<endl;
    int a=10;
    int *p=&a;// '*' is used to declare a pointer and '&' is used to get address of a value
    cout<<a<<endl;
    cout<<p<<endl;
    cout<<*p<<endl;// again '*' is used to print data stored in the address that the pointer holds
    cout<<&p<<endl;//can also print the address of the pointer
    int b=50;
    int& g=b;//'&' after the datatype indicates a reference variable changing the value for ref var will change the value of original as well
    g=100;
    cout<<g<<endl;
    cout<<b<<endl;

   




}

```
# FUNCTIONS
```C++
#include <iostream>
using namespace std;
void gg(){
    cout<<"from function"<<endl;
}
int add(int x, int y){
    return x+y;

}
int add10(int x,int y){
    x+=10;
    y+=10;
}
int add10withref(int &x,int &y){//passing refernce from actual parameters
    x+=10;
    y+=10;
}
void display(int a[]){
    for(int i=0;i<3;i++){
        cout<<a[i]<<" ";
    }
    cout<<endl;
}
int main(){
    int a[3]={1,2,3};
    display(a);
    int x =1;
    int y=2;
    add10withref(x,y);
    cout<<x<<" "<<y<<endl;
    gg();
    cout<<add(2,4);
}
```
