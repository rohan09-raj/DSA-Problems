### Question
https://leetcode.com/problems/move-zeroes/

### Solution
```JAVA
class Solution {
    public void moveZeroes(int[] nums) {
        int countNonZero = 0;
        
        for(int i=0; i<nums.length; i++) {
            if(nums[i] != 0) {
                nums[countNonZero] = nums[i];
                countNonZero++;
            }
        }
        
        while(countNonZero < nums.length) {
            nums[countNonZero] = 0;
            countNonZero++;
        }
    }
}
```
