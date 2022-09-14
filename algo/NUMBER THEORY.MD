# IMPORTANT NOTES
$ odd +/- odd = even,
  even +/- even = even,
  odd +/- even = odd,
  even +/- odd = odd,
  odd x odd = odd,
  even x even = even,
  odd x even = even,
  even x odd = even
  
  <img width="443" alt="Screenshot 2022-09-14 184750" src="https://user-images.githubusercontent.com/100711675/190165031-91ffd1b0-4902-4cbb-8518-c7058bd5f9bc.png">


```c++

void solve(){
    int x;
    cin>>x;
    if(x%2==0)C<<4<<" "<<x-4;
    else C<<9<<" "<<x-9;   
}

```
# TO FIND SUM TILL N
```C++
 int x=10;
    C<<x*(x+1)/2<<l
```
# LCM AND GCD
```C++
void solve(){
    int x=10,y=20;
    int m=max(x,y);
    while(1){
        if(m%x==0&&m%y==0){
            C<<m<<l
            break;
        }
        m++;
    }
    C<<__gcd(x,y);

}
```
# Balls and boxes
```C++
//if number of balls is equal to or greater than sum of n natural number then it can the boxes can have unique set of balls and with min 1 ball ber box and n is number of boxes
```
