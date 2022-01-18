# Linked-List-Implementation-using-Stack


#include <stdio.h>  
#include <stdlib.h>  

void push();  
void pop();  
void display();  
struct node   
{  

int val;  
struct node *next;  
};  
struct node *top ,*top1, *temp;  

void main ()  
{  

    int choice=0;     
    printf("\n*********Stack operations using linked list*********\n");  
    printf("\n----------------------------------------------\n");  
    while(choice != 4)  
    {  
    
        printf("\n\nChose one from the below options...\n");  
        
        printf("\n1.Push\n2.Pop\n3.Show\n4.Exit");  
        
        printf("\n Enter your choice \n");        
        scanf("%d",&choice);  
        switch(choice)  
        {  
            case 1:  
            {   
                push();  
                break;  
            }  
            case 2:  
            {  
                pop();  
                break;  
            }  
            case 3:  
            {  
                display();  
                break;  
            }  
            case 4:   
            {  
                printf("Exit");  
                break;   
            }  
            default:  
            {  
                printf("Please Enter valid choice ");  
            }   
    };  
}  
}  

void push(int data)
{

	  printf("Enter the value");  
        scanf("%d",&data);  
        
	if(top==NULL)
	{
		top=(struct node*)malloc(sizeof(struct node));
		top->val=data;
		top->next=NULL;
	
	}
	else
	{
			temp=(struct node*)malloc(sizeof(struct node));
			temp->next=top;
			temp->val=data;
			top=temp;
	}
}
void display()
{

	top1=top;
	if(top1==NULL)
	{
		printf("stack is empty");
		return;
		
	}
	
	while(top1!=NULL)
	{
  
		printf("%d",top1->val);
		top1=top1->next;
	}
	
}

void pop()
{
	top1=top;
	if(top1==NULL)
	{
		printf("\n Error");
		return;
		
	}
	else
	{
      top1=	top1->next;	
      printf("\npoped value = %d",top->val);
      free(top);
      top=top1;
	}
}
