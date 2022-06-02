### Question
https://leetcode.com/problems/majority-element/

### Solution
#### Approach - 1 (Boyer-Moore Majority Voting Algorithm)
```JAVA
class Solution {
    public int majorityElement(int[] nums) {
        int count = 1;
        int majority = nums[0];
        
        for(int i=1; i<nums.length; i++) {
            if(count == 0) {
                count = 1;
                majority = nums[i];
            } else if (nums[i] == majority) {
                count += 1;
            } else {
                count -= 1;
            }
        }
        
        return majority;
    }
}
```

#### Approach - 2 (Takes extra space)
```JAVA
import java.util.*;

class Solution {
    public int majorityElement(int[] nums) {
        HashMap<Integer, Integer> map = new HashMap<>();
        
        for(int i=0; i<nums.length; i++) {
            if(!map.containsKey(nums[i])) {
                map.put(nums[i], 1);
            } else {
                int count = map.get(nums[i]);
                map.put(nums[i], count + 1);   
            }
        }
    
        Map.Entry<Integer, Integer> maxEntry = null;
        for(Map.Entry<Integer, Integer> entry : map.entrySet()) {
            if(maxEntry == null || entry.getValue() > maxEntry.getValue()) {
                maxEntry = entry;
            }
        }
   
        return maxEntry.getKey();
    }
}
```
