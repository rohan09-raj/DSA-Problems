### Question
https://leetcode.com/problems/sort-colors/

### Solution
```JAVA
class Solution {
    public void sortColors(int[] nums) {  
        int count0 = 0;
        int count1 = 0;
        int count2 = 0;
        
        for(int i=0; i<nums.length; i++) {
            if(nums[i] == 0) {
                count0 += 1;
            } else if (nums[i] == 1) {
                count1 += 1;
            } else {
                count2 += 1;
            }
        }

        int j=0;
        
        while(count0 != 0) {
            count0--;
            nums[j] = 0;
            j++;
        }
            
        while(count1 != 0) {
            count1--;
            nums[j] = 1;
            j++;
        }
        
        while(count2 != 0) {
            count2--;
            nums[j] = 2;
            j++;
        }
    }
}
```
