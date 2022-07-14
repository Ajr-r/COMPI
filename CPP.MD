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
