### Question
https://leetcode.com/problems/find-common-characters

### Solution
```JAVA
class Solution {
    public List<String> commonChars(String[] words) {
      
      ArrayList<String> result = new ArrayList<>();
        
      if (words == null || words.length == 0) {
        return result;
      }
        
      HashMap<Character,Integer> map = new HashMap<>();
        
      for(char character : words[0].toCharArray()) {
        map.put(character, map.getOrDefault(character, 0) + 1);
      } 
        
      for(int i=1; i<words.length; i++) {
        HashMap<Character,Integer> tempMap = new HashMap<>();
            
        for(int j=0; j<words[i].length(); j++) {
          char character = words[i].charAt(j);
                    
          if(map.containsKey(character)) {
            tempMap.put(
              character, 
              (Math.min(
                map.get(character), 
                tempMap.getOrDefault(character, 0) + 1)
              ));
          }           
        }
        
        map = tempMap;
      }
        
      for(char character : map.keySet()) {
        for(int i=0; i<map.get(character); i++) {
          result.add("" + character);
        }
      }
        
      return result; 
    }
}
```
