### Question
https://leetcode.com/problems/pascals-triangle-ii/

### Solution
**Optimised Solution**
```JAVA
class Solution {
    public List<Integer> getRow(int rowIndex) {        
        List<Integer> result = new ArrayList<>();
        
        for(int i=0; i<=rowIndex; i++) {
            result.add(1);
            int tmp = result.get(0);
            
            for(int j=1;j<result.size()-1;j++){
                int tmp2 = result.get(j);
                result.set(j,result.get(j)+tmp);
                tmp = tmp2;
            }
        }   
        return result;
    }
}
```
**My Solution**
```JAVA
class Solution {
    public List<Integer> getRow(int rowIndex) {        
        List<List<Integer>> result = generate(rowIndex);
        return result.get(rowIndex);
    }
    
    public static List<List<Integer>> generate(int rowIndex) {
        List<List<Integer>> triangle = new ArrayList<>();
        List<Integer> prev = null;
        
        for(int i=0; i<=rowIndex; i++) {
            List<Integer> rowList = new ArrayList<>();
            
            for(int j=0; j<=i; j++) {
                if(j==0 || j==i) {
                    rowList.add(1);
                } else {
                    rowList.add(prev.get(j) + prev.get(j-1));
                }
            } 
            prev = rowList;
            triangle.add(rowList);
        }
        return triangle;
    }
}
```
