## Binary Tree Level Order Traversal

- [binary-tree-level-order-traversal] - leetcode

```csharp
Time: O(n)
Mem:  O(n)

/**
 * Definition for a binary tree node.
 * public class TreeNode {
 *     public int val;
 *     public TreeNode left;
 *     public TreeNode right;
 *     public TreeNode(int val=0, TreeNode left=null, TreeNode right=null) {
 *         this.val = val;
 *         this.left = left;
 *         this.right = right;
 *     }
 * }
 */

public IList<IList<int>> LevelOrder(TreeNode root) {

        if(root == null) return new List<IList<int>>();

        var q = new Queue<TreeNode>();
        q.Enqueue(root);

        var levels = new List<IList<int>>();
        while(q.Any()) {
            
            var cnt = q.Count();
            var partition = new List<int>();
            for(var i = 0; i < cnt; i ++) {
                var current = q.Dequeue();
                
                partition.Add(current.val);

                if(current.left != null) {
                    q.Enqueue(current.left);
                }

                if(current.right != null) {
                    q.Enqueue(current.right);
                }
            }
            
            if(partition.Any()) {
                levels.Add(partition);
            }
        }

        return levels;
    
    }

```



[binary-tree-level-order-traversal]: <https://leetcode.com/problems/binary-tree-level-order-traversal/>