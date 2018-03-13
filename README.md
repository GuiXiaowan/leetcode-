# leetcode-

#### 参考答案
http://www.jiuzhang.com/solution/


### 二叉树最小深度

#### 思路
就左右两边找然后递归。
**开始没有考虑到无根情况，导致一直是段错误**

#### code
class Solution {
public:
    int run(TreeNode *root) {
        if(!root) return 0;
        if (root->left==NULL && root->right==NULL){
            return 1;
        }
        else {
            int a=0;
            int b=0;
            if(root->left!=NULL) a=run(root->left);
            if(root->right!=NULL) b=run(root->right);
            if(a==0) return b+1;
            if(b==0) return a+1;
            return (a<b)?(a+1):(b+1);
        }
    }
};
