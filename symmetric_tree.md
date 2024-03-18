## Symmetric Tree

- [symmetric-tree] - leetcode

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

public bool IsSymmetric(TreeNode root) {
        
        if(root.left is null && root.right is null) {
            return true;
        }

        var q = new Queue<TreeNode>();

        q.Enqueue(root);
        q.Enqueue(root);

        while(q.Any()) {
            var node1 = q.Dequeue();
            var node2 = q.Dequeue();

            if(node1 is null && node2 is null) {
                continue;
            }

            if(node1 is null || node2 is null) {
                return false;
            }

            if(node1.val != node2.val) {
                return false;
            }

            q.Enqueue(node1.left);
            q.Enqueue(node2.right);
            q.Enqueue(node1.right);
            q.Enqueue(node2.left);
        }

        return true;
    }

```



[symmetric-tree]: <https://leetcode.com/problems/symmetric-tree/>