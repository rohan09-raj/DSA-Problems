### Question
https://leetcode.com/problems/lowest-common-ancestor-of-a-binary-search-tree/

### Solution
```JAVA
class Solution {
    public TreeNode lowestCommonAncestor(TreeNode root, TreeNode p, TreeNode q) {
        TreeNode node = root;
        
        while(node != null) {
            if (node.val < p.val && node.val < q.val)
                node = node.right;
            else if (node.val > p.val && node.val > q.val)
                node = node.left;
            else
                return node;   
        }
        
        return node;    
    }
}
```
