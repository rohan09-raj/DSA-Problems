### Question
https://leetcode.com/problems/longest-consecutive-sequence/

### Solution
```JAVA
class Solution {
    public int longestConsecutive(int[] nums) {
        HashSet<Integer> set = new HashSet<>();
        int count = 0;
        
        for(int num: nums) {
            set.add(num);
        }
        
        for(int num: nums) {
            int max = 1;
            int prev = num - 1;
            int next = num + 1;
            
            while(set.contains(prev)) {
                max++;
                set.remove(prev);
                prev--;
            }
            
            while(set.contains(next)) {
                max++;
                set.remove(next);
                next++;
            }
            
            count = Math.max(count, max);
        }
        
        return count;
    }
}


```
