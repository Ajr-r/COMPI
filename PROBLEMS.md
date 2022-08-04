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
# SMALLEST NEXT PALINDROME
```C++
#include<iostream>
using namespace std;
int main(){
    int x;
    string s,se;
     cin>>x;     
      
    while(x--){
        s=to_string(x);
         for(int i =s.size()-1;i>=0;i--){
            se+=s[i];
        }
        if(s==se){
            cout<<se<<endl;
            break;
        }
        se="";
    }

}
```
# 3
Constraints

All indices in this challenge are zero-based.
All the given numbers are non negative and are not greater than 
Output Format

For each pair of  and  values (i.e., for each query), print a single integer that denotes the element located at index  of the array referenced by . There should be a total of  lines of output.

Sample Input

2 2
3 1 5 4
5 1 2 8 9 3
0 1
1 3
Sample Output

5
9
```c++
#include <iostream>
using namespace std;

int main() {
    /* Enter your code here. Read input from STDIN. Print output to STDOUT */ 
    int a,q;
    cin>>a>>q;
    int* ar[a];
    for (int i=0;i<a;i++){
      int e;
      cin>>e;
      ar[i]=new int [e];
      for(int j=0;j<e;j++){
        cin>>ar[i][j];//ar[i][j] represents a int varaible wherease ar[i] is a pointer
    }  
    }  
 while(q--){
  int y,u;
  cin>>y>>u;
  cout<<ar[y][u]<<endl;
 }
}

```
# 4
The first line of input will contain a single integer TT, denoting the number of test cases.
Each test case consists of two lines of input.
The first line of each test case contains a single integer NN, the length of string SS.
The second line of each test case contains the string SS.
Output Format
For each test case, output on a new line the answer — YES if SS is easy to pronounce, and NO otherwise.

Each character of the output may be printed in either uppercase or lowercase. For example, the strings YES, yeS, yes, and YeS will all be treated as identical.
1≤T≤100
1 \leq N \leq 1001≤N≤100
SS contains only lowercase Latin characters, i.e, the characters \{a, b, c, \ldots, z\}{a,b,c,…,z}
Sample 1:
Input
Output
5
5
apple
15
schtschurowskia
6
polish
5
tryst
3
cry
YES
NO
YES
NO
YES
```c++
#include <iostream>
using namespace std;

int main() {
	// your code goes here
	int t,n;
	string s;
	cin>>t;
	while(t--){
		bool f=1;
		int c=0;
		cin>>n;
		cin>>s;

		for(char i:s){
			if(i!='a' and i!='e' and i!='o' and i!='u' and i!='i' ){
				c++;
			}
			else{
				c=0;
			}
		if(c>=4){
			f=0;
			break;
		}
		}
		if(f){
			cout<<"YES"<<endl;
		}
		else{
			cout<<"NO"<<endl;
			c=0;
		}
	}

}
	

```
