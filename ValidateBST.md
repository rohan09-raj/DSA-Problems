### Question
https://leetcode.com/problems/validate-binary-search-tree/

### Solution
#### Approach - 1 (Wrong 72 out of 80 TestCases Passed)
```JAVA
class Solution {
    public boolean isValidBST(TreeNode root) {
        if(root == null) {
            return true;
        }
        
        Queue<TreeNode> queue = new LinkedList<>();      
        queue.add(root);
        
        while(!queue.isEmpty()) {
            int count = queue.size();
            
            for(int i=0; i<count; i++) {
                TreeNode curr = queue.remove();
                
                if(curr.left != null && curr.left.val < curr.val) {
                    queue.add(curr.left);
                } else if (curr.left != null && curr.left.val >= curr.val) {
                    return false;
                }
                
                if(curr.right != null && curr.right.val > curr.val) {
                    queue.add(curr.right);
                } else if (curr.right != null && curr.right.val <= curr.val) {
                    return false;
                }
            }
        }
        
        return true;
    }
}
```

#### Approach - 2 (Recursive)
```JAVA
class Solution {
    public boolean isValidBST(TreeNode root) {
        return verify(root, Long.MIN_VALUE, Long.MAX_VALUE);
    }
    
    private static boolean verify(TreeNode root, long min, long max) {
        if (root == null) {
            return true;   
        }
        if (root.val <= min || root.val >= max) {
            return false;
        };
        
        return verify(root.left, min, root.val) && verify(root.right, root.val, max);
    }
}
```

#### Approach - 3 (Iterative using BFS)
```JAVA
class Solution {
    public boolean isValidBST(TreeNode root) {
        if(root == null) {
            return true;
        }
        
        Queue<TreeNode> queue = new LinkedList();
        queue.add(root);
        
        int rootVal = root.val;
        int upRootVal = -1;
        boolean flag = false;
        
        TreeNode curr = queue.poll();
    
        while(curr != null) {
            if (curr.left != null) {
                if(curr.left.val < curr.val) {
                    if(curr.val > rootVal && curr.left.val <= rootVal) {
                        return false;
                    }
                    
                    queue.add(curr.left); 
                    TreeNode left = curr.left.right;
                    
                    while(left != null) {
                    // check in left.right < current root
                        if (left.val > curr.val) {
                            return false;
                        }  
                        left = left.right;
                    }

                } else {
                    return false;
                }
            }
            
            if (curr.right != null) {
                if(curr.right.val > curr.val) {
                    if(curr.val > rootVal && curr.right.val < rootVal) {
                        return false;
                    }
                    
                    if(curr.val < rootVal && curr.right.val >= rootVal) {
                        return false;
                    }
                    
                    queue.add(curr.right);
                } else {
                    return false;
                }
            }

            curr = queue.poll();
        }
        return true;
    }
}

```
