# ITERATIVE-METHODS
Here is the program to count number of nodes using iterative methods
#include<stdio.h>
#include<stdlib.h>
struct Node{
	int data;
	struct Node *next;
};
void create(struct Node **head_ref,int ele)
{
	struct Node *new_node=(struct Node*)malloc(sizeof(struct Node*));
	new_node->data=ele;
	new_node->next=(*head_ref);
	*head_ref=new_node;	
}
void printList(struct Node * ptr)
{
	while(ptr!=NULL){
		printf("%d ",ptr->data);
		ptr=ptr->next;
	}
}
void count(struct Node *ptr)
{
	int c=0;	
	while(ptr!=NULL)
	{
		c++;
		ptr=ptr->next;
	}
	printf("\n Nodes = %d",c);
}
void main(){
	
	int i,n,ele;
	struct Node *head=NULL;

	printf("\nEnter the number of nodes:\n");
	scanf("%d",&n);
	
	for(i=0;i<n;i++){
		printf("\n Enter the value in  node:\n");
		scanf("%d",&ele);
		create(&head,ele);
	}
	printf("\nThe Input Link List is :\n");
	printList(head);
	printf("\nThe number of node in link list are");
	count(head);
}
