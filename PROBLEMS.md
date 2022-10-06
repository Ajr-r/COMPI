
# to find if number prime or not
```c++
#include <bits/stdc++.h>
# define C cout
# define l "\n";
#define ll long long 
#define ld long double 
using namespace std; 
int main()
{
    int x=73;
    bool f=1;
for(int i=2;i*2<=x;i++){

    if(x%i==0){
        f=0;
        
        C<<"NO"<<l
        break;
    }
   
        

}
if(f) C<<"YES"<<l
}

```
# Y-shape pattern
```c++
#include <bits/stdc++.h>
using namespace std;

vector<string> yShapedPattern(int n) {
        // code here
        vector<string> s;
        string se="";
        int y=n;
		
        for(int i=0;i<n/2;i++){
            for(int k=0;k<i;k++)
            se+=" ";
            for(int j=0;j<=y;j++){
				
                if(j==0)se+="*";
                else if(j==y)se+="*";
                else se+=" ";
                
            }
            y-=2;
			
            s.push_back(se);
			se="";
        }
		for(int i=0;i<n/2;i++)se+=" ";
		se+="*";
        for(int i=0;i<n/2;i++)s.push_back(se);
        return s;
    }
int main() {
	vector <string> s;
	s=yShapedPattern(4);
	for(auto i:s){
		cout<<i<<endl;
	}

	
}


```
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
# infy1
Problem Statement
read_more
Consider a non-empty input string instr and generate outstr, a hash value such that:

For each of the vowels in instr
Multiply their index by 5. For the obtained result res, add the consecutive odd numbers starting from 1 up to res to get outnum
If outnum is not a single digit, reduce it to a single digit by repetitively adding all the digits in outnum
Replace the corresponding vowel in instr with outnum
If no single vowel exists in instr return -1.

Input format:

Read instr from the standard input stream.

Output format:

Print the hash generated value to the standard output stream.

Sample Input	Sample Output	Explanation
Program		Pr7gr7m	
For the given input instr the vowels are ‘o’ and ‘a’.

Vowel ‘o’:
Vowel ‘o’ is at index 2. Multiplying the index 2 with 5 results in 10. Adding the consecutive odd numbers starting with 1 up to 10,i.e. 1, 3, 5, 7 and 9 gives outnum ,25. Reducing outnum to single digit results in 7. Replacing ‘o’ with 7 gives ‘Pr7gram’

Vowel ‘a’:
Vowel ‘a’ is at index 5. Multiplying the index 5 with 5 results in 25. Adding the consecutive odd numbers starting with 1 up to 25, i.e. 1, 3, 5, 7, 9, 11, 13, 15, 17, 19, 21, 23, 25 gives outnum ,169. Reducing outnum to single digit results in 7. Replacing ‘a’ with 7 gives ‘Pr7gr7m’ and hence the output

Pg Dn btn prssd by RK	-1	
There exists no vowel in the given input instr and hence the output is -1

Languages: C#,Python 3,Java,C++,C,Scala,Go,Perl,Bash,TypeScript,Plain JavaScript,R,PHP,Ruby,Python,Clojure
```C++
#include <iostream>

using namespace std;

int main() {
  string s;
  getline(cin,s);
  int res=0;
  int tr=0;
  for(int i=0;i<s.size();i++){
  int outnum=0;
    if(s[i]=='a'||s[i]=='A'||s[i]=='e'||s[i]=='E'||s[i]=='i'||s[i]=='I'||s[i]=='o'||s[i]=='O'||s[i]=='u'||s[i]=='U'){
      tr=1;
      res=i*5;
      for(int j=1;j<=res;j++){
        if(j%2!=0){
          outnum+=j;

        }
      }
      while(1){

      if(to_string(outnum).size()>1){
        
        string w=to_string(outnum);
        outnum=0;
        for(char q:w){
          outnum+=q-'0';  
        }
      }
        else{
          break;
        }
        
     
      }
     s[i]=outnum+(int)'0';
    }
  }
  if(tr){

  cout<<s<<endl;
  }
  else{
  cout<<-1<<endl;

  }


    return 0;
}    



```
# BINARY CONVERSION
```C++
#include <bits/stdc++.h>
using namespace std;
 
int main()
{   
    int x=45;
    string s="";
    while(x>0){//conerting decimal base 10 to binary
        s+=to_string(x%2);
        x/=2;
    }
    reverse(s.begin(),s.end());//should reverse the order
    cout<<s<<endl;
    int y=0;
    for(int i=0;i<s.size();i++){//converting from binary to decimal base 10
        if(s[i]=='1'){
            y+=pow(2,i);
        }
    }
    cout<<y;
}

```
# INFY ASS 1
Problem Statement
read_more
Given an array of integers, find the equilibrium index of the array.

