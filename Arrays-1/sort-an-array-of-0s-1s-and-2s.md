Solution 1: Keeping count of values

Time Complexity: O(N) + O(N)

Space Complexity: O(1)
~~~
class Solution {
public:
    void sortColors(vector<int>& nums) {
        int zero=0, one=0,two=0;
        
        for(int i=0;i<nums.size();i++){
            if(nums[i]==0){
                zero++;
            }else if(nums[i]==1){
                one++;
            }else if(nums[i]==2){
                two++;
            }
        }
        
        int j=0;
        while(zero--){
            nums[j]=0;
            j++;
        }
        while(one--){
            nums[j]=1;
            j++;
        }
        while(two--){
            nums[j]=2;
            j++;
        }
        
        
    }
};
~~~

Solution 2: 3-Pointer approach

Time Complexity: O(N)

Space Complexity: O(1)
~~~
class Solution {
public:
    void sortColors(vector<int>& nums) {
        int lo = 0; 
        int hi = nums.size() - 1; 
        int mid = 0; 

        while (mid <= hi) { 
            switch (nums[mid]) { 

            // If the element is 0 
            case 0: 
                swap(nums[lo++], nums[mid++]); 
                break; 

            // If the element is 1 . 
            case 1: 
                mid++; 
                break; 

            // If the element is 2 
            case 2: 
                swap(nums[mid], nums[hi--]); 
                break; 
            }
        }
         
    }
};
~~~
