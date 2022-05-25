### Question
https://leetcode.com/problems/3sum-closest/

### Solution
```JAVA
import java.util.*;

class Solution {
    public int threeSumClosest(int[] nums, int target) {
        Arrays.sort(nums);
        int sum = 0;

        // Haven't created these variables to keep track of values
        int ans = 0;
        int diff = Integer.MAX_VALUE;
        
        for(int i=0; i<nums.length-2; i++) {
            int j = i+1;
            int k = nums.length-1;

            while(j < k) {
                sum = nums[i] + nums[j] + nums[k];
                
                // Missed this factor, here it's a general case but I have considered
                // only few cases i.e. sum is near to target by 1 num
                if(Math.abs(sum-target) < diff) {
                    diff = Math.abs(sum-target);
                    ans = sum;
                }
                
                if(sum > target) {
                    k--;
                } else {
                    j++;
                }
            }
        }
        
        return ans;
    }
}
```
