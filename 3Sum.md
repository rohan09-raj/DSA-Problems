### Question
https://leetcode.com/problems/3sum/

### Solution
```JAVA
import java.util.*;

class Solution {
    public List<List<Integer>> threeSum(int[] nums) {
        Arrays.sort(nums);
        
        HashSet<List<Integer>> list = new HashSet<>();
                
        // This I was trying to achieve using pointer but it doesn't work
        for(int i=0; i<nums.length-2; i++) {
            
            int j = i+1;
            int k = nums.length - 1;
            
            while(j < k) {
                List<Integer> triplets = new ArrayList<>();

                if(nums[i] + nums[j] + nums[k] == 0) {
                    triplets.add(nums[i]);
                    triplets.add(nums[j]);
                    triplets.add(nums[k]);
                }

                // Previously I was doing k-- after adding 
                // and j++ on if triplets are not equal to 0
                if(nums[i] + nums[j] + nums[k] > 0) {
                    k--;
                } else {
                    j++;
                }


                if(!triplets.isEmpty()) {
                    list.add(triplets);
                }
            }
        }
        
        return new ArrayList<>(list);
    }
}
```
