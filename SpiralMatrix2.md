### Question
https://leetcode.com/problems/spiral-matrix-ii/

### Solution
```JAVA
class Solution {
    public int[][] generateMatrix(int n) {
        int[][] spiral = new int[n][n];
        generate(0, spiral, n, 1);
        return spiral;
    }
    
    public void generate(int layer, int[][] spiral, int n, int count) {
        if(n==0) {
            return;
        }
        
        if(n==1) {
            spiral[layer][layer] = count;
            return;
        }
        
        for(int col=layer; col<layer+n-1; col++) {
            spiral[layer][col] = count++;
        }
        
        for(int row=layer; row<layer+n-1; row++) {
            spiral[row][layer+n-1] = count++;
        }
        
        for(int col=layer+n-1; col>=layer+1; col--) {
            spiral[layer+n-1][col] = count++;
        }
        
        for(int row=layer+n-1; row>=layer+1; row--) {
            spiral[row][layer] = count++;
        }
        
        generate(layer+1, spiral, n-2, count);
    }
}
```
