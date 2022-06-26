Link: https://practice.geeksforgeeks.org/problems/find-missing-and-repeating2512/1

~~~
#include <bits/stdc++.h> 

pair<int,int> missingAndRepeating(vector<int> &arr, int n)
{
    int xor1 = arr[0]; int x=0, y=0;
    
    for(int i=1;i<n;i++){
        xor1 = xor1^arr[i];
    }
    
    for(int i=1;i<=n;i++){
        xor1 = xor1^i;
    }
    
    int set_bit_no = xor1 & ~(xor1-1);
    
    for(int i=0;i<n;i++){
        if(arr[i] & set_bit_no){
            x = x^arr[i];
        }else{
            y = y^arr[i];
        }
    }
    
    for(int i=1;i<=n;i++){
        if(i & set_bit_no){
            x = x^i;
        }else{
            y = y^i;
        }
    }
    
    int x_count = 0;
    for (int i=0; i<n; i++) {
        if (arr[i]==x)
            x_count++;
    }
    
    if (x_count==0)
        return {x, y};
    
    return {y, x};
}

~~~
