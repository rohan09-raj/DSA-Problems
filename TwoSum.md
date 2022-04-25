### Question
https://leetcode.com/problems/two-sum/

### Solution
```JAVA
class Solution {
    public int[] twoSum(int[] nums, int target) {
        int[] res = new int[2];
        HashMap<Integer, Integer> hp = new HashMap<>();
        for(int i=0; i<nums.length; i++) {
           if(hp.containsKey(target - nums[i])) {
               res[0] = i;
               res[1] = hp.get(target - nums[i]);
               return res;
           } else {
               hp.put(nums[i], i);
           }
        }
        return res;
    }
}
```
