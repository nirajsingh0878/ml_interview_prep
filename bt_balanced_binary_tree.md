# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution:
    def isBalanced(self, root: Optional[TreeNode]) -> bool:
        
        def height(root,ans):
            if not root:
                return 0

            lh = height(root.left,ans)
            rh = height(root.right,ans)

            if abs(lh-rh)>1:
                ans[0] = False
            
            return max(lh,rh)+1

        ans = [True]    
        height(root,ans)

        return ans[0]
        