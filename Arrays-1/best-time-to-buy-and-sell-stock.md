Link: https://leetcode.com/problems/best-time-to-buy-and-sell-stock/

~~~
class Solution {
public:
    int maxProfit(vector<int>& prices) {
        if(prices.size()==0) return 0;
        
        int min_price=INT_MAX, max_sell=0;
        int n = prices.size();
        for(int i=0;i<n;i++){
            min_price = min(min_price, prices[i]);
            max_sell = max(max_sell,prices[i]-min_price);
        }       
        
        
        return max_sell;       
        
    }
};
~~~
