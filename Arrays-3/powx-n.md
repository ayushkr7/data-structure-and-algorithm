Link: https://leetcode.com/problems/powx-n/

~~~
class Solution {
public:
    
    double myPow(double x, int n) {
        double res = 1;
        if(n==0){
            return 1;
        }else if(n>0){
            while(n>0){
                if(n&1){
                    res = res*x;
                }
                x = x*x;
                n = n>>1;
            }
        }else if(n<0){
            n = abs(n);
            while(n>0){
                if(n&1){
                    res = res/x;
                }
                x = (x*x);
                n = n>>1;
            }
        }
        return res;
    }
};
~~~