In case of an array, A, its equilibrium index, i, is such that

(A[0]+A[1]+……+A[i-1]) =  (A[i+1]+A[i+2]+……..+A[n-1]) where 0 < i < n-1

Exception cases:

0 should be considered as the equilibrium index, if A[1]+A[2]+…….+A[n-1] = 0
n-1 should be considered as the equilibrium index, if A[0]+A[1]+…….+A[n-2] = 0
-1 should be considered as the equilibrium index, if the condition for equilibrium index is not found to be true for any acceptable value of i.
Input format:

Read the array of elements from the standard input stream

Output format:

Print the equilibrium index to the standard output stream

Sample Input		Sample Output	Explanation
3,-4, 2, -1,-3, 2, 1	2	For the given input, the equilibrium index is 2 as sum of the elements to the left of index 2 is -1 and right of index 2 is also -1
```C++
#include <bits/stdc++.h>
using namespace std;
 
int main()
{
    // Get the string
    int f=1;
    int ch1=0;
    string str ;
    getline(cin,str);
 
    vector<int> v;
 
    // Get the string to be taken
    // as input in stringstream
    stringstream ss(str);
 
    // Parse the string
    for (int i; ss >> i;) {
        v.push_back(i);
        ch1+=i;
        
        if (ss.peek() == ',')
            ss.ignore();
    }
   
  
    if(ch1-v[0]==0){
        
        cout<<0;
        return 0;
    }
    else if(ch1-v[v.size()-1]==0){
         cout<<v.size()-1;
        return 0;
    }
    else{

    
   
   for(int j=1;j<v.size();j++){
    int fh=0;
    int sh=0;
    for(int y=0;y<j;y++){
        fh+=v[y];
    }
    for(int g=j+1;g<v.size();g++){
        sh+=v[g];
    }
    if(fh==sh){
        cout<<j<<endl;
        f=0;
        break;

    }
   }
   if(f){
    cout<<-1<<endl;
   }
    }
}

```
# Sum of subarrays
```c++
#include <bits/stdc++.h>
using namespace std;
 
int main()
{ 
  int sum=0;
  int n=5;//Number of subarrays is n*(n+1)/2
  int ar[n]={1,2,0,7,2};
  for(int i=0;i<n;i++){
    for(int j=i;j<n;j++){
      sum+=ar[j];
     cout<<sum<<" ";

  }
  sum=0;
  }

  
      
     
    }

```
# longest diff in array
```c++
#include <bits/stdc++.h>
using namespace std;
 
int main()

{ 
  int c=2;
  int cmax=0;
  int cdiff=0;

  int pdiff=0;

  int n=7;//Number of subarrays is n*(n+1)/2
  int ar[n]={10,15,10,15,10,15,10};
    pdiff=abs(ar[0]-ar[1]);
  for(int i=1;i<n-1;i++){
    cdiff=abs(ar[i]-ar[i+1]);
    cout<<cdiff<<" "<<endl;
    if(cdiff==pdiff){

      c++;
      cout<<"in if "<<c<<endl;
     cmax=max(cmax,c);
    }
    else{
      c=1;
      pdiff=cdiff;
    }
   
  
  }
  cout<<cmax<<endl;
}

```
# NUMBER OF OCCURENCE
```C++
#include <bits/stdc++.h>
using namespace std;
 
int main()

{ 
	string s="hello world";
	map<char,int> m;
	map<char,int> ::iterator it;

	for(int i=0;i<s.size();i++){
		if(m.find(s[i])==m.end()){//find goes through the entire map if it is equal to map.end()then the element is not in the map
			m[s[i]]=1;
		}
		else{
			m[s[i]]++;
		}
	}
	for(it=m.begin();it!=m.end();it++){
		cout<<it->first<<" "<<it->second<<endl;
	}




}
```
# fibinocci sequence
```c++
#include <bits/stdc++.h>
using namespace std;
 
int main()

{ 	
	int m=8;
	int n1=0;
	int n2=1;
	int n3=0;
	cout<<n1<<endl<<n2<<endl;
	for(int i=2;i<m;i++){
		n3=n2+n1;
		cout<<n3<<endl;
		n1=n2;
		n2=n3;
	}
}
	
```
# armstrong number
```c++
#include <bits/stdc++.h>
using namespace std;
 
int main()

{ 	
	int n=153;
	string s=to_string(n);
	int r=0;
	for(char i:s){
		r+=(i-'0')*(i-'0')*(i-'0');
	}
	cout<<r;
	cout<<__gcd(x,y);//using a function

	
}
	
```
# apna 1
<img width="606" alt="Screenshot 2022-08-23 190751" src="https://user-images.githubusercontent.com/100711675/186172663-53ae99cd-519d-4777-a968-61df3d878525.png">



