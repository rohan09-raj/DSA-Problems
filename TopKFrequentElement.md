### Question
https://leetcode.com/problems/top-k-frequent-elements/

### Solution
```JAVA
class Solution {
    
    public class Pair implements Comparable<Pair> {
        int element;
        int frequency;
        
        public Pair(int element, int frequency) {
            this.element = element;
            this.frequency = frequency;
        }
        
        public int compareTo(Pair p) {
            return frequency - p.frequency;
        }
        
    }
    
    public int[] topKFrequent(int[] nums, int k) {
        int[] res = new int[k];
        HashMap<Integer, Integer> map = new HashMap<>();
        PriorityQueue<Pair> freq = new PriorityQueue<>(Collections.reverseOrder());
        
        for(int val: nums) {
            if(!map.containsKey(val)) {
                map.put(val, 1);
            } else {
                map.put(val, map.get(val) + 1);
            }
        }
        
        for(Map.Entry<Integer, Integer> entry : map.entrySet()) {
            freq.offer(new Pair(entry.getKey(), entry.getValue()));
        }
        
        for(int i=0; i<k; i++) {
            Pair pair = freq.poll();
            res[i] = pair.element;
        }
        
        return res;
    }
}
```
