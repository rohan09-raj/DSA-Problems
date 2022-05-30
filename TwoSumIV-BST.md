### Question
https://leetcode.com/problems/two-sum-iv-input-is-a-bst/

### Solution
```JAVA
class Solution {
    public boolean findTarget(TreeNode root, int k) {
        if (root == null) {
            return false;
        }
        
        Queue<TreeNode> queue = new LinkedList<>();
        HashSet<Integer> set = new HashSet<>();
        
        queue.add(root);
        
        while(!queue.isEmpty()) {
            int count = queue.size(); //Miseed this count
            
            for(int i=0; i<count; i++) { // Also, missed this loop
                TreeNode currentNode = queue.remove();
            
                if(set.contains(k-currentNode.val)) {
                    return true;
                }

                set.add(currentNode.val);

                if(currentNode.left != null) {
                    queue.add(currentNode.left);
                }

                if(currentNode.right != null) {
                    queue.add(currentNode.right);
                }   
            }
        } 
        return false;
    }
}
```
