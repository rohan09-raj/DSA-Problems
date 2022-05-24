### Question
https://leetcode.com/problems/binary-tree-preorder-traversal/

### Solution
```JAVA
class Solution {
    public List<Integer> preorderTraversal(TreeNode root) {
        List<Integer> list = new ArrayList<>();
        preorderTraversalHelper(root, list);
                
        return list;
    }
    
    public void preorderTraversalHelper(TreeNode root, List list) {
        if(root != null) {
            list.add(root.val);
            preorderTraversalHelper(root.left, list);
            preorderTraversalHelper(root.right, list);
        }
    }
}
```

### Question
https://leetcode.com/problems/binary-tree-inorder-traversal/

### Solution
```JAVA
class Solution {
    public List<Integer> inorderTraversal(TreeNode root) {
        List<Integer> list = new ArrayList<>();
        inorderTraversalHelper(root, list);
        
        return list;
    }
    
    public void inorderTraversalHelper(TreeNode root, List list) {
        if(root != null) {
            inorderTraversalHelper(root.left, list);
            list.add(root.val);
            inorderTraversalHelper(root.right, list);
        }
    }
}
```

### Question
https://leetcode.com/problems/binary-tree-postorder-traversal/

### Solution
```JAVA
class Solution {
    public List<Integer> postorderTraversal(TreeNode root) {
        List<Integer> list = new ArrayList<>();
        postorderTraversalHelper(root, list);
        
        return list;
    }
    
    public void postorderTraversalHelper(TreeNode root, List list) {
        if(root != null) {
            postorderTraversalHelper(root.left, list);
            postorderTraversalHelper(root.right, list);
            list.add(root.val);
        }
    }
}
```

### Question
https://leetcode.com/problems/binary-tree-level-order-traversal

### Solution
```JAVA
class Solution {
    public List<List<Integer>> levelOrder(TreeNode root) {
        List<List<Integer>> list = new ArrayList<>();
        
        if(root == null) {
            return list;
        }
        
        Queue<TreeNode> queue = new LinkedList<>();
        
        queue.add(root);
        
        while(!queue.isEmpty()) {
            List<Integer> level = new ArrayList<>();
            int queueLength = queue.size();
            
            for(int i=0; i<queueLength; i++) {
                TreeNode current = queue.remove();
                level.add(current.val);
                
                if(current.left != null) {
                    queue.add(current.left);
                }
                
                if(current.right != null) {
                    queue.add(current.right);
                }
            }
            
            list.add(level);
        }
        
        return list;
    }
}
```
