### Question


### Solution
```JAVA
class Solution {
    public int[][] merge(int[][] intervals) {
        if(intervals.length < 2) {
            return intervals;
        }
        
        Arrays.sort(intervals, (a,b) -> a[0] - b[0]);
        
        List<int[]> result = new ArrayList<>();
        
        int prevStart = intervals[0][0];
        int prevEnd = intervals[0][1];
        
        result.add(intervals[0]);
        
        for(int i=1; i<intervals.length; i++) {
            if(prevEnd >= intervals[i][0]) {
                int[] newInterval = new int[]{prevStart, Math.max(prevEnd, intervals[i][1])};
                
                result.remove(result.size()-1);
                result.add(newInterval);
                prevStart = newInterval[0];
                prevEnd = newInterval[1];
            } else {
                result.add(intervals[i]);
                prevStart = intervals[i][0];
                prevEnd = intervals[i][1];
            }
        }
        
        return result.toArray(new int[result.size()][]);
    }
}
```
