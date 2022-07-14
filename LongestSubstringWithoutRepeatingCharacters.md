### Question
https://leetcode.com/problems/longest-substring-without-repeating-characters/

### Solution
```JAVA
class Solution {
    public int lengthOfLongestSubstring(String s) {
        int ans = 0;
        int start=0;
        Set<Character> search = new HashSet<>();
        for(int end=0; end<s.length(); end++){
            if(search.contains(s.charAt(end))){
                while(s.charAt(start) != s.charAt(end)){
                    search.remove(s.charAt(start));
                    start++;
                }
                start++;
            }else{
                search.add(s.charAt(end));
            }
            ans = Math.max(ans, end-start+1);
            
        }
        return ans;
    }
}
```
