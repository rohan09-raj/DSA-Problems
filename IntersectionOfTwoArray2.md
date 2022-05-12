### Question
https://leetcode.com/problems/intersection-of-two-arrays-ii

### Solution
```JAVA
class Solution {
    public int[] intersect(int[] nums1, int[] nums2) {
        int[] counterArray = new int[1001];
        List<Integer> intersectionList = new ArrayList<>();
        
        for(int num: nums1) {
            counterArray[num]++;
        }
        
        for(int num: nums2) {
            if(counterArray[num] > 0) {
                intersectionList.add(num);
                counterArray[num]--;
            }
        }
        
        int[] intersection = new int[intersectionList.size()];
        
        for(int i=0; i<intersectionList.size(); i++) {
            intersection[i] = intersectionList.get(i);
        }
        
        return intersection;
        
    }
}
```
