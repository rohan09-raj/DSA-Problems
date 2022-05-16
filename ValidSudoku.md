### Question
https://leetcode.com/problems/valid-sudoku/

### Solution
```JAVA
class Solution {
    public boolean isValidSudoku(char[][] board) {
        HashSet set = new HashSet();
        
        for(int i=0; i<9; i++) {
            for(int j=0; j<9; j++) {
                if(board[i][j] != '.') {
                    char current = board[i][j];
                    if( 
                        !set.add("Row : " + i + "Value : " + current) ||
                        !set.add("Column : " + j + "Value : " + current) ||
                        !set.add("Block : " + i/3 + j/3 + "Value : " + current)
                    ) {
                        return false;
                    }
                }
            }
        }
        
        return true;
    }
}
```