```c++
#include <bits/stdc++.h>
using namespace std;
 
int main(){
  int n=7;
  int a[n]={1,5,3,4,3,5,6};
  int amin=INT_MAX;
  int y=*max_element(a,a+n);
   int ar[y]={-1};
  for(int i =0;i<y;i++){
    ar[i]=-1;
  }
  for(int i =0;i<y;i++){
    if(ar[a[i]]!=-1){
      amin=min(amin,ar[a[i]]);
    }
    else{
      ar[a[i]]=i;
    }
  
  }
  if(amin==INT_MAX){
    cout<<-1;
  }
  else{
    cout<<amin;
  }

 

}

```
# apna 2
<img width="614" alt="Screenshot 2022-08-23 195727" src="https://user-images.githubusercontent.com/100711675/186184547-441be63b-e00d-4f6f-9260-3f039e5dd294.png">


```c++
#include <bits/stdc++.h>
using namespace std;
 
int main(){
  int n=5;
 int s=3;
  int a[n]={1,2,3,7,5};
  int i=0;
  int j=0;
  int sum=0;
  while(sum<s){
    sum+=a[j];
    j++;
  if(sum==s){
    cout<<i+1<<" "<<j;
    return 0;
  }
  }

sum=0;
i=j-1;
while(i>=0){
  sum+=a[i];
  if(sum==s){
    cout<<i+1<<" "<<j;
    return 0;
  }
  i--;
    
  }

  cout<<-1;

  

}

```
# apna 3
<img width="506" alt="Screenshot 2022-08-23 212840" src="https://user-images.githubusercontent.com/100711675/186205766-6bdc4eb5-9d48-494b-b8db-4f8f12212cb2.png">


```c++
#include <bits/stdc++.h>
using namespace std;

int main() {//find the lowest missing positive number ex 123...2 is missing the given array
  int n=6;
  int ar[n]={0,-9,1,3,-4,5};
  int y =*max_element(ar,ar+n);
  int b[y];//boolean array to mark the number which are present ex:-going to 3rd index and marking it 1
  for(int i=0;i<y;i++){
    b[i]=0;
  }
  for(int i=0;i<y;i++){
    if(ar[i]>=0){
        b[ar[i]]=1;
    }
  }
  for(int i=0;i<y;i++){
    if(b[i]==0){//first element which is missing
        cout<<i;
        break;
    }
  }

  
   
    
  
}


```
# infy ass 4
<img width="332" alt="Screenshot 2022-08-25 230806" src="https://user-images.githubusercontent.com/100711675/186732597-a7115833-d29a-445c-b5bf-cc37fe13a53d.png">
<img width="319" alt="Screenshot 2022-08-25 230849" src="https://user-images.githubusercontent.com/100711675/186732680-51beb644-9144-40d6-a24f-f5a76344cb3c.png">



```c++

#include <bits/stdc++.h>

using namespace std;
int main(){
    int t,x,y;
    cin>>t;
    string s;
    while(t--){
        
        cin>>x>>y;
        cin>>s;
        map <char,int> m;
        for(char i:s){
            if(m.find(i)==m.end()){////also can just use m[i]++ instead of the if condition to store the occurence
                m[i]=1;
            }
            else{
                m[i]++;
            }
            if(m[i]<=y){
                cout<<i;
                
            }
        }
    cout<<"\n";

    }
}

```
# Infyq


<img width="315" alt="Screenshot 2022-09-07 131051" src="https://user-images.githubusercontent.com/100711675/188818784-bde5f1b0-41f4-465c-8797-5c2d1eb2d31a.png">



<img width="307" alt="Screenshot 2022-09-07 131128" src="https://user-images.githubusercontent.com/100711675/188818902-9cd8b0d6-6b85-4af5-b71d-3aa353388581.png">


