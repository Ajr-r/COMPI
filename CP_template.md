```c++
#include <bits/stdc++.h>
# define C cout
# define l "\n";
#define ll long long 
#define ld long double 
using namespace std;
int bs(vector <int> v,int key,bool f){
	int i=0,e=v.size()-1,ans=-1;
	while(i<=e){
		int mid=(i+e)/2;
		if(v[mid]==key){ans=mid;break;
		}
		else if(v[mid]>key)e=mid-1;
		else i=mid+1;
		}	
		if(f&&ans>=0&&ans<v.size())return 1;
    		else if(f&&ans<0)return 0;
		else return ans;
}

void solve(){
	C<<"das"<<l
	vector <int> v={5,6,7,8,9};
	int key=7;
	 C<<bs(v,key,0)<<l
	

	
	

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
