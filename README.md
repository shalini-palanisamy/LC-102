# LC-102
Binary Tree Level Order Traversal II
```ruby
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
    vector<vector<int>> levelOrderBottom(TreeNode* root) {
        typedef TreeNode Node;
        vector<vector<int>> v;
        if(!root) return v;
        queue <Node*> q;
        q.push(root);
        while(!q.empty())
        {
            vector<int>v1;
            int count=q.size();
            while(count)
            {
                Node* curr = q.front();
                q.pop();
                v1.push_back(curr->val);
                if(curr->left)
                   q.push(curr->left);
                if(curr->right)
                   q.push(curr->right);
                --count;
            }
            v.push_back(v1);
        }
        reverse(v.begin(),v.end());
        return v;
    }
};
```
