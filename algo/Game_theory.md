#impotant points
!! make the p1 as your main target and you want him to win

!! analys the problem and try to bring up solutions for small testcases

!! find the pattern and implement it 


# 1
Given an array A of N integers. Two players play a game with the array in turns. The game aims to make the array equal. Players add 1 to any number of the array to increase it by 1(except the maximum number). The player who adds last i.e. the player after whose turn the array becomes equal is declared the winner. If no moves can be made, the game is a draw.


Input:
N=2
A[]={1,2}
Output:
First
Explanation:
The first player adds 1 to the first 
number making it 2. The array 
becomes equal, so he is the winner.


Input:
N=3
A[]={2,2,2}
Output:
Draw
Explanation:
No moves can be made as all the elements are
already maximum and numbers cannot be
added to the maximum numbers.


```c++
class Solution {
  public:
    string arrayGame(int n, int a[]) {
        // code here
        int m=*max_element(a,a+n);
        int diff=0;
        for(int i=0;i<n;i++) diff+=m-a[i];
        if(diff==0)return "Draw";
        else if(diff%2==0) return "Second";
        else return "First";
        
    }
};

```
# 2
Jack and Jelly are on the ship en route to discover Atlantis and decide to play a game. The distance between their starting point and the city of Atlantis is N kilometers. They take turns manning the ship and each of them can steer the ship for 1, 2, or 4 kilometers in one turn. This should never exceed the remaining distance. The captain who is in charge of the ship when they react Atlantis wins the game.
If Jelly starts as the captain in charge of the ship, find who wins the game, i.e., who will be in charge of the ship when they reach Atlantis given both Jack and Jelly play optimally.
```
ex:- distances
n=1->jelly will win as it takes her 1 step
n=2->jelly will win as it takes her 2 step
n=3
  ->jelly can take 1 step
    ->jack will take 2 step and win
  ->jelly can take 2 step
    ->jack will take 1 step and win//so for 3 jelly cant win
n=4->jelly can take 4 step and win
n=5->jelly can take 2 step
      ->jack will be on n=3 while n=3 the first player cant win ...so jelly wins
n=6->jelly can take 1 step
      ->again same scenario as n=5 first player in n=5 wins aka jack
    ->jelly can take 2 step
      ->jack takes 4 step and wins
    ->  jelly can take 4 step
       ->jack takes 2 step and wins

so we can conclude that if the distance is divisble by 3 jack will win else jelly will win
       
```

# grundy method
  if output is 0 then p1 looses else he wins
```c++
#include <bits/stdc++.h>
using namespace std;
# define C cout
# define l "\n";
 
unordered_map <int,int> m={{0,0}};

int mex(unordered_set <int> s,int n){
    int i=0;
    while(s.find(i)!=s.end())i++;
    m[n]=i;
    return i;

}


int calcnim(int n,int a,int b){
    unordered_set <int> s;
    if(m.find(n-a)==m.end())
         s.insert(n-a);
    else s.insert(m[n-a]);     
   if(m.find(n-b)==m.end())
         s.insert(n-b);
    else s.insert(m[n-b]); 
  

    return mex(s,n);

}
int main(){
    int n=10;
    for(int i=0;i<=n;i++){

        calcnim(i,2,4);
    }
   for(auto i:m){
    C<<i.first<<" "<<i.second<<l
   }
}
```
# 3
3 stacks having x,y and z coins you can remove 1,2 or 4 coins from any stack determine if p1 wins or p2
Sprague grundy theorm
```c++

#include <bits/stdc++.h>
using namespace std;
# define C cout
# define l "\n";
int clacmex(unordered_set <int> s){
    int i=0;
    while(s.find(i)!=s.end())i++;
    return i;
}
int calcnimbers(int n){
    unordered_set <int> s;
    s.insert(n-1);
    s.insert(n-2);
    s.insert(n-4);
    return clacmex(s);

} 
int main(){
    int x,y,z;
    cin>>x,y,z; 
    int xe,ye,ze;
    xe=calcnimbers(x);
    ye=calcnimbers(y);
    ze=calcnimbers(z);
    C<<((xe^ye)^ze)<<l
}
```
# 4
game of nim 3 stacks with n coins p1 and p2 play turn by turn can take any number of coins determine the winner
```c++
#include <bits/stdc++.h>
using namespace std;
# define C cout
# define l "\n";
int main(){
    int a[]={4,3,5};
    int xorsum=0;
    for(int i:a)xorsum^=i;//fallows sprague grundy theorm since there is no limit for number coins that can be removed grundy number is equal to the number of coins

    if(xorsum==0)C<<"p2 wins";
    else C<<"p1 wins";
}

```
# 4
You are given an array A[] of n elements. There are two players player 1 and player 2.
A player can choose any of element from an array and remove it. If the bitwise XOR of all remaining elements equals 0 after removal of the selected element, then that player loses. Find out the winner if player 1 starts the game and they both play their best. 
```
Input: n = 3
A[] = {3, 3, 2}
Output: 2
Explaination: Optimal removal of values are 
3, 2, 3 sequentially. Then the array is empty. 
So player 2 wins.

Input: n = 2
A[] = {3, 3}
Output: 1
Explaination: In this case the xor is 0 from 
beginning of the game. So, player 1 does not 
need to make a move. So, he is the winner.

```

