# Unique-Binary-Search-Trees-II
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution:
    def generateTrees(self, n: int) -> List[Optional[TreeNode]]:
        def add(a,b):
            if a>b:
                return [None]
            res=[]
            for i in range(a,b+1):
                left=add(a,i-1)
                right=add(i+1,b)
                for l in left:
                    for r in right:
                        temp=TreeNode(i)
                        temp.left=l
                        temp.right=r
                        res.append(temp)
            return res
        return add(1,n)

              
