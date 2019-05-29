## 450二分搜索数中删除节点

### &准备知识

二叉树的结构：

(1)所有左子树的节点小于等于根节点

(2)所有右子树的节点大于等于根节点

(3)对于任意节点满足(1)(2)

所以二叉查找树查出节点的关键在于如何保证不破坏二叉查找树的性质。

### &问题分析

二叉查找树删除节点可以分为三种情况：

(1)删除叶子节点

叶子节点删除是最简单的情况，由于叶子节点没有左右子数，删除后不会破坏原有的树的结构。只需要找到节点并把它置为null即可。

(2)被删除的节点只有一个子节点

把待删除节点的父亲指向待删除节点的子节点即可。

(3)被删除的节点左右子数都有

这种情况是最复杂的，为了不破坏二叉查找树的结构，我们按照如下操作进行：

- 找出左子树中最大的值或者右子树的最小值val
- 将当前节点的值替换为val
- 在左子树或者右子树中找到val删除。

Note：由于二分查找树的性质，即找到当前节点的左子树的最右边的叶子节点或者右子树最左边的节点是符合要求的。并且不会破坏二叉查找树的结构。

### &代码

```java
class Solution {
    public TreeNode deleteNode(TreeNode root, int key) {
        if(root == null){
            return null;
        }
        int val = root.val;
        if(val > key){
            root.left = deleteNode(root.left,key);
        }
        else if(val < key){
            root.right = deleteNode(root.right,key);
        }
        else{
            //待删除节点没有左右孩子
            if(root.left == null && root.right == null){
                return null;
            }
            //待删除节点只有一个孩子
            if(root.left == null || root.right == null){
                return root.left !=null?root.left:root.right;
            }
            //待删除节点有两个孩子
            TreeNode next = maxNode(root.left);
            root.val = next.val;
            //这一步我得绞尽脑汁才能想到啊 当那个节点的值充当根节点时，
            //如何删除此节点？
            root.left = deleteNode(root.left,next.val);                                               
        }
        return root;
    }
		//找到左子树的最大值，一定位于左子树最右边的叶子节点
    public TreeNode maxNode(TreeNode node){
        TreeNode cur = node;
        while(cur != null && cur.right != null){
            cur = cur.right;
        }
        return cur;
    }   
}
```



