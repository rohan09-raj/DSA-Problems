### Question
https://leetcode.com/problems/sqrtx/

### Solution
```JAVA
class Solution {
    public int mySqrt(int x) {  
        int start = 0;
        int end = x;
        while (true) {
            if (start * start == x) {
                return start;
            }
            if (end * end == x) {
                return end;
            }
            if (end - start <= 1) {
                return start;
            }
            long mid = (start + end) / 2;
            if (mid * mid == x) {
                return (int) mid;
            } else if (mid * mid > x) {
                end = (int) mid;
            } else {
                start = (int) mid;
            }
        }
    }
}
```

#### Approach - 1 (Wrong)
```JAVA
class Solution {
    public int mySqrt(int x) {  
        int start = 0;
        int end = x/2;
        int mid = start + ((end - start)/2);
        
        if(x == 1) {
            return 1;
        }
        
        while(start <= end) {
            mid = start + ((end - start)/2);
            
            if(mid * mid < x) {
                 start = mid + 1;
            } else if (mid * mid > x) {
                end = mid - 1;
            } else {
                return mid;
            }
        }
        return end;
    }
}
```

#### Approach - 2 (Wrong)
```JAVA
class Solution {
    public int mySqrt(int x) {  
        int counter = 1; 
        
        while(true) {
            if(counter * counter > x) {
                return counter - 1;
            } else if (counter * counter == x) {
                return counter;
            } else {
                counter++;
            }
        }
    }
}
```
