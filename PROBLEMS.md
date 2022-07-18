# 1
Write a C++ program to convert specified days into years, weeks and days. Note: Ignore leap year.

Input :
Number of days : 1329


Expected Output :
Years: 3 Weeks: 33 Days: 3
```c++
#include<iostream>
using namespace std;
int main() {
float nodays=1329;
int year=nodays/365;
int week=(nodays-(year*365))/7;
int day=(nodays-((year*365)+(week*7)));
cout<<"number of years "<<year<<" number of week: "<<week<<" number of days is "<<day;
}


```
# 2
Write a C++ program to read an amount (integer value) and break the amount into smallest possible number of bank notes.

Input:
375


Expected Output:
There are:
3 Note(s) of 100.00
1 Note(s) of 50.00
1 Note(s) of 20.00
0 Note(s) of 10.00
1 Note(s) of 5.00
```c++
#include<iostream>
using namespace std;
int main() {
    int x=375;
    int h=x/100;
    int f=(x-h*100)/50;
    int tw=(x-((h*100)+(f*50)))/20;
    int te=(x-((h*100)+(f*50)+(tw*20)))/10;
    int fi=(x-((h*100)+(f*50)+(tw*20)+(te*10)))/5;
    cout<<"There are :"<<endl;
    cout<<h<<"Note(s) of 100.00"<<endl;
    cout<<f<<"Note(s) of 50.00"<<endl;
    cout<<tw<<"Note(s) of 20.00"<<endl;
    cout<<te<<"Note(s) of 10.00"<<endl;
    cout<<fi<<"Note(s) of 5.00"<<endl;
  
}

```
# PALINDROME/STRING REVERSAL
```c++
#include <iostream>
using namespace std;
int main(){
  string s="1221";
  string s1;
  for(int i =0;i<s.size();i++){
    s1+=s[(s.size()-1)-i];
  }
  if(s==s1){
    cout<<"is a palindrome";
  }
  else{
    cout<<"not a palindrome";
  }
  

}

```
