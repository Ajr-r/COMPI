
# IMPORTNANT POINT
!! dont compare string.size() to -1 it will give wrong reading

!! Trying to erase a element in a array which is for loop it will skip the next element after erasing due to index relocation better to store the wanted value in diff array

!!sometime if the getline() is not working properly use cin.ignore(), also cin.ignore() sometime remove the first element

!!find function in unordered set is faster than binary search 

!!unordererd data structures are faster than order structure ex:- unordered set and unordered map

!!use int** a to pass matrix to functions

!!sometime if the getline() is not working properly use cin.ignore()

!!In order to reach the conditon limit faster mess with i in condition part in for loop EX: for(int i=0;i*i<=x;i++)

!! for(int i:a) does not work when pasing it a function inside a class



# To take input separated by comma
```c++

#include <bits/stdc++.h>
using namespace std;
 
int main()

{ 	
	string s="1,23,45,634,1";
	stringstream ss(s);
	while(ss.good()){//rem this condition

	string s1;
	getline(ss,s1,',');
	cout<<s1<<endl;

	}

	
}
	

--------------------------------------------------------------------------------------------
#include <bits/stdc++.h>
using namespace std;
 
int main()

{ 	
	string s;
	getline(cin,s);
	cout<<s<<endl;
	cout<<s.size()<<endl;

	vector <int> v;
	for(int i=0;i<s.size();i++){
		if(s[i]==','){
			continue;
		}
		else{
			v.push_back(s[i]-'0');
		}
	}

	for(int t:v){
		cout<<t<<endl;
	}




}

```
# BUILT IN PERMUTATION AND COMBINATION
```C++
#include <bits/stdc++.h>
using namespace std;
 
int main()

{ 	
	char a[3]={'a','b','c'};
	sort(a,a+3);//sorting the array as next_permutation func will generate lexicographically larger elements than last
	do{
		for(int i=0;i<3;i++){
			cout<<a[i];
		}
		cout<<endl;
	}while(next_permutation(a,a+3));
	//using prev_permutation will generate smaller than previous arrangement but the array should be sorted in decending arder

	
}
	
```
# array
	use array+(n-1) for getting end value in array for fucntions like sort ,max use array+n
	for vector v.begin()..etc to get to last value use n-1 else index out of bounds in vector will crash the code
	

# FOR GETTING DECIMAL POINTS
```c++
cout.precision(2); //2 number of digits after point
else C<<fixed<<x<<l;//use fixed to display decimal points
```
# For passing matrix in a function
```c++
int n=5;//use int** a as formal parameters in a function
    int** a=new int*[n];
    for(int i=0;i<n;i++){
        a[i]=new int[n];
    }
    for(int i=0;i<n;i++){
        for(int j=0;j<n;j++){
            cin>>a[i][j];
        }
    } 
    int** s=new int*[n];
    for(int i=0;i<n;i++){
        s[i]=new int[n];
    }
    for(int i=0;i<n;i++){
        for(int j=0;j<n;j++){
          s[i][j]=0;
        }
    } 

```
# datastructure conversion
```c++
 set <int,greater<int>> s(arr,arr+n);//can use it for other data as well but 2 DS should have the same datatype
  map <int,int>m;
        for(int i:nums)m[i]++;
        vector <pair<int,int>> f(m.begin(),m.end());//can directly store data to vector like 
```
