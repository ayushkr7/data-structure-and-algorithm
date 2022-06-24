Link: https://practice.geeksforgeeks.org/problems/merge-two-sorted-arrays-1587115620/1
<br><br>
Solution 1: <br>
Time Complexity: O(n logn)<br>
Space complexity: O(1)<br>

~~~
class Solution{
    public:
        //Function to merge the arrays.
        void merge(long long arr1[], long long arr2[], int n, int m) 
        { 
            // code here 
            int gap = ceil((float)(m+n)/2);
            
            while(gap>0){
                int i=0, j=gap;
                
                while(j<(n+m)){
                    if(j<n && arr1[i]>arr1[j]){
                        swap(arr1[i],arr1[j]);
                    }else if(j>=n && i<n && arr1[i] > arr2[j - n]){
                        swap(arr1[i], arr2[j - n]);
                    }else if(j >= n && i >= n && arr2[i - n] > arr2[j - n]) {
                        swap(arr2[i - n], arr2[j - n]);
                    }
                
                    i++;
                    j++;
                }
                
                if (gap == 1) {
                    gap = 0;
                } else {
                    gap = ceil((float) gap / 2);
                }
            }

        } 
};
~~~