```c++
class Solution{
public:
    int findWinner(int n, int A[]){
        // code here
        int xorsum=0;
       for(int i=0;i<n;i++) xorsum^=A[i];
       if(xorsum==0)return 1;
       else if(n%2==0)return 1;
       else return 2;
    }
};
```
# infy (lvl 3)
Alice and Bob are playing a game with a stack of N cards. Players take their turn alternatively. In each turn a player can remove atleast A and atmost B cards from the stack unless there are less than A cards left in the stack, in that case player has to pick all the cards left.

The one who will start the game is decided by a coin toss. If the coin lands 'heads' Alice will start else Bob will start.

If a player cannot make the next move, then the player loses the game. If both the players play optimally, your task is to determine how many times does Alice wins the game from the T test cases.


<img width="295" alt="Screenshot 2022-10-05 140916" src="https://user-images.githubusercontent.com/100711675/194018266-b20ded46-ab52-4e86-b241-89127a43436d.png">


<img width="287" alt="Screenshot 2022-10-05 140959" src="https://user-images.githubusercontent.com/100711675/194018371-2561f745-7bfc-4ba3-99d6-8b759aff4b42.png">


```c++

#include <bits/stdc++.h>
using namespace std;
# define C cout
# define l "\n";






int main(){
    int t;
    cin>>t;
    int alicecount=0;
    int q;
    cin>>q;

    while(t--){
        int n,a,b,toss;
        cin>>n>>a>>b>>toss;
        if(toss==1){
            if(((n^a)^b)>0)alicecount++;
        }
        if(toss==0){
            if(((n^a)^b)<=0)alicecount++;
        }
     
        
    }
    C<<alicecount<<l
}

```
# GFG Jon and Arya are playing a game. Rules of game as follows:
·  They have a single number N initially.
·   Both will play an alternate move. Jon starts first.
·   Both will play each move optimally.
·   In each move, they can perform only one of these operation
          1. Divide that number by 2, 3, 4 or 5 and take floor of result.
          2. Subtract that number by 2, 3, 4 or 5.
·   If after making a move the number becomes 1, the player who made the move automatically loses the game.
·   When number becomes zero, the game will stop and the player who can't make a move loses the game.
```
Input:
N = 3
Output:
Jon
Explanation:
Jon will just subtract 3 from initial
number and win the game.

Input:
N = 6
Output:
Arya
Explanation:
Jon will divide by 3 and then in next step
Arya will subtract by 2 and win the game.
```
```c++
    string divAndSub(int n) {
       if(n==1) return "Arya";
       bool dp[n+1];
       memset(dp,0,sizeof(dp));
       dp[0]=0;//if n=0 then its a lossing state
       for(int i=1;i<=n;i++){
        for(int j=2;j<=5;j++){
            if(dp[i/j]==0)dp[i]=1;//checking to c if can reach to loosing state, if you give your opponent a lossing state that means your winning
            if((i-j)>=0&&dp[i-j]==0)dp[i]=1;//

        }
       }
       if(dp[n]==0)return "Arya";
       return "Jon";
     
    }

```


# infy hard(messi game)

<img width="450" alt="Screenshot 2022-10-14 120115" src="https://user-images.githubusercontent.com/100711675/195778810-20101294-5a6a-46c0-b4c9-075fca029e2e.png">


<img width="437" alt="Screenshot 2022-10-14 120125" src="https://user-images.githubusercontent.com/100711675/195778832-a32245c2-4106-423a-be2c-a9c3cde9859b.png">


```c++
#include <bits/stdc++.h>
# define C cout
# define l "\n";
#define ll long long 
#define ld long double 
using namespace std; 
int mod=1000000007;
ll sum(ll n){
  return (n*(n+1))/2;
}

int main() { 
  int n;
  cin>>n;
  int a[n];
  int b=0;
  for(int i=0;i<n;i++){
    cin>>a[i];
    if(a[i]%2==0&&sum(a[i])%3==0)b++;
    else if(a[i]%2!=0&&sum(a[i])%3!=0&&a[i]!=1)b++;
     }
  C<<b<<l
}




```
