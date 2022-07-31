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
# STRING
```C++
#include<iostream>
#include <list>


using namespace std;
int main(){
    char a[50];//string is also list of char
    cin.get(a,50);//used to get all inputs in 0ne go,but use the other one
    for(int i=0;i<50;i++){
        cout<<a[i]<<endl;
    }
    string str;
    int a;
    getline(cin,str);//also gets entire line use this 
    cout<<str.size();
}

```
# ENUMERATE AND STRUCTERS
```C++
#include<iostream>
using namespace std;

enum week{// used to create user defined data types and defualt values start from 0 and increase for next var
    sun=1,
    mon=2,
    tue=3,
    wed=2131231,
    thu=5,
    fri=6,
    sat=7,

};

struct student//same as class with minor diff
{
    string name;
    int age;
    string dept;

};

int main(){
    student s;
    s.age=23;
    s.dept="mech";
    s.name="arjith";
    cout<<s.age<<endl;
    cout<<wed;
    
}

```
# OOPS

```C++
#include<iostream>
using namespace std;
class student{ 
    int rollno;//memebers are private by default
    string name;
    string dept;

   public:
   student(){
    cout<<"in parameterless constructor";
   }
   student(int rollno,string name,string dept){
        cout<<"in parameterized constructor"<<endl;
        this->name=name;
        this->rollno=rollno;
        this->dept=dept;

   }
    void setRollno(int roll){
        this->rollno=roll;
    }
     void setdept(string roll){
        this->dept=roll;
    }
     void setname(string roll){
        this->name=roll;
    }
    string getname(){
        return this->name;
    }
      string getdept(){
        return this->dept;
    }
      int getroll(){
        return this->rollno;
    }
    void display(){
        cout<<"hi my name is "<<name<<" i am from "<<dept<<" department and my rollno. is "<<rollno<<endl;
    }

    

};
int main(){
    student s1;
    s1.setname("arjith");
    s1.setdept("Mech");
    s1.setRollno(12345);
    cout<<s1.getdept()<<endl;
    cout<<s1.getname()<<endl;
    cout<<s1.getroll()<<endl;
    s1.display();
    cout<<"------------using constructor------------"<<endl;
    student s2(333,"sanjith","BBA");
    s2.display();

    
    

}

```
# STATIC AND FRIEND FUNC
```C++
#include <iostream>
using namespace std;
    class gg{
        public:
        static int counter;//static var only declaration is allowed 
        static void t(){//static method
            cout<<"in static method"<<endl;
        }
        gg(){
            counter++;
            cout<<counter<<endl;
        }


    }; int gg::counter=0;//should be initialized outside the class
class name{

    string namee;
    public:
    name(string n){
        namee=n;
    }
    friend void disp(name);//used to get private members of class & can also use friend class used to get private var and methods

};
void disp(name ne){//implementation of friend class should pass an object
    cout<<ne.namee<<endl;
}
int main(){
    int i =10;
    while(i--){
        gg g;

    }
    cout<<gg::counter<<endl;
    gg::t();
    name e("arjith");
    disp(e);
}

```
# INHERITENCE
```C++

#include <iostream>
using namespace std;

    class f{//base class
        public:
        string name;
        void d(){
            cout<<"from parent class"<<endl;
        }
    };
    class g :public f{//derived class
        public:
     
        void s(){
            cout<<"from child class"<<endl;
        }

    };
    int main(){
        g g;
        g.name="arjith";
        g.d();
        g.s();
    }



```
# MEMORY ALLOCATION
```c++
#include <iostream>
using namespace std;
int main(){
int* p=(int*)malloc(sizeof(int)); //malloc is used allocate memory from heap and returns a void pointer therferore should typecaste to int pointer n store it
//also has garbage vaule in the allocated memory
free(p);//garbage collector is not in c++ so should manually free memory to prevent memory leak
p=(int*)malloc(100*sizeof(int));//memory allocated 100*8bytes
*p=20;//assigning value
cout<<*p;
int* arr=(int*)calloc(4,sizeof(int));//gives u 4 contiguous memory location and intialises the value to zero
free(arr);
free(p);
}
```
