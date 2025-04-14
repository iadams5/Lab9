# Lab9
#Problem 1:
[Link Text](https://leetcode.com/problems/same-tree/description/?envType=study-plan-v2)

#Goal:
For this problem, I had to write a function that would check if two binary trees were the same, given their roots.

#Code Explanation:
I included two bases cases. The first checked if both trees were empty, and the second checked if only one was. If both were empty, the trees were technically identical. If only one was, the two trees were obviously different.
I then recursively checked the left subtree of the first binary tree, as well as the left subtree of the second, to see if they were the same. I did the same with the right subtree of both binary trees. If both subtrees were identical, then the two trees were identical.

Code: 
class Solution {
    
public:
    bool isSameTree(TreeNode* p, TreeNode* q) {
        if (p == nullptr && q == nullptr) {
            return true;
        }
        if ((p == nullptr && q != nullptr) || (p != nullptr && q == nullptr)) {
            return false;
        }
        if (p->val != q-> val) {
            return false;
        }
        bool leftSame = isSameTree(p->left,q->left);
        bool rightSame = isSameTree(p->right,q->right);
        return leftSame && rightSame;
    
    }
};
#Test Cases:
LeetCode tested my code against a few test cases. When presented with different trees, or a tree with a null value, my code retrurned false. When presented with two identical trees, my code returned true. 

#Problem2
[Link Text](https://leetcode.com/problems/maximum-depth-of-binary-tree/?envType=study-plan-v2&envId=top-interview-150)

#Goal:
For this problem, I had to find the max depth of a binary search tree, from the root to the farthest leaf node

#Code Explanation:
First, I included a base case that returned a depth of 0 if the tree was empty. Then, I recursively calculated both the right and left subtrees. I compared the two, and had my code return the largest value.
#Code:
'''cpp
class Solution {
public:
    int maxDepth(TreeNode* root) {
        if (root == nullptr) {
            return 0;
        }
        int leftDepth = maxDepth(root->left);
        int rightDepth = maxDepth(root->right);
        if (leftDepth >= rightDepth) {
            return (leftDepth+1);
        }
        else {
            return (rightDepth + 1);
        }
    }
};

#Test Cases:
Leetcode provided some test cases. In both, even if there were some null values in the tree, my code provided the correct max depth. 

