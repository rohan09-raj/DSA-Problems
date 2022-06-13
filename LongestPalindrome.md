### Question
https://leetcode.com/problems/longest-palindrome/

### Solution
```JAVA
class Solution {
    public int longestPalindrome(String s) {
        int result=0;
        int[] frequency = new int[128];
        for(char c:s.toCharArray()){
            frequency[c]++;
        }
        
        for(int i=0; i<frequency.length; i++){
            result = result + ((frequency[i]/2)*2);
            if(frequency[i]%2 != 0 && result%2 == 0){
                result+=1;
            }
        }
        return result;
    }
}
```
