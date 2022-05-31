### Question
https://leetcode.com/problems/invert-binary-tree/

### Solution
```JAVA
class Solution {
    public TreeNode invertTree(TreeNode root) {
        if (root == null) {
            return null;
        }
        
        TreeNode swapNode = root;
        
        swap(swapNode);
        invertTree(root.left);
        invertTree(root.right);
        
        return swapNode;
    }
    
    public TreeNode swap(TreeNode root) {
        TreeNode left = root.left;
        root.left = root.right;
        root.right = left;
        return root;
    }
}
```
