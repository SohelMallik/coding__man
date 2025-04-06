#include<stdio.h>
#include<stdlib.h>
struct node{
    int data;
    struct node *add;
};
struct node* newnode, *head=NULL, *temp;

void create();
void display();

int  main(){
    create();
    display();
    return 0;
}

void create(){
    char ch;
    do{
        newnode= (struct node*)malloc(sizeof(struct node));
        printf("Enter the Element:");
        scanf("%d",&newnode->data);
        newnode->add=NULL;
        if(head==NULL){
            head=temp=newnode;
        }else{
            temp->add=newnode;
            temp=newnode;
        }
     printf("Add more node? (y/n): ");
        scanf(" %c", &ch);
    }while(ch=='y'|| ch=='Y');
}

void display(){
    if (head==NULL){
        printf("Linked List not found");
    }else{
        temp=head;
        printf("Linked LIst:");
        // Traverse the linked list and print each node's data

        while(temp!=NULL){
            printf("%d->", temp->data);
            temp=temp->add;
        }
        printf("NULL");
    }
    
}
