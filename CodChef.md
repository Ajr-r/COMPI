1435


<img width="353" alt="Screenshot 2022-11-16 141529" src="https://user-images.githubusercontent.com/100711675/202132006-01f4cf17-bef5-44bf-879d-01dd975ae2ba.png">

<img width="352" alt="Screenshot 2022-11-16 141542" src="https://user-images.githubusercontent.com/100711675/202132124-a889caca-5841-421c-acc1-f56c04918f15.png">

```c++
#include <bits/stdc++.h>
# define C cout
# define l "\n";
#define ll long long 
#define ld long double 
using namespace std;
const int n=10000000;
ll mod=1000000007;
ll dp[n];
int main() {
    dp[0]=0;
    dp[1]=1;
    for(int i=2;i<=n;i++)dp[i]=(dp[i-1]%mod*i%mod)%mod;//precomputing
	int t;
	cin>>t;
	while(t--){
	    ll e;
	    cin>>e;
        ll sum=0;
        for(int i=0;i<e;i++){
            ll y;
            cin>>y;
             sum+=dp[y]%mod;
        }
       
        cout<<sum%mod<<endl;

	}
	return 0;
}

```
