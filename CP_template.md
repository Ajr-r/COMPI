```c++
#include <bits/stdc++.h>
# define C cout
# define l "\n";
using namespace std;
int bs(vector <int> v,int key,bool f){
	int i=0;
	int e=v.size()-1;
	int ans=-1;
	while(i<=e){
		int mid=(i+e)/2;
		if(v[mid]==key){
			ans=mid;
			break;
		}
		else if(v[mid]>key){
			e=mid-1;
		}
		else i=mid+1;
	}
	if(f&&ans>=0){
		return 1;

	}
	else{
		return ans;
	}
}

void solve(){
	C<<"das"<<l
	vector <int> v={5,6,7,8,9};
	int key=0;
	 C<<bs(v,key,1)<<l
	

	
	

}

 
int main()
{ 
	ios_base::sync_with_stdio(false);
    cin.tie(NULL);
	int t=1;
	while(t--){
		solve();
	}

	return 0;
	
	
}
	


```
