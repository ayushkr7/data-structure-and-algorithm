Link: https://leetcode.com/problems/merge-intervals

Time Complexity: O(NlogN) + O(N). O(NlogN) for sorting and O(N) for traversing through the array.

Space Complexity: O(N) to return the answer of the merged intervals.
~~~
class Solution {
public:
    vector<vector<int>> merge(vector<vector<int>>& intervals) {
        vector<vector<int>> res;
        
        if(intervals.size()==0){
            return res;
        }
        
        sort(intervals.begin(), intervals.end());
        vector<int> temp = intervals[0];
        
        for(auto it: intervals){
            if(it[0] <= temp[1]){
                temp[1] = max(it[1], temp[1]);
            }else{
                res.push_back(temp);
                temp = it;
            }
        }
        
        res.push_back(temp);
        
        return res;
    }
};
~~~


