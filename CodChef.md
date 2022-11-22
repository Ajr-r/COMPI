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
# maxedges 1618

<img width="346" alt="Screenshot 2022-11-22 140446" src="https://user-images.githubusercontent.com/100711675/203265102-c58c4c73-0887-4dfc-a1e4-622f57953884.png">
<img width="347" alt="Screenshot 2022-11-22 140500" src="https://user-images.githubusercontent.com/100711675/203265114-4e70fe42-4a3c-4564-86dc-8dd3b8c45e07.png">

```c++
#include <bits/stdc++.h>
# define C cout
# define l "\n";
#define ll long long 
#define ld long double 
using namespace std;

void solve(){
         ll n,s1,s2;
	    cin>>n>>s1>>s2;
	    
	     ll temp; 
	     ll ans ;
	    
	    if(n>= (s1+s2)){
	        temp = n-(s1+s2);
	         ll ans1 = s1*s2;
	         ll ans2= temp*s1 + temp*s2;
	         ll ans3 = ((temp-1)*(temp))/2;
	        
	        ans = ans1 + ans2+ans3;
	        cout<<ans<<endl;
	        
	    }
	    else{
	        
	        temp = (s1+s2)-n;// normal vertices
	        ans = (s1-temp)*(s2-temp);	        
	        cout<<ans<<endl;
	        
	    }
	    
	    return;


}

 
int main()
{ 
	ios_base::sync_with_stdio(false);
    cin.tie(NULL);
	int t;
    cin>>t;
	while(t--){
		solve();
	}

	return 0;
	
	
}
	





```
