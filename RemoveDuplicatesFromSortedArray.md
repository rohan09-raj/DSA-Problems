### Question
https://leetcode.com/problems/remove-duplicates-from-sorted-array

### Solution
```JAVA
class Solution {
    public int removeDuplicates(int[] nums) {
        int size = nums.length;
        int j=0;
        
        for(int i=0; i<size-1; i++) {
            if(nums[i] != nums[i+1]) {
                nums[j++] = nums[i];
            }
        }
        
        nums[j++] = nums[size-1];
        return j;
    }
}
```
