### Question
https://leetcode.com/problems/insert-into-a-binary-search-tree/

### Solution
```JAVA
class Solution {
    public TreeNode insertIntoBST(TreeNode root, int val) {
        if(root == null) {
            TreeNode newNode = new TreeNode();
            newNode.val = val;
            return newNode;
        } else if (val <= root.val) {
            root.left = insertIntoBST(root.left, val);
            return root;
        } else {
            root.right = insertIntoBST(root.right, val);
            return root;
        }
    }
}
```
