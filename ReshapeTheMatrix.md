### Question
https://leetcode.com/problems/reshape-the-matrix

### Solution
```JAVA
class Solution {
    public int[][] matrixReshape(int[][] mat, int r, int c) {
        int rowp = 0;
        int colp = 0;
        
        if(mat.length * mat[0].length != r*c) {
            return mat;
        }
        
        int[][] result = new int[r][c];
        
        for(int i=0; i<mat.length; i++) {
            for (int j=0; j<mat[i].length; j++) {
                result[rowp][colp] = mat[i][j];
                colp++;
                
                if(colp == c) {
                    colp = 0;
                    rowp++;
                }
            }
        }
    
        return result;    
    }
}
```
