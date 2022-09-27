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
