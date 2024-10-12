# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution:
    def diameterOfBinaryTree(self, root: Optional[TreeNode]) -> int:
        def diameter(root,ans):
            if not root:
                return 0
            
            lh = diameter(root.left,ans)
            rh = diameter(root.right,ans)
            
            ans[0] = max(ans[0],lh+rh)

            return max(lh,rh)+1

        # int var is immutable and list is mutable 
        ans=[0]
        diameter(root,ans)
        return ans[0]