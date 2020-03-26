#include<stdio.h>
#include<ctype.h>
#include<conio.h>
#include<string.h>
#include<stdlib.h>

struct node
{
char data[10];
struct node *next;
}*ptr,*start=NULL;

static int count=0;

void insert(char brand[])
{
	struct node *newnode;
	newnode=(struct node*)malloc(sizeof(struct node));

	strcpy(newnode->data,brand);

	if(start==NULL)
	{
		newnode->next=start;
		start=newnode;
	}
	else
	{
		ptr=start;

		while(ptr->next!=NULL)
			ptr=ptr->next;
		newnode->next=ptr->next;
		ptr->next=newnode;
	}
	printf("Brand Inserted");
}


void display()
{
	count=0;
	ptr=start;
	clrscr();
	printf("Brands in the given List are:\n\n");
	while(ptr->next!=NULL)
	{
		printf("%s",ptr->data);
		ptr=ptr->next;
		printf("\n");
		count++;
	}
	printf("%s",ptr->data);

	printf("\n\nThere are currently %d brands in the given list",count+1);

}

void initialise()
{
	insert("Toblerone");
	insert("Cadbury");
	insert("Mars");
	insert("Godiva");
	insert("Guylian");
	insert("Milky Bar");
	insert("Lindt");
	insert("Kit Kat");
	insert("Munch");
	display();
	printf("\n\nPress any key to continue");
	getch();

}


void delete()
{
	char del[10];
	int flag=0;
	struct node *temp;
	display();
	if(start==NULL)
	printf("List is Empty");
	else
	{
	printf("\nEnter Brand to be Deleted:");
	fflush(stdin);
	gets(del);

	if(islower(del[0]))
	{
	del[0]=del[0]-32;
	}


	if(strcmp(start->data,del)==0)
	{
		temp=start;
		start=temp->next;
		free(temp);
		flag=1;
	}
	else
	{
		ptr=start;
		while(ptr->next!=NULL && strcmp(ptr->next->data,del)!=0)
			ptr=ptr->next;

		if(ptr->next!=NULL)
		{
			temp=ptr->next;
			ptr->next=temp->next;
			free(temp);
			flag=1;
		}

		if(flag==1)
		{
			printf("Brand Deleted");
		}
		else
		{
			printf("Brand not found");
		}
	}
	}
}


void main()
{
	int ch,x;
	char brand[10];
	clrscr();

	initialise();

	clrscr();

	while(1)
	{
	clrscr();
	printf("\nMENU");
	printf("\n1.Insert New Brand\n2.Delete exitsing brand\n3.Display Brands\n4.Exit List");
	printf("\nEnter Choice:");
	scanf("%d",&ch);

	switch(ch)
	{
		case 1:
		do
		{
		display();
		printf("\nEnter brand name:");
		fflush(stdin);
		gets(brand);
		if(islower(brand[0]))
			brand[0]=brand[0]-32;
		insert(brand);
		printf("\n\nDo you want to insert more brands?\n1.Yes\n2.No\nEnter Choice:");
		scanf("%d",&x);
		clrscr();
		}while(x==1);
		break;

		case 2:
		do
		{
		delete();
		printf("\n\nDo you want to delete more brands?\n1.Yes\n2.No\nEnter Choice:");
		scanf("%d",&x);
		}while(x==1);
		clrscr();
		break;

		case 3:
		display();
		printf("\n\nPress any key to continue");
		getch();
		break;

		case 4:
		exit(0);

		default:
		printf("Invalid input");
		printf("\nPress any key to try again");
		getch();
	 }
	 }
	 getch();
}
