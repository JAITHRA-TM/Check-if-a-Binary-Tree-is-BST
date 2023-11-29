# Check-if-a-Binary-Tree-is-BST
int maximum(BinaryTreeNode<int>* root){
	if(root == NULL){
		return INT_MIN;
	}
	return max(root->data, max(maximum(root->left), maximum(root->right)));
}
int minimum(BinaryTreeNode<int>* root){
	if(root == NULL){
		return INT_MAX;
	}
	return min(root->data, min(minimum(root->left), minimum(root->right)));
}

bool isBST(BinaryTreeNode<int> *root) {
	// Write your code here
	int leftmax = maximum(root->left);
	int rightmin = minimum(root->right);
	return ((root->data > leftmax) && (root->data <= rightmin) && isBST(root->left) && isBST(root->right));
}
