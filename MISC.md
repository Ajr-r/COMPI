# 1> In order to reach the conditon limit faster mess with i in condition part in for loop EX: for(int i=0;i*i<=x;i++)

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
	
# sometime if the getline() is not working properly use cin.ignore()
# FOR GETTING DECIMAL POINTS
```c++
cout.precision(2); //2 number of digits after point
else C<<fixed<<x<<l;//use fixed to display decimal points
```
# find function in unordered set is faster than binary search 
# unordererd data structures are faster than order structure ex:- unordered set and unordered map
# IMPORTNANT POINT
!! Trying to erase a element in a array which is for loop it will skip the next element after erasing due to index relocation better to store the wanted value in diff array

