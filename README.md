# Competitive-Programming-Theory
---


## Basic Maths:


### Algorithms:
[1. Sieve of Eratosthenes](https://www.geeksforgeeks.org/sieve-of-eratosthenes/)[ & extensions](https://codeforces.com/blog/entry/22229)


----

## Miscellaneous:


[1.Compare function in sort()](http://www.cplusplus.com/reference/cstdlib/qsort/)
<br />
<br />
Eg:<br />
  vector<pair<ll,char>>mp;<br />
  bool cmp(pair<ll,char>&p1,pair<ll,char>&p2)<br />
            {<br />
                  if(p1.first!=p2.first)<br />
                  return p1.first<p2.first;//Returning smaller value<br />
                  else<br />
                  return p1.second>p2.second;//Returning bigger value<br />
            }<br />
    sort(mp.begin(),mp.end(),cmp);<br />
    <br />
            




      
