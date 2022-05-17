### Question
https://leetcode.com/problems/first-unique-character-in-a-string/

### Solution
```JAVA
// Solution - 1
class Solution {
    public int firstUniqChar(String s) {
        HashMap<Character, Integer> hash = new HashMap<>();
        
        for(int i=0; i<s.length(); i++) {
            char character = s.charAt(i);
            
            if(hash.containsKey(character)) {
                hash.put(character, hash.get(character) + 1);
            } else {
                hash.put(character, 1);
            }
        }
        
        for(int i=0; i<s.length(); i++) {
            if(hash.get(s.charAt(i)) == 1) {
                return i;
            }
        }
        
        return -1;
    }
}

// Solution - 2
class Solution {
    public int firstUniqChar(String s) {
        int[] frequency = new int[26]; 
        
        for(int i=0; i<s.length(); i++) {
            frequency[s.charAt(i) - 'a']++;
        }
        
        for(int i=0; i<s.length(); i++) {
            if(frequency[s.charAt(i) - 'a'] == 1) {
                return i;
            }
        }
        
        return -1;
    }
}
```
