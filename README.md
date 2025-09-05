# java.BST
BST problems
no1.built tree

public class BST {
static class Node {
int data;
Node left;
Node right;
Node(int data) {
this.data = data;
}
}
// Corrected insert method for BST
public static Node insert(Node root, int val) {
if (root == null) {
return new Node(val);
}
if (val < root.data) {
root.left = insert(root.left, val);
} else {
root.right = insert(root.right, val);
}
return root;
}
// Inorder traversal: left, root, right
public static void inorder(Node root) {
if (root == null) {
return;
}
inorder(root.left);
System.out.print(root.data + " ");
inorder(root.right);
}
public static void main(String[] args) {
int[] values = {5, 1, 3, 4, 2, 7};
Node root = null;
for (int val : values) {
root = insert(root, val);
inorder(root);
System.out.println();
}
}
}
