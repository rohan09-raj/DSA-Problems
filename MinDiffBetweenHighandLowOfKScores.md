### Question
https://leetcode.com/problems/minimum-difference-between-highest-and-lowest-of-k-scores/

### Solution
```JAVA
class Solution {
    public int minimumDifference(int[] nums, int k) {
        int minDiff = Integer.MAX_VALUE;
        
        Arrays.sort(nums);
        
        for(int i=k-1; i<nums.length; i++) {
            if(minDiff > nums[i] - nums[i - (k-1)]) {
                minDiff = nums[i] - nums[i - (k-1)];
            }
        }
                
        return minDiff;
    }
}
```
