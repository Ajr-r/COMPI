# Google Kickstart speed typing(easy)
https://codingcompetitions.withgoogle.com/kickstart/round/00000000008cb33e/00000000009e7021#problem
```

Problem
Barbara is a speed typer. In order to check her typing speed, she performs a speed test. She is given a string I that she is supposed to type.
While Barbara is typing, she may make some mistakes, such as pressing the wrong key. As her typing speed is important to her, she does not want to spend additional time correcting the mistakes, so she continues to type with the errors until she finishes the speed test. After she finishes the speed test, she produces a P.
Now she wonders how many extra letters she needs to delete in order to get I from P. It is possible that Barbara made a mistake and P cannot be converted back to I just by deleting some letters. In particular, it is possible that Barbara missed some letters.
Help Barbara find out how many extra letters she needs to remove in order to obtain I or if I cannot be obtained from P by removing letters then output IMPOSSIBLE.

Input
The first line of the input gives the number of test cases, T. T test cases follow.
Each test case has 2 lines. The first line of each test case is an input string I (that denotes the string that the typing test has provided). The next line is the produced string P (that Barbara has entered).

Output
For each test case, output one line containing Case #x: y, where x is the test case number (starting from 1) and y is the number of extra letters that need to be removed in order to obtain I. If it is not possible to obtain I then output IMPOSSIBLE as y.

Limits
Memory limit: 1 GB.
1≤T≤100.
Both the strings contain letters from a-z and A-Z.
Length of the given strings will be 1≤|I|,|P|≤105.
Test Set 1
Time limit: 20 seconds.
All letters in I are the same.

Test Set 2
Time limit: 40 seconds.
Sample
Note: there are additional samples that are not run on submissions down below.

2
aaaa
aaaaa
bbbbb
bbbbc

Case #1: 1
Case #2: IMPOSSIBLE

2
Ilovecoding
IIllovecoding
KickstartIsFun
kkickstartiisfun

Case #1: 2
Case #2: IMPOSSIBLE

```
```c++
#include <bits/stdc++.h>
using namespace std;
void solve(){
    
    string i,p;
    cin>>i>>p;
    int k=0,j=0;
    while(k<i.size()&&j<p.size()){
        if(p[j]==i[k]){
            j++;
            k++;
        }
        else j++;
    }
    // cout<<k<<" "<<j<<endl;
    if(k!=i.size()){
          cout<<"IMPOSSIBLE"<<endl;
        return ;
    }

   
    cout<<p.size()-i.size()<<endl;
}
int main(){
    ios::sync_with_stdio(0);
    cin.tie(0);
    int t;
    cin>>t;
    int i=1;
    while(t--){
      cout<<"Case #"<<i<<": ";
        solve();
        i++;
    }
}
```
# Google kickstart new password(easy)
https://codingcompetitions.withgoogle.com/kickstart/round/00000000008cb4d1/0000000000b20f15
```
 company named Gooli has issued a new policy that their employees account passwords must contain:

At least 7 characters.
At least one uppercase English alphabet letter.
At least one lowercase English alphabet letter.
At least one digit.
At least one special character. There are four special characters: #, @, *, and &.
The company has asked all the employees to change their passwords if the above requirements are not satisfied. Charles, an employee at Gooli, really likes his old password. In case his old password does not satisfy the above requirements, Charles will fix it by appending letters, digits, and special characters. Can you help Charles to find the shortest possible new password that satisfies his company's requirements?

Input
The first line of the input gives the number of test cases, T. T test cases follow. Each test case consists of two lines. The first line of each test case contains an integer N, denoting the length of the old password. The second line of each test case contains the old password of length N. Old password contains only digits, letters, and special characters.

Output
For each test case, output one line containing Case #x: y, where x is the test case number (starting from 1) and y is a valid new password, obtained by possibly fixing the old password in the way that Charles wants and satisfying the company's requirements.

It is guaranteed that at least one solution exists. If there are multiple solutions, you may output any one of them.

Limits
Time limit: 20 seconds.
Memory limit: 1 GB.
1≤T≤100.
Test Set 1
7≤N≤104.
The old password contains only digits.

Test Set 2
1≤N≤104.
The old password contains only digits, letters, and special characters.

Sample
Note: there are additional samples that are not run on submissions down below.

2
7
1234567
10
1111234567

Case #1: 1234567aA&
Case #2: 1111234567@Rc

3
1
A
2
1*
7
1234aB&

Case #1: Aa1*111
Case #2: 1*abAA*
Case #3: 1234aB&


```
```c++
#include <bits/stdc++.h>
using namespace std;
string update(string s){
    int f2=0,f3=0,f4=0,f5=0;
    for(char i:s){
        if(isdigit(i)){
            f4=1;
            continue;
        }
         if(isalpha(i)){
            if(isupper(i)){
            f2=1;
            continue;
        }
        else{
            f3=1;
            continue;
        }
         }
         f5=1;
    }
    if(!f4)s.append("0");
     if(!f2)s.append("A");
     if(!f3)s.append("a");
     if(!f5)s.append("@");

    return s;
}
void solve(){
    int n;
    cin>>n;
    string s;
    cin>>s;
    string ans=update(s);
    // cout<<ans.size()<<endl;
    // cout<<ans<<endl;

    if(ans.size()<7){
        int x=7-ans.size();
        for(int i=0;i<x;i++){
            ans.append("a");
        }
    }
    cout<<ans<<endl;
    

}
int main(){
    ios::sync_with_stdio(0);
    cin.tie(0);
    int t;
    cin>>t;
    int i=1;
    while(t--){
       cout<<"Case #"<<i<<": ";
        solve();
        i++;
    }
}

```
# GFG Maximum Occuring Character
```
Given a string str. The task is to find the maximum occurring character in the string str. If more than one character occurs the maximum number of time then print the lexicographically smaller character.

Input:
str = testsample
Output: e
Explanation: e is the character which
is having the highest frequency.

Input:
str = output
Output: t
Explanation:  t and u are the characters
with the same frequency, but t is
lexicographically smaller.
```
```c++
    char getMaxOccuringChar(string str)
    {
        // Your code here
        map <char,int>m;
        set <char> s;
        int mx=INT_MIN;
        for(int i=0;i<str.size();i++){
            m[str[i]]++;
            mx=max(mx,m[str[i]]);
            
        }
          for(int i=0;i<str.size();i++){
            if(m[str[i]]==mx)s.insert(str[i]);
            
            
        }
        return *s.begin();
       
    }
```
# GFG check is string is rotated
```
Given two strings s1 and s2. The task is to check if s2 is a rotated version of the string s1. The characters in the strings are in lowercase.

Input:
geeksforgeeks
forgeeksgeeks
Output: 
1
Explanation: s1 is geeksforgeeks, s2 is
forgeeksgeeks. Clearly, s2 is a rotated
version of s1 as s2 can be obtained by
left-rotating s1 by 5 units.

Input:
mightandmagic
andmagicmigth
Output: 
0
Explanation: Here with any amount of
rotation s2 can't be obtained by s1.


```
```c++
    bool areRotations(string s1,string s2)
    {
        if(s1.length()!=s2.length())
            return false;
        else
        {
            //we concatenate first string to itself and check if other 
            //string occurs in it as substring. If yes, then it 
            //is rotated version and we return true else false.
            string concated=s1+s1;
            if(concated.find(s2)!=string::npos)
                return true;
            else
                return false;
        }
    }
```
# GFG reversing the vowels (school)
```
Given a string consisting of lowercase english alphabets, reverse only the vowels present in it and print the resulting string.

Input:
S = "geeksforgeeks"
Output: geeksforgeeks
Explanation: The vowels are: e, e, o, e, e
Reverse of these is also e, e, o, e, e.

Input: 
S = "practice"
Output: prectica
Explanation: The vowels are a, i, e
Reverse of these is e, i, a.

Input: 
S = "bcdfg"
Output: bcdfg
Explanation: There are no vowels in S.
```
```c++
  string modify (string s)
        {
            //code here.
            int i=0;
            int j=s.size()-1;
           string v="aeiou";
           for(int i=0;i<s.size();i++){
               if(v.find(s[i])!=string::npos){
                while(j>=i){
                 if(v.find(s[j])!=string::npos){
                    swap(s[i],s[j]);
                    j--;
                    break;
                 }
                 j--;
                }
        
               }
           }
           return s;
    
        }
        \\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\alternate sol
        string modify (string s)
        {
            string vow = "";
            for (int i = 0; i < s.length (); ++i)
            {
                // removing the vowels from s and adding them to the string vow
                if (s[i] == 'a' || s[i] == 'e' || s[i] == 'i' || s[i] == 'o' || s[i] == 'u')
                {
                    vow += s[i];
                    s[i] = '.'; // to indicate that the current position is now empty
                }
            }
        
            // traversing s in reverse order and placing the vowels at empty locations
            int i = s.length () - 1;
            int j = 0;
            while (i >= 0)
            {
                if (s[i] == '.') s[i] = vow[j++];
                i--;
            }
            return s;
        }
        
```
