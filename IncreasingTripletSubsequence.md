### Question
https://leetcode.com/problems/increasing-triplet-subsequence/

### Solution
```JAVA
class Solution {
    public boolean increasingTriplet(int[] nums) { 
        int min = Integer.MAX_VALUE;
        int secondMin = Integer.MAX_VALUE;
        
        for(int num: nums) {
            if(num <= min) {
                min = num;
            } else if (num <= secondMin) {
                secondMin = num;
            } else {
                return true;
            }
        }
        return false;
    }
}
```

**1st Approach (Wrong Solution)** - **70** of **76** Testcases passed
```JAVA
class Solution {
    public boolean increasingTriplet(int[] nums) { 
        for(int i=0; i<nums.length-2; i++) {
            int j = i+1;
            int k = nums.length-1;
            
            while(j < k) {
                if(nums[i] < nums[j] && nums[j] < nums[k]) {
                    return true;
                }    
                
                if (nums[j] > nums[k]) {
                    k--;
                } else {
                    j++;
                }  
            }
        }
        return false;
    }
}
```
