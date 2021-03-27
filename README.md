# Competitive-Programming-Theory
---


## Basic Maths:


### Algorithms:
[1. Sieve of Eratosthenes](https://www.geeksforgeeks.org/sieve-of-eratosthenes/)[ & extensions](https://codeforces.com/blog/entry/22229)


----

## Miscellaneous:


[1.Compare function in sort()](https://stackoverflow.com/questions/597532/how-do-you-structure-your-comparison-functions)

   ```C++
   //Example 1
      vector<pair<ll,char>>mp;
      bool cmp(pair<ll,char>&p1,pair<ll,char>&p2)
                {
                      if(p1.first!=p2.first)
                      return p1.first<p2.first;//Returning smaller value
                      else
                      return p1.second>p2.second;//Returning bigger value
                }
        sort(mp.begin(),mp.end(),cmp);
        
        ```
        
      
            




      
