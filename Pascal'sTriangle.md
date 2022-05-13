### Question
https://leetcode.com/problems/pascals-triangle

### Solution
```JAVA
class Solution {
    public List<List<Integer>> generate(int numRows) {
        List<List<Integer>> triangle = new ArrayList<List<Integer>>();
        List<Integer> prev = null;
        
        for(int i=0; i<numRows; i++) {
            List<Integer> result = new ArrayList<>();
            
            for(int j=0; j<=i; j++) {
                if(j==0 || j==i) {
                    res.add(1);
                } else {
                    res.add(prev.get(j)+prev.get(j-1));
                }   
            }
            
            prev = res;
            triangle.add(res);
        }
        return triangle;
    }
}
```

### Wrong Solution
```JAVA
class Solution {
    public List<List<Integer>> generate(int numRows) {
        List<List<Integer>> pascalTriangle = new ArrayList<>();

        for(int i=0; i<numRows; i++) {
            List<Integer> list = new ArrayList<>();
            
            for(int j=0; j<=i; j++) {
                list.add(factorial(i)/(factorial(i-j)*factorial(j)));
            }
            
            pascalTriangle.add(list);
        }
        
        return pascalTriangle;
    }
    
    public int factorial(int elem) {
        if(elem == 0) {
            return 1;
        }
        
        return elem * factorial(elem-1);
    } 
}
```
