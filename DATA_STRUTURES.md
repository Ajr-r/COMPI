# VECTORS
```C++
#include <bits/stdc++.h>
using namespace std;
 
int main()
{
    vector <int> v={1,2,3,4};//can initialize elements like this
    v.push_back(5);// also can add elements works like a array
    for(int i:v){
        cout<<i<<" ";
    }
    cout<<endl;
    cout<<*v.cbegin()<<endl;
    cout<<*v.cend()<<endl;
    cout<<v.size()<<endl;
    cout<<v.max_size()<<endl;
    cout<<v.empty()<<endl;
    v.resize(3);//trims the rest val after 3 elemenents
     for(int i:v){
        cout<<i<<" ";
    }
    cout<<endl;
    v.assign(5,10);//fills the vector with 5 10s

    v.pop_back();//removes the last element
    cout<<v.size()<<endl;
    v.insert(v.begin(),22);//inserts element to given posi and pushes other elements one step behind
    v.insert(v.begin(),11);//inserts element to given posi and pushes other elements one step behind
    v.erase(v.begin()+1);//erases the element in that posi
      for(int i:v){
        cout<<i<<" ";
    }
    //v1.sawap(v2)->swaps all elements
    v.clear();//clears the vector
    sort(v.begin(), v.end(), greater<int>());//to sort the vector
   *max_element(v.begin(),v.end())//to find max element
}
//vector matrix
vector <vector<int>> v;
        for(int i=0;i<n;i++){
            vector <int> temp;
            for(int j=0;j<n;j++){
                int t;
                cin>>t;
                temp.push_back(t);
            }
            v.push_back(temp);
        }
        for(int i=0;i<n;i++){
            for(int j=0;j<n;j++){
                C<<v[i][j]<<" ";
            }
            C<<endl;
        }

    }
```
# MAP AND PAIR
```c++
#include <bits/stdc++.h>
using namespace std;

int main() {
    //keys are unique
pair<char,int> p('r',9);
p.first='a';
p.second=7;
cout<<p.first<<" "<<p.second<<endl;

map <string,int> m={{"frieza",9200},{"nappa",4000}};
m["goku"]=9000;
m["vegeta"]=8000;
map<string,int>::iterator i;
for(i=m.begin();i!=m.end();i++){
    cout<<i->first<<" "<<i->second<<endl;
}
m.erase("vegeta");
cout<<m["vegeta"]<<endl;
m.clear();//clears the map
m.find(); //returns a iterator which points to the key, else returns the iterator which is same as m.end()
cout<<m.empty()<<endl;//returns 1 if empty else 0
  map <int,int> m={{1,2}};
    if(m.find(1)==m.end())C<<"s"<<l
    C<<m.find(1)->first<<l// "-> " is used to get the value from the iterator
 
}
//vector matrix
vector <vector<int>> v;
        for(int i=0;i<n;i++){
            vector <int> temp;
            for(int j=0;j<n;j++){
                int t;
                cin>>t;
                temp.push_back(t);
            }
            v.push_back(temp);
        }
        for(int i=0;i<n;i++){
            for(int j=0;j<n;j++){
                C<<v[i][j]<<" ";
            }
            C<<endl;
        }

    }
    for( char i:s){
        if(m.find(i)==m.end()){
            m[i]++;//while checking for a element if not present also selt the value to 1 else the map doesnt store the value
            sum+=2;
        }
        else{
          
            m[i]++;
            sum++;
        }
    }
```
# SETS
```C++
#include <bits/stdc++.h>
using namespace std;
    //Storing order – The set stores the elements in sorted order.
    // Values Characteristics – All the elements in a set have unique values.
    // Values Nature – The value of the element cannot be modified once it is added to the set, though it is possible to remove and then add the modified value of that element. Thus, the values are immutable.
    // Search Technique – Sets follow the Binary search tree implementation.
    // Arranging order – The values in a set are unindexed.
    // Note: To store the elements in an unsorted(random) order,  unordered_set() can be used.
int main() {//find the lowest missing positive number ex 123...2 is missing the given array
set <int> s;
  set<int, greater<int> > s1;//even after inserting random it sorts it in decending order
s.insert(100);
s.insert(93);
s.insert(130);
s.insert(1050);
s.insert(102);
cout<<s.size();
// The time complexities for doing various operations on sets are:
// Insertion of Elements – O(log N)
// Deletion of Elements – O(log N)
set <int>  :: iterator it;
for(it=s.begin();it!=s.end();it++){
    cout<<*it<<" ";
}
cout<<"\n-----------------------------\n";
s.erase(s.begin(),s.find(102));//it exlusive of 102
int y=s.erase(1050);//can aslo store the removed value

for(it=s.begin();it!=s.end();it++){
    cout<<*it<<" ";
}
   
    
  
}

```
