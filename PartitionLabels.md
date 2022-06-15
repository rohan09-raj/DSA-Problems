### Question
https://leetcode.com/problems/partition-labels

### Solution
```JAVA
class Solution {
    public List<Integer> partitionLabels(String s) {
        HashMap<Character, Integer> map = new HashMap<>();

        for(int i=0; i<s.length(); i++) {
            char currChar = s.charAt(i);
            map.put(currChar, i);
        }
        
        int prev = -1;
        int max = 0;
        List<Integer> partition = new ArrayList<>();
        
        for(int i=0; i<s.length(); i++) {
            char currChar = s.charAt(i);
            max = Math.max(max, map.get(currChar));
            
            if(max == i) {
                partition.add(max - prev);
                prev = max;
            }
        }
        
        return partition;
    }    
}

```
