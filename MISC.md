# 1> In order to reach the conditon limit faster mess with i in condition part in for loop EX: for(int i=0;i*i<=x;i++)

# To take input separated by comma
```c++

#include <bits/stdc++.h>
using namespace std;
 
int main()
{
    // Get the string
    string str = "11,21,31,41,51,61";
 
    vector<int> v;
 
    // Get the string to be taken
    // as input in stringstream
    stringstream ss(str);
 
    // Parse the string
    for (int i; ss >> i;) {
        v.push_back(i);
        if (ss.peek() == ',')
            ss.ignore();
    }
 
    // Print the words
    for (size_t i = 0; i < v.size(); i++)
        cout << v[i] << endl;
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
