### Question
https://leetcode.com/problems/best-time-to-buy-and-sell-stock/

### Solution
```JAVA
class Solution {
    public int maxProfit(int[] prices) {
        // Solution 1
        int maxProfit = 0;
        int maxSellPrice = prices[prices.length-1];
        
        for(int i=prices.length-2; i>=0; i--) {
            if(maxSellPrice > prices[i] && maxSellPrice - prices[i] > maxProfit) {
                maxProfit = maxSellPrice - prices[i];
            } 
            
            if(maxSellPrice < prices[i]) {
                maxSellPrice = prices[i];
            }
        }
        
        return maxProfit;

        // Solution 2
        int maxProfit = 0;
        int min = Integer.MAX_VALUE;
        
        for(int i=0; i<prices.length; i++) {
            if(prices[i] < min) {
                min = prices[i];
            }
            
            if(prices[i]-min > maxProfit) {
                maxProfit = prices[i]-min;
            }
        }
        
        return maxProfit;
    }
}
```
