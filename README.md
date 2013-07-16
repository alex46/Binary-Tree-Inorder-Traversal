Binary-Tree-Inorder-Traversal
=============================

/**
 * Definition for binary tree
 * public class TreeNode {
 *     int val;
 *     TreeNode left;
 *     TreeNode right;
 *     TreeNode(int x) { val = x; }
 * }
 */
public class Solution {
    public ArrayList<Integer> inorderTraversal(TreeNode root) {
        // Start typing your Java solution below
        // DO NOT write main() function
        
        ArrayList<Integer> list = new ArrayList<Integer>();
        
        return helper(root,list);
        
    }
    
    public static ArrayList<Integer> helper(TreeNode root, ArrayList<Integer> list){
        if(root==null) return list;
        
       // if(root.left!=null){
        helper(root.left,list);
       // }
        list.add(root.val);
        
       // if(root.right!=null){
        helper(root.right,list);
       // }
        
        return list;
    }
}


//Iteratively"

/**
 * Definition for binary tree
 * public class TreeNode {
 *     int val;
 *     TreeNode left;
 *     TreeNode right;
 *     TreeNode(int x) { val = x; }
 * }
 */
 
 public class Solution{
 public ArrayList<Integer> inorderTraversal(TreeNode root) {
    ArrayList<Integer> result=new ArrayList<Integer>();
    Stack<TreeNode> st=new Stack<TreeNode>();
    
    
    if(root!=null)
     {
         st.push(root);
        while(root.left!=null)
        {
             root=root.left;
            st.push(root);
         }
     }
     while(!st.empty())
    {
        TreeNode top=st.pop();
        result.add(top.val);
        if(top.right!=null)
        {
            st.push(top.right);
            top=top.right;
            while(top.left!=null)
            {
                top=top.left;
                st.push(top);
            }
        }
    }
  
   return result;
 }
 }
