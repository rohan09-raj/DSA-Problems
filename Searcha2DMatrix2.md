### Question
https://leetcode.com/problems/search-a-2d-matrix-ii/

### Solution
```JAVA
class Solution {
    public boolean searchMatrix(int[][] matrix, int target) {
        int numRows = matrix.length;
        int numCols = matrix[0].length;
        
        int rowIndex = numRows-1;
        int colIndex = 0;
        
        while(rowIndex >= 0 && colIndex < numCols) {
            int num = matrix[rowIndex][colIndex];
            
            if(num == target) {
                return true;
            } else if (num > target) {
                rowIndex--;
            } else {
                colIndex++;
            }
        }
        return false;
    }
}
```
