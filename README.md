# Competitive-Programming-Theory
---


## Basic Maths:


### Algorithms:
[1. Sieve of Eratosthenes](https://www.geeksforgeeks.org/sieve-of-eratosthenes/)[ & extensions](https://codeforces.com/blog/entry/22229) <br /> 
2.Storing 2 numbers in a single varibale:
```c++
n1=5;
n2=7;
z=10(greater than both n1 & n2)
n1=n1+(n2%z)*z;

To get n1:
n1=n1%z;

To get n2:
n2=n2/z;
```
<br />

 




----
## Arrays:
[1.Kadane's Algorithm](https://www.geeksforgeeks.org/largest-sum-contiguous-subarray/)<br />
[2.Dutch National Flag](http://users.monash.edu/~lloyd/tildeAlgDS/Sort/Flag/)[ and 3 way partioning](https://www.geeksforgeeks.org/sort-an-array-of-0s-1s-and-2s/)<br />
[3.Merge without extra space](https://practice.geeksforgeeks.org/problems/merge-two-sorted-arrays/0/)

  ```c++
  int i=0,j=m-1;
            while(i<n&&j>0)
            {
                if(arr1[i]>arr2[j])
                {int tem=arr1[i];
                arr1[i]=arr2[j];
                arr2[j]=tem;
                i++;
                sort(arr2,arr2+m);
                
                }
                else
                {
                i++;j--;
                }
            }
  
  ```

[4.Sliding Window](https://www.geeksforgeeks.org/window-sliding-technique/0)<br />
[5.Valley Peak Approach](https://dev.to/bebopvinh/leetcode-122-the-valleys-and-peaks-approach-5j9#:~:text=The%20first%20inner%20loop%20looks,before%20the%20price%20starts%20increasing&#41.&text=This%20one%20looks%20for%20a,difference%20to%20the%20max%20profit.)<br />


----

## Miscellaneous:


[1.Compare function in sort()](https://stackoverflow.com/questions/597532/how-do-you-structure-your-comparison-functions)

   ```c++
   //Example 1
      vector<pair<ll,char>>mp;
      bool cmp(pair<ll,char> &p1,pair<ll,char> &p2)
                {
                      if(p1.first!=p2.first)
                      return p1.first<p2.first;//Returning smaller value
                      else
                      return p1.second>p2.second;//Returning bigger value
                }
        sort(mp.begin(),mp.end(),cmp);
        
   ```
   
   
   ```c++
   //Example 2
   struct Car{
 Manufacturer make;
 ModelName model;
 Year year;
};

bool carLessThanComparator( const Car & car1, const Car & car2 ) {
 if( car1.make < car2.make )
     return true;

 if ( car1.make != car2.make )
     return false;

 if( car1.model < car2.model )
     return true;

 if( car1.model != car2.model )
     return false;

 if( car1.year < car2.year )
     return true;

 return false;
}
   ```
        
 <br/>
 
 
 ----
 ## Conceptual Questions
 [Maximum sum subarray removing at most one element](https://www.geeksforgeeks.org/maximum-sum-subarray-removing-one-element/#:~:text=Given%20an%20array%2C%20we%20need,sum%20subarray%20by%20removing%20%2D4.)
 
 
 <br/>
 
 
 ----
            




      
