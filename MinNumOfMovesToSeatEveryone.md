### Question
https://leetcode.com/problems/minimum-number-of-moves-to-seat-everyone

### Solution
```JAVA
class Solution {
    public int minMovesToSeat(int[] seats, int[] students) {
        Arrays.sort(seats);
        Arrays.sort(students);
        
        int moves = 0;
        
        for(int i=0; i<seats.length; i++) {
            if(seats[i] > students[i]) {
                moves += seats[i] - students[i];    
            } else {
                moves += students[i] - seats[i];
            }  
        }
        
        return moves;
    }
}
```