```c++
void solve(){
	int c=0;
	int k;
	cin>>k;
	string s;
	cin.ignore();
	getline(cin,s);
	vector <int> v;
	map <string,int> m;
	stringstream ss(s);
	string sub;
	while(ss.good()){
		getline(ss,sub,',');
		m[sub]++;
	}
	for(auto i:m){
		v.push_back(i.second);
	}
	sort(v.begin(),v.end());
	for(int i=0;i<v.size();i++){
			int t=v[i];
			v[i]-=k;
			k-=t;

		if(v[i]>0){
			c++;
		}
	}
	
	C<<c<<l

}

```


# INFY Lexico beads

<img width="330" alt="Screenshot 2022-09-07 221106" src="https://user-images.githubusercontent.com/100711675/188933652-3f493683-1197-4250-a47c-45c4a4c60875.png">

<img width="301" alt="Screenshot 2022-09-07 221042" src="https://user-images.githubusercontent.com/100711675/188933662-4fe8950e-09f0-4323-9cd3-16b699156b04.png">




```c++

void solve(){
    int k;
    cin>>k;
    string s;
    cin>>s;
    string mina="z";
    if(k<2){//if k is more than 1 then suffling will generate same result as sorting
        for(int i=0;i<s.length();i++){
            char temp=s[0];
            s.erase(0,1);
            s+=temp;
            mina=min(mina,s);
        }
        C<<mina<<l
    }
    else{
        sort(s.begin(),s.end());
        C<<s<<l
    }

}
  

```

# infy ass10


<img width="308" alt="Screenshot 2022-09-11 144731" src="https://user-images.githubusercontent.com/100711675/189520252-3f4daa23-9eeb-4733-8e46-ab440b2109b3.png">


```c++
#include <iostream>
#include <string>
using namespace std;

int main() {
  
    string inputString;
   cin>>inputString;
    int hh=stoi(inputString.substr(0,2));
    if( inputString[8]=='P'){
        if(hh==12){
             cout<<12;
        for(int i=2;i<=7;i++){
            cout<< inputString[i];
        }
        }
        else{
        cout<<12+hh;
        for(int i=2;i<=7;i++){
            cout<< inputString[i];
        }
        cout<<endl;
        }
    }
    else{
         if(hh==12){
             cout<<"00";
               for(int i=2;i<=7;i++){
            cout<< inputString[i];
        }
         }
         else{
                 for(int i=0;i<=7;i++){
            cout<< inputString[i];
        }
         }
       
    
        cout<<endl;
    }
    
    
    return 0;
}

```
#infy ass5

<img width="322" alt="Screenshot 2022-09-11 200005" src="https://user-images.githubusercontent.com/100711675/189533037-45a416e4-ed5b-4da6-b72d-9da0af77d9c7.png">

<img width="308" alt="Screenshot 2022-09-11 195956" src="https://user-images.githubusercontent.com/100711675/189533048-212f2cf6-94b1-4ff0-9c09-e4fe915d5910.png">


```c++

void solve(){
    int n;
    cin>>n;
    vector <int> v;
   
    int sum=0;
    for(int i=0;i<n;i++){
        int y;
        cin>>y;
        v.push_back(y);
        
    }
    sort(v.begin(),v.end());
    while (n>3)
    {   
        sum+=min((v[0]+(v[1]*2)+v[n-1]),((v[0]*2)+v[n-1]+v[n-2]));//1st conditon is when 1st element is not that much less than the rest of the element
      
        n-=2;
    }
    if(n==3)sum+=v[0]+v[1]+v[2];
    else if(n==2)sum+=v[1];
    else sum+=v[0];
    C<<sum<<l
    }
```
# infyass 7

<img width="323" alt="Screenshot 2022-09-12 121450" src="https://user-images.githubusercontent.com/100711675/189589781-1a6578a1-b033-4c9f-8769-5df53c9f685a.png">


<img width="291" alt="Screenshot 2022-09-12 121509" src="https://user-images.githubusercontent.com/100711675/189589806-cc38aed4-7b67-441d-94ec-49be5461c7af.png">


