#include <stdio.h>
#include <stdlib.h>
Struct node{
Int data;
Struct node *left,*right;
};
Struct node* create(int data){
Struct node* newnode =
(struct
node*)malloc(sizeof(struct
node));
Newnode->data=data;
Newnode->left=newnode-
>right=NULL;
Return newnode;
}
Struct node* insert(struct
node* root,int data){
If(root==NULL)
Return create(data);
If(data < root->data)
Root->left = insert(root-
>left,data);
Else
Root->right = insert(root-
>right,data);
Return root;
}
Int search(struct node* root,int
key){
If(root==NULL) return 0;
If(root->data==key) return
1;
If(key < root->data)
Return search(root-
>left,key);
Else
Return search(root-
>right,key);
}
Void inorder(struct node*
root){
If(root!=NULL){
Inorder(root->left);
Printf(“%d “,root->data);
Inorder(root->right);
}
}
Int main(){
Struct node* root=NULL;
Root=insert(root,20);
Root=insert(root,10);
Root=insert(root,30);
Printf(“Student Roll
Numbers (BST): “);
Inorder(root);
If(search(root,10))
Printf(“\nRoll No 10
Found”);
Else
Printf(“\nNot Found”);
Return 0;
}
OUTPUT
Student Roll Numbers (BST):
10 20 30
Roll No 10 Found
