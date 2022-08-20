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
cout<<m.empty()<<endl;//returns 1 if empty else 0
 
}
```
