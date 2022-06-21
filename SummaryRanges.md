### Question
https://leetcode.com/problems/summary-ranges

### Solution
Optimized Approach
```JAVA
class Solution {
    public List<String> summaryRanges(int[] nums) {
        List<String> list = new ArrayList<>();
        
        if(nums.length == 0)
            return list;
        
        int begin = 0;
        String arrow = "->";
        for(int i=1; i<nums.length; i++){
            if(nums[i] == nums[i-1]+1)
                continue;
            
            StringBuilder sb = new StringBuilder();
            sb.append(nums[begin]);
            
            if(i-1 > begin){
                sb.append(arrow);
                sb.append(nums[i-1]);
            }
            
            list.add(sb.toString());
            begin = i;
        }
        
        StringBuilder sb = new StringBuilder();
        sb.append(nums[begin]);
        
        if(nums.length-1 > begin){
            sb.append(arrow);
            sb.append(nums[nums.length-1]);
        }
        list.add(sb.toString());
        return list;
    }
}
```

My Approach -> Some Failing Testcases 
```JAVA
class Solution {
    public List<String> summaryRanges(int[] nums) {
        if(nums.length == 0) {
            return new ArrayList<>();
        }
        
        List<String> result = new ArrayList<>();
        
        int[] arr = new int[2];
        arr[0] = nums[0];
        
        for(int i=1; i<nums.length; i++) {
            if(nums[i] == (nums[i-1] + 1)) {
                arr[1] = nums[i];
            } else {
                if(arr[0] == arr[1]) {
                    String range = "" + arr[0];
                    result.add(range);
                } else {
                    String range = arr[0] + "->" + arr[1];
                    result.add(range);
                }
                
                arr[0] = nums[i];
                arr[1] = nums[i];
            }
        }
        
        if(arr[0] == arr[1]) {
            String range = "" + arr[0];
            result.add(range);
        } else {
            String range = arr[0] + "->" + arr[1];
            result.add(range);
        }
        
        return result;
    }
}
```
