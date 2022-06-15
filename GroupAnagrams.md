### Question
https://leetcode.com/problems/group-anagrams/

### Solution
```JAVA
class Solution {
    public List<List<String>> groupAnagrams(String[] strs) {
        HashMap<String, List<String>> map = new HashMap();
        
        for(int i=0; i<strs.length; i++) {
            char[] sorted = strs[i].toCharArray();
            Arrays.sort(sorted);
            String key = new String(sorted);
            
            if(map.containsKey(key)) { 
                map.get(key).add(strs[i]);
            } else {
                map.put(key, new ArrayList(List.of(strs[i])));
            }
        }
        return new ArrayList(map.values());
    }
}
```
