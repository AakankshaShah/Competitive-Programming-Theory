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
3.No. of a digits in a number:
floor(log b)+1 (if base is 10)

 




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

## Strings
[1.Permutations of a string](https://www.geeksforgeeks.org/write-a-c-program-to-print-all-permutations-of-a-given-string/)
```c++
	void permute(string a, int l, int r)
{
    // Base case
    if (l == r)
        ans.push_back(a);
    
    else
    {
        // Permutations made
        for (int i = l; i <= r; i++)
        {
 
            // Swapping done
            swap(a[l], a[i]);
 
            // Recursion called
            permute(a, l+1, r);
 
            //backtrack
            swap(a[l], a[i]);
        }
    }
    
   ```
<br />

<img src="https://user-images.githubusercontent.com/55951533/116806306-aab6c880-ab49-11eb-91c7-cd14bd081452.png">

    

----
## Queue:
1.Rotten Oranges:

```c++

class Solution {
public:
int N,M;
 
 struct ele
 {
    int tf;
    int x;
    int y;
 };

 bool isSafe(int i,int j)
 {
    if(i>=0 && i<N && j>=0 && j<M)
        return true;
    return false;
 }

 bool orangeLeft(vector<vector<int>>& grid)
 {
    for(int i=0;i<N;i++)
    {
        for(int j=0;j<M;j++)
        {
            if(grid[i][j]==1)
                
                return true;
                
        
               
        }
    }
    return false;
 }


    int orangesRotting(vector<vector<int>>& grid) 
    {queue<ele>q;
ele temp;
int ans=0;
N=grid.size();
M=grid[0].size();

for(int i=0;i<N;i++)
    {
        for(int j=0;j<M;j++)
        {if(grid[i][j]==2)
            {
                temp.tf=0;
                temp.x=i;
                temp.y=j;
                q.push(temp);
            }

        }
    }
    while(!q.empty())
    {


        temp=q.front();
        int i=temp.x;
        int j=temp.y;
        //cout<<i<<j<<"ij\n";
        if(isSafe(i-1,j)&&grid[i-1][j]==1)
        {
            grid[i-1][j]=2;
            temp.tf++;
            ans=max(ans,temp.tf);
            temp.x--;
            q.push(temp);
            temp.tf--;
            temp.x++;
            //cout<<i-1<<j<<"i-1\n";

        }
         if(isSafe(i,j+1)&&grid[i][j+1]==1)
        {
            grid[i][j+1]=2;
            temp.tf++;
             ans=max(ans,temp.tf);
            temp.y++;
            q.push(temp);
            temp.tf--;
            temp.y--;
            //cout<<i<<j+1<<"j+1\n";
        }
        
         if(isSafe(i,j-1)&&grid[i][j-1]==1)
        {
            grid[i][j-1]=2;
            temp.tf++;
            ans=max(ans,temp.tf);
            temp.y--;
            q.push(temp);
            temp.tf--;
            temp.y++;
            //cout<<i<<j-1<<"j-1\n";
        }
        
         if(isSafe(i+1,j)&&grid[i+1][j]==1)
        {
            grid[i+1][j]=2;
            temp.tf++;
            ans=max(ans,temp.tf);
            temp.x++;
            q.push(temp);
            temp.tf--;
            temp.x--;
            //cout<<i+1<<j<<"i+1\n";
        }
        
        q.pop();

    }
     if(orangeLeft(grid)==true)
    return -1;
    else
    return ans;
        
    }
};

 ```

2.First non-repeating character in a stream

```c++
class Solution {
	public:
		string FirstNonRepeating(string A)
		{string s = "";
         queue<char>q;
         int arr[26] = {0};
for (int i = 0; i < A.size(); i++) {

q.push(A[i]);
arr[A[i] - 'a']++;
while (!q.empty()) {
if (arr[q.front() - 'a'] > 1) {
q.pop();
}
else
break;
}
if (q.empty())
s += '#';
else
s += q.front();
}

return s;
}

````

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
 ## Graphs:
 1.Bridges(DFS TREE)

```c++
#include<stdio.h>
#include<math.h>
           second 

ll dis[max5],vis[15];
vector<ll> arr[15];
ll timer=1;
ll in[15],low[15];

void dfs(ll node,ll par)
{
    vis[node]=1;
    in[node]=low[node]=timer;
    
    timer++;
    for(auto child:arr[node])
    {//Checking for parent
        if(child==par)
        continue;
        if(vis[child]==1)
        {//back edge
            low[node]=min(in[child],low[node]);
            cout<<node<<"-"<<child<<"back edge\n";
        }
        else
        {//forward edge
            dfs(child,node);
            if(low[child]>in[node])
            {
                cout<<node<<"-"<<child<<"is a bridge\n";

            }
            low[node]=min(low[child],low[node]);
        }
    }
}



int main () 
{
  
 
 #ifndef ONLINE_JUDGE
    // for getting input from input.txt
    freopen("inputFile.txt", "r", stdin);
    // for writing output to output.txt
    freopen("outputFile.txt", "w", stdout);
#endif
    
ios_base::sync_with_stdio (0);
  
 
cin.tie (0);
  
 
cout.tie (0);
ll n,e,x,y;
cin>>n;
cin>>e;
while(e--)
{cin>>x>>y;
arr[x].push_back(y);
arr[y].push_back(x);


}
dfs(1,-1);



  
 
 
 
 
 
return 0;

 
}

```
 
 
 
 <br/>
 
 
 ----
 ## Conceptual Questions
 [Maximum sum subarray removing at most one element](https://www.geeksforgeeks.org/maximum-sum-subarray-removing-one-element/#:~:text=Given%20an%20array%2C%20we%20need,sum%20subarray%20by%20removing%20%2D4.)
 
 
 <br/>
 
 
 ----
 ## Extras
 [1.Fast Input](https://discuss.codechef.com/external-redirect/?url=https://stackoverflow.com/questions/1042110/using-scanf-in-c-programs-is-faster-than-using-cin)
  ```c++
  ios_base::sync_with_stdio(0); cin.tie(0); cout.tie(0);
  
  ```
            




      