```
6
3 6
1 6
7 11
2 15
5 8
1 2
```
```c++
void solve(){
    int n;
    cin>>n;
    vector<int> v1;
    vector<int> v2;
   
    int maxc=-1;
    int ans=INT_MAX;
    int count=0; 
    int maxcount=-1;
   
    bool f=0;

    
    for(int i=0;i<n;i++){
        int y;
        cin>>y;
        v1.push_back(y);

       
        int u;
        cin>>u;
        v2.push_back(u);

  
     
        

    }
    

    for( int j=0;j<n;j++){
        for(int i=0;i<n;i++){
            if(v1[j]>=v1[i]&&v1[j]<=v2[i]){
                count++;
            }
        }
           
            if(count>maxcount){
                maxcount=count;
                ans=v1[j];
              
            }
            else if(count==maxcount){
                if(ans>v1[j]){
                    ans=v1[j];
                }
            }
             count=0;
      
    }
    C<<ans<<" "<<maxcount<<l

   
    
}

```
# infy q
You are given an integer N. Now, you need to find if there exists two prime numbers (X,Y) such that X^2+y^2=N. If (X,Y) exists then output the minimum value of X+Y otherwise print -1.

Input format: The first line contains an integer, N, denoting the value of N described in the problem.

Constraints: 1<=N<=10^9.

Sample Input:

input: 7
output: -1
explanation: for N=7 no such X,Y exists.

input: 34
output: 8
explanation: X=5 and Y=3 satisfy the condition 25+9=34.

input: 13
output: 5
explanation: X=2 and Y=3 satisfy the condition 4+9=13.

```c++

#include <bits/stdc++.h>
# define C cout
# define l "\n";
#define ll long long 
#define ld long double 
using namespace std; 
bool isprime(int x){
    bool f;
    if(x==1){
        return 1;
    }
    for(int i=2;i*i<=x;i++){

    if(x%i==0){
        f=0;
        
        return 0;
    }
   
        

}
if(f) return 1;

}


int main()
{   bool f=1;
    int r;
    cin>>r;
    map <int,int>m;
    for(int i=2;i*i<=r;i++){
        if(isprime(i)){
            m[i*i]++;
        }
    }
   if(m.size()<=1) {
   
    C<<"-1"<<l
    f=0;
   }
   else{
    for(auto i:m){
       
        if(i.first<r){ 
            auto y=m.find(r-i.first);
            if(y->first!=i.first&&y!=m.end()){
                C<<sqrt(y->first)+sqrt(i.first)<<l
                f=0;
                break;


            }
        }
    }
   }
   if(f){
    C<<-1<<l
   }
   

}
```
# infy ez

<img width="509" alt="Screenshot 2022-09-13 214611" src="https://user-images.githubusercontent.com/100711675/189953658-f0a47c50-d92f-4442-8f4b-370cc655f5e5.png">


```c++
#include <bits/stdc++.h>
# define C cout
# define l "\n";
#define ll long long 
#define ld long double 
using namespace std; 
int main()
{
      vector <int> vp;
      vector <int> vn;
      string s;
      cin>>s;
      int sum=0;
      stringstream ss(s);
      string sub;
      while(ss.good()){
        getline(ss,sub,',');
        int r=stoi(sub);
        if(r>=0) vp.push_back(r);
        else vn.push_back(r);
      }
      sort(vp.begin(),vp.end(),greater<int>());
      sort(vn.begin(),vn.end());
      for(int i=0;i<vp.size();i++){
        sum+=abs(vp[i]-vn[i]);
      }
      int i=0;
      int j=vp.size()-1;
      while(i<j){
        sum+=abs(vn[i]-vn[j]);
        i++;
        j--;
      }
      C<<sum<<l
}

```
# CC 1600

<img width="524" alt="Screenshot 2022-09-15 140052" src="https://user-images.githubusercontent.com/100711675/190355527-53c8a3ad-8304-4d0d-ba83-0a55277d1a34.png">


```
4
6 4
2 2 3 3 2 2
1 1
1
5 3
1 2 3 4 5
4 3
6 12 18 24

```

```c++
void solve(){
    int n,k;
    cin>>n>>k;
    int a[n];
    int b[n];
    int g=0,m=0,c=0;
    for(int i=0;i<n;i++){
        cin>>a[i];
        g=__gcd(g,a[i]);//to get the gcd of all numbers
    }
    bool f=1;
    for(int i:a){
        m=__gcd(m,i);//checks the gcd of sub arrays
        if(m==g){
            c++;
            m=0;// if gcd is same then reset the gcd for next pair
            if(c>=k){// for inputs like 1 1 1 4 5
                C<<"YES"<<l
                f=0;
                break;
            }
        }

    }
    if(f)C<<"NO"<<l

}



```

