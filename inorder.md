## leetcode 94. Binary Tree Inorder Traversal
```cpp
/**
 * Definition for a binary tree node.
 * struct TreeNode {
 *     int val;
 *     TreeNode *left;
 *     TreeNode *right;
 *     TreeNode() : val(0), left(nullptr), right(nullptr) {}
 *     TreeNode(int x) : val(x), left(nullptr), right(nullptr) {}
 *     TreeNode(int x, TreeNode *left, TreeNode *right) : val(x), left(left), right(right) {}
 * };
 */
class Solution {
public:
    vector<int> inorderTraversal(TreeNode* root) {
        //inorder using stack
        vector <int> ans;
        stack <TreeNode *> s;
        TreeNode * curr = root;
        // 往左走到底 再往右看一下有沒有Node
        // curr 可能起始為NULL
        while(curr|| !s.empty()){
            //上一個curr -> right 如果是NULL 不會跑進去
            while(curr){
                s.push(curr);
                curr  = curr -> left;
            }
            curr = s.top();
            s.pop();
            // 已到左最底 再開始往右看
            ans.push_back(curr->val);
            // 往右一次就要檢查到最左下一次
            curr = curr -> right;
        }
        return ans;
    }
};
```
