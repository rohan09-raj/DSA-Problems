### Question
https://leetcode.com/problems/count-and-say/

### Solution
**Optimised Solution**
```JAVA
class Solution {
    public String countAndSay(int n) {
        if(n == 1) return "1"; 
        String prev = countAndSay(n - 1); 
        StringBuilder str = new StringBuilder();
        int i = 0;
        while(i < prev.length()) {
            char curr = prev.charAt(i);
            int j = 0;
            while(i+j < prev.length() && prev.charAt(i+j) == curr) j++;
            str.append(j);
            str.append(curr);
            i += j;
        }
        return str.toString();
    }
} 
```

**Average Solution**
```JAVA
class Solution {
    public String countAndSay(int n) {
        if(n == 1) return "1"; 
        if(n == 2) return "11";
        
        String s = "11";
        
        for(int i=2; i<n; i++) {
            String eachRes = "";
            int counter = 1;
            s = s + '&';
            for(int j=1; j<s.length(); j++) {
                if(s.charAt(j) != s.charAt(j-1)) {
                    eachRes = eachRes + Integer.toString(counter);
                    eachRes = eachRes + s.charAt(j-1);
                    counter = 1;
                } else {
                    counter++;
                }
            }
            s = eachRes;
        }
        return s;
    }
}

```
