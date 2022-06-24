Link: https://leetcode.com/problems/next-permutation/

~~~
class Solution {
public:
    void nextPermutation(vector<int>& nums) {
        int n = nums.size()-1;
        int index1, index2;
        for(int i=n-1;i>=0;i--){
            if(nums[i]<nums[i+1]){
               index1 = i; 
                break;
            }
        }
        
       if(index1<0){
           reverse(nums.begin(),nums.end());
           return;
       }
        
        for(int i=n;i>index1;i--){
            if(nums[i]>nums[index1]){
                index2 = i;
                break;
            }
        }
        
        swap(nums[index1],nums[index2]);
        reverse(nums.begin()+index1+1,nums.end());
        
        
    }
};
~~~
