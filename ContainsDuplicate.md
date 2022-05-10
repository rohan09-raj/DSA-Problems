### Question
https://leetcode.com/problems/contains-duplicate/

### Solution
```JAVA
class Solution {
    public boolean containsDuplicate(int[] nums) {
        
        // Solution - 1
        HashMap<Integer, Integer> hp = new HashMap<>(); 
        
        for(int i=0; i<nums.length; i++) {
            if (!hp.containsKey(nums[i])) {
                hp.put(nums[i], i);
            } else {
                return true;
            }
        }
        
        return false;
        
        
        // Solution - 2
        Set set = new HashSet();
        for (int i: nums) {
            boolean isPresent;
            
            isPresent = set.add(i);
            
            if (!isPresent) {
                return true;
            }
            
        }
        
        return false;
    }
}
```
