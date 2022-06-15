### Question
https://leetcode.com/problems/longest-common-prefix/

### Solution
**Optmised Approach**
```JAVA
class Solution {
    public String longestCommonPrefix(String[] strs) {
        String smallestString = strs[0];
        for (int i = 1; i < strs.length; i++) {
          if (strs[i].length() < smallestString.length()) {
            smallestString = strs[i];
          }
        }

        StringBuilder prefix = new StringBuilder("");
        for (int i = 0; i < smallestString.length(); i++) {
          char c = smallestString.charAt(i);
          
          for (int j = 0; j < strs.length; j++) {
            if (strs[j].charAt(i) != c) {
              return prefix.toString();
            }
          }
          prefix = prefix.append(c);
        }
        return prefix.toString();
    }
}
```

**My Approach**
```JAVA
class Solution {
    public String longestCommonPrefix(String[] strs) {
        String prev = "";
        String result = strs[0];
        
        for(int i=1; i<strs.length; i++) {
            String current = strs[i];
            
            for(int j=0; j<Math.min(current.length(), result.length()); j++) {
                if(current.charAt(j) == result.charAt(j)) {
                    prev += current.charAt(j);
                } else {
                    break;
                }
            }
            result = prev;
            prev = "";
        }
        return result;
    }
}
```