# infy hungry fish
```c++

#include <bits/stdc++.h>
using namespace std;
# define C cout
# define l "\n";
int main(){
    int x=10;
    int a[]={9,20,25,100};
    sort(a,a+4);
    int c=0;
    for(int i:a){
        if(i<x){
            x+=i;
        }
        else {
            if(i<x+(x-1)){
                x+=x-1;
                x+=i;
                c++;
            }
            else{
                c++;

            } 
        }

    }
    C<<c<<l
}
```
# infy teamdivision

<img width="299" alt="Screenshot 2022-09-20 131409" src="https://user-images.githubusercontent.com/100711675/191197838-9f4cc762-d78b-424f-b5d5-71eb18c54689.png">


<img width="86" alt="Screenshot 2022-09-20 131529" src="https://user-images.githubusercontent.com/100711675/191198122-1f0695c3-c379-4970-b01a-0b05d48052ec.png">



```
Input:
87,100,28,67,68,41,67,1

output
229 230
```
```c++
int diff(vector <int> v,int n,int s1,int s2,int lens1,int lens2){
    if(n==0){
        if(abs(lens2-lens2)>1){
            return INT_MAX;
        }     
        return abs(s1-s2);
    }
     return min(diff(v,n-1,s1,s2,lens1,lens2),diff(v,n-1,s1+v[n-1],s2-v[n-1],lens1+1,lens2-1));
}
void solve(){
    string s;
    getline(cin,s);
    stringstream ss(s);
    string sub;
    vector <int> v;
    int sum=0;
    while(ss.good()){
        getline(ss,sub,',');
        v.push_back(stoi(sub));
        sum+=stoi(sub);
    }
    int n=v.size();
    int mindiff=diff(v,n,0,sum,0,n);
    C<<(int)(((float)sum/2)-(float)mindiff/2)<<" "<<(int)(((float)sum/2)+(float)mindiff/2)<<l
}
```
# infy codecrack

<img width="305" alt="Screenshot 2022-09-24 200016" src="https://user-images.githubusercontent.com/100711675/192103623-6296c96d-a2a5-4b4c-a5b3-25305acb8763.png">

<img width="286" alt="Screenshot 2022-09-24 200047" src="https://user-images.githubusercontent.com/100711675/192103639-5f297a19-2f8d-487c-b7cc-55845c478f9b.png">


```
input:-
Array : 10.0.1.45 -/d/in/intheclass,10.0.1.45-/a/facts/final/bhgahf,10.3.54.123-/d/xyz/bcc/yes

Array : 10.3.54.123 -/d/in/intheclass,10.0.1.45-/a/facts/final/bhgahf,10.3.54.123-/d/xyz/bcc/yes

output:-
10.0.1.45
10.3.54.123

```
```c++
#include <bits/stdc++.h>
using namespace std;
# define C cout
# define l "\n";
#define ll long long 
#define ld long double 
int main(){
    string s;
    getline(cin,s);
    string se="";
    for(char i:s){
        if(isdigit(i)||i=='.'||i=='-'){
            se+=i;
        }
    }
    map <string,int> m;
    string maxs;
    int maxe=INT_MIN;
    stringstream ss(se);
    string sub;
    while(ss.good()){
        getline(ss,sub,'-');
        m[sub]++;
    }
    for(auto i:m){
        if(i.second>maxe){
            maxe=i.second;
            maxs=i.first;
        }    
    }
    C<<maxs;
}


```
# infy ccc 4

<img width="293" alt="Screenshot 2022-09-24 203849" src="https://user-images.githubusercontent.com/100711675/192142447-1402f245-f477-4d4d-8b03-df8e522616c4.png">


```
input:-
101000011 5
1100000100111 6
10101010101111010101 4
```

```c++

#include <bits/stdc++.h>
using namespace std;
# define C cout
# define l "\n";
#define ll long long 
#define ld long double 
int main(){
string s;
cin>>s;
int d;
cin>>d;
int i=0;
int c=0;
bool f=1;
while(i<s.size()-1){
  C<<c<<" "<<i<<l
     if(s[i+d]=='1'){
        c++;
        i+=d;
        continue;

    }
       else if(s[i+2]=='1'){
        c++;
        i+=2;
        continue;

    }
        else if(s[i+1]=='1'){
        c++;
        i+=1;
        continue;

        }
        
    C<<-1<<l
    f=0;
    break;

}
if(f){
    C<<c<<l
}



 

}

```

