  int ans=0, mh=0;
    void solve(Node* root, int h, int s){
        if(!root){
            return;
        }
        if(!root->left && !root->right){
            s+=root->data;
            if(h>mh){
                ans=s;
                mh=h;
            }
            else if(h==mh){
                ans=max(ans, s);
            }
            return ;
        }
        
        s+=root->data;
        solve(root->left, h+1, s);
        solve(root->right, h+1, s);
        
        return;
    }
    
    int sumOfLongRootToLeafPath(Node *root)
    {
        //code here
        solve(root, 0, 0);
        return ans;
    }
