#impotant points

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
