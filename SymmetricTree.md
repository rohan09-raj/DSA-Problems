### Question
https://leetcode.com/problems/symmetric-tree/

### Solution
```JAVA
class Solution {
    public boolean isSymmetric(TreeNode root) {
        return symmetricHelper(root.left, root.right);
    }
    
    public boolean symmetricHelper(TreeNode rootLeft, TreeNode rootRight) {
        if(rootLeft == null && rootRight == null) {
            return true;
        }
        
        if((rootRight == null && rootLeft != null) || (rootLeft == null && rootRight != null) ) {
            return false;
        }
           
        return (rootLeft.val == rootRight.val) &&
            symmetricHelper(rootLeft.left, rootRight.right) &&
            symmetricHelper(rootLeft.right, rootRight.left);
    }
}
```
