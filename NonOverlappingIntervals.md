### Question
https://leetcode.com/problems/non-overlapping-intervals/

### Solution
```JAVA
class Solution {
    public int eraseOverlapIntervals(int[][] intervals) {
        Arrays.sort(intervals, (a, b) -> Integer.compare(a[0], b[0]));

        int[] prev = intervals[0];
        int count = 0;
        
        for(int i=1; i<intervals.length; i++) {
            int[] curr = intervals[i];
            
            if(prev[1] > curr[0]) {
                count += 1;
                prev[1] = Math.min(prev[1], curr[1]);
            } else {
                prev[0] = curr[0];
                prev[1] = curr[1];
            }
        }

        return count;
    }
}
```
