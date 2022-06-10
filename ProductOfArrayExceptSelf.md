### Question
https://leetcode.com/problems/product-of-array-except-self/

### Solution
```JAVA
class Solution {
    public int[] productExceptSelf(int[] nums) {            
        int n = nums.length;
        int[] leftProduct = new int[n];
        int[] rightProduct = new int[n];
        int[] ans = new int[n];

        leftProduct[0] = nums[0];
        rightProduct[n-1] = nums[n-1];
        
        // Left Product : Prefix
        for(int i=1; i<n; i++) {
            leftProduct[i] = nums[i] * leftProduct[i-1];
        }

        // Right Product : Suffix
        for(int i=n-2; i>=0; i--) {
            rightProduct[i] = nums[i] * rightProduct[i+1];
        }
        
        for(int i=0; i<n; i++) {
            if(i == 0) {
                ans[i] = rightProduct[i+1];
            } else if (i == n-1) {
                ans[i] = leftProduct[i-1];
            } else {
                ans[i] = leftProduct[i-1] * rightProduct[i+1];
            }
        }
        
        return ans;
    }
}
```
