### Question
https://leetcode.com/problems/contains-duplicate-ii

### Solution
```JAVA
class Solution {
    public boolean containsNearbyDuplicate(int[] nums, int k) {
        HashMap<Integer, Integer> hm = new HashMap<>();
        
        for(int i=0; i<nums.length; i++) {
            if(!hm.containsKey(nums[i])) {
                hm.put(nums[i], i);
            } else {
                if (hm.get(nums[i]) != null) {
                    if(Math.abs(i-hm.get(nums[i])) <= k) {
                        return true;
                    }
                
                    hm.replace(nums[i], i);
                }
            }
        }
        
        return false;
    }
}
```
