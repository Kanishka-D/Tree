# Tree

BINARY TREE LEVEL ORDER TRAVERSAL

Given the root of a binary tree, return the level order traversal of its nodes' values. (i.e., from left to right, level by level).

 

Example 1:


Input: root = [3,9,20,null,null,15,7]
Output: [[3],[9,20],[15,7]]


/**
 * Definition for a binary tree node.
 * public class TreeNode {
 *     int val;
 *     TreeNode left;
 *     TreeNode right;
 *     TreeNode() {}
 *     TreeNode(int val) { this.val = val; }
 *     TreeNode(int val, TreeNode left, TreeNode right) {
 *         this.val = val;
 *         this.left = left;
 *         this.right = right;
 *     }
 * }
 */
class Solution {
    public List<List<Integer>> levelOrder(TreeNode root) {
        
        List<List<Integer>> list=new  ArrayList<>();
        if(root==null) return list;
        Queue<TreeNode> q=new LinkedList<>();
        q.add(root);
        
        while(!q.isEmpty()){
            ArrayList<Integer> sublist=new  ArrayList<Integer>();
            int qelements=q.size();
            
            for(int i=0;i<qelements;i++){
                TreeNode node=q.poll();
                sublist.add(node.val);
                
                if(node.left != null)
                    q.add(node.left);
                if(node.right != null)
                    q.add(node.right);
                    
            }
            list.add(sublist);
        }
        return list;
    }
}
