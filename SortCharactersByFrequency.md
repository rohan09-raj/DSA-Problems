### Question
https://leetcode.com/problems/sort-characters-by-frequency/

### Solution
```JAVA
import java.util.*;

class Solution {
    
    class Pair implements Comparable<Pair>{
        char c;
        int f;
        public Pair(char c,int f){
            this.c = c;
            this.f = f;
        }
        public int compareTo(Pair p){
            return f-p.f;
        }
    }
    
    public String frequencySort(String s) {
        HashMap<Character, Integer> freq = new HashMap<>();
        PriorityQueue<Pair> sort = new PriorityQueue<>(Collections.reverseOrder());
        
        String res = "";
        
        for(int i=0; i<s.length(); i++) {
            if(freq.containsKey(s.charAt(i))) freq.put(s.charAt(i), freq.get(s.charAt(i)) + 1);
            else freq.put(s.charAt(i), 1);
        }
        
        for(Map.Entry<Character, Integer> element : freq.entrySet()) {
            sort.offer(new Pair(element.getKey(), element.getValue()));
        }
        
        StringBuilder sNew = new StringBuilder();
        sNew.append(res);
        
        while(sort.size() != 0) {
            Pair pair = sort.poll();
            String repeat = String.valueOf(pair.c).repeat(pair.f);
            sNew.append(repeat);
        }
        
        return sNew.toString();
    }
}
```
