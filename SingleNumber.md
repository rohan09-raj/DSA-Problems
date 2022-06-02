### Question
https://leetcode.com/problems/single-number/

### Solution
#### Approach - 1 (Time Complexity - O(n)
```JAVA
import java.util.*;

class Solution {
    public int singleNumber(int[] nums) {
        int single = nums[0];
        
        for(int i=1; i<nums.length; i++) {
            single = single ^ nums[i];
        }
        
        return single;
    }
}
```

#### Approach - 2 (Time Complexity - O(nlogn) 
```JAVA
import java.util.*;

class Solution {
    public int singleNumber(int[] nums) {
        if(nums.length == 1) {
            return nums[0];
        }
        
        Arrays.sort(nums);
        
        for(int i=0; i<nums.length-1; i+=2) {
            if(nums[i] != nums[i+1]) {
                return nums[i];
            }
        }
        return nums[nums.length - 1];
    }
}
```
