### Question
https://leetcode.com/problems/repeated-dna-sequences

### Solution
```JAVA
class Solution {
    public static List<String> findRepeatedDnaSequences(String s) {
        HashMap<String, Integer> map = new HashMap<>();
  
        for(int i=0; i+9<s.length(); i++) {
            String sequence = s.substring(i, i+10);
            map.put(sequence, map.getOrDefault(sequence, 0) + 1);
        }
        
        List<String> result = new ArrayList<>();
        
        for(Map.Entry mapElement : map.entrySet()) {
            if((int) mapElement.getValue() > 1) {
                result.add((String) mapElement.getKey());
            }
        }
        return result;
    }
}
```
