<div align="center">

## single linklist novice


</div>

### Description

The code is for creating adding deleting and printing
 
### More Info
 
data structure and pointers


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Balkrishna L Talele](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/balkrishna-l-talele.md)
**Level**          |Intermediate
**User Rating**    |5.0 (10 globes from 2 users)
**Compatibility**  |C
**Category**       |[Data Structures](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/data-structures__3-8.md)
**World**          |[C / C\+\+](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/c-c.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/balkrishna-l-talele-single-linklist-novice__3-4192/archive/master.zip)





### Source Code

```
/*-----------------------------------------------------------------
 Name: Singly linklist
 Description:The code is for creating adding deleting and printing list...
 By: Talele Balkrishna L
 Comliped on turboc 3.0
 Warnings   :  0
 Errors    :  0
 Side Effects: Will make you completely understand
 This code is copyrighted and has limited warranties.
 Please see http://www.Planet-Source-Code.com
 Talele Balkrishna L ,Pune Univ. India
 TOPIC LINKED LIST (In Place Of Array of Structures)
 All Basic Functions in a LINKED LIST
 THE AUTHOR IS NOT RESPONSIBLE FOR ANY DAMAGE OR PLEASUR OR FUSS IN
 YOUR HEAD OR PC. THIS CODE IS FOR EDUCATIONAL PURPOSEONLY AND WILL
 VOID WARRENTIES IF USED ILLEGELY OR ABUSED IN ANY FORM...
*/
#include "stdio.h"
#include "alloc.h"
typedef struct s_list
		   {
		   int val;
		   struct s_list *next;
		   }*SLL;
SLL start,last,temp,extra,one;
void checkme();
//check if list is empty if so automatically create it...
void checkme()
{
temp=start;
    if(temp==NULL)  //start==null then goto create
	{
	printf("\n\t\t\t\t Entering creating mode...");
	create();      //okay...
	}
}
// main start here with no arguments...
main()
   {
   int choice;
   clrscr();
   start=NULL;  // always make start node NULL
  xxx:  printf("\n MENU\n\n 1: create\n 2: append\n 3: print\n 4: add\n 5: delete \n 6: exit :_____\b\b\b\b");
	 scanf("%d",&choice);
	 switch(choice)
	  {
	  case 1: create(); break;
	  case 2: append(); break;
	  case 3: print();  break;
	  case 4: add();   break;
	  case 5: del();   break;
	  case 6: exit();
	  default: printf("\n choice failed...");break;
	  }
	  goto xxx;
    }
 create()
    {
    if(start==NULL)
	 {
	 start=malloc(sizeof(struct s_list)); //alloc the struct s_list
	 printf("\n\t\t\t\t input initilal value:");
	 scanf("%d",&start->val); // get init value
	 start->next=NULL;   // if you fail to mke this null...garbage list is placed
	 }
	 else
	 {
	  printf("\n\t\t\t\t already created...");
	 }
	return;
    }
 append()
   {
	temp=start;  // always give starting of list to temporary
		   // so that we can make changes...
	 if(temp==NULL)
		{
		 printf("\n\t\t\t\t entering creating mode...");
		 create();
		}
	 else
	   {
	   last=malloc(sizeof(struct s_list));
	   if(last==NULL){printf("\n\t\t\t\t not enough memory...");}
	   while(temp->next!=NULL) temp=temp->next;
	   printf("\n\t\t\t\t N enter value : ");
	   scanf("%d",&last->val);
	   last->next=NULL;
	   temp->next=last;
	   }
	return;
   }
 print()
    {
	checkme(); // always check for list? created or not?
	temp=start;
	printf("\n List ::=>");
	while(temp!=NULL)
	  {
	  printf("\t%d",temp->val);
	  temp=temp->next;
	  }
	  return;
    }
add()
   {
	int data;
	checkme();
	temp=start;
	printf("\n\t\t\t\t enter before which :");
	scanf("%d",&data);
	if(data==temp->val)
	  {
	   printf("\t\t\t\tstart val...");
	   last=malloc(sizeof(struct s_list));
	   printf("\n\t\t\t\t get the value...:");
	   scanf("%d",&last->val);
	   last->next=temp;
	   start=last;
	   return;
	  //getch();
	  }
	while(temp!=NULL)            //go upto last node
		  {
		  if(temp->val==data)     //if found
		    {
			printf("\n\t\t\t\t making changes...");
			extra=temp;      //point to that node
			one=temp;       // here i used two ptr "extra and one"
			break;         //break the loop and work on the same
		    }
		    temp=temp->next;
		    printf("\n\t\t\t\t\t not found..");
		   // return;
		  }
		   temp=start;          // set temp to start
		   while(temp->next!=extra)    //now find upto pointed value or node
			  {
			  printf("%d",temp->val);
			  temp=temp->next;
			  }
			  last=malloc(sizeof(struct s_list));
			  printf("\n\t\t\t\t value : ");
			  scanf("%d",&last->val);
//	  printf("temp-> %d *temp-> %d",temp,*temp);
			 temp->next=last;  // join prev+new
			 last->next=one;   // join prev+new+remaning
		  //	 return;
    }
 del()
   {
	int data;//,cnt=0;
	checkme();
	temp=start;
	printf("\n enter number to be deleted :");
	scanf("%d",&data);
	while(temp!=NULL)               //temp->next for next and temp for the given number
	   {
	  //cnt+=1;
	   if(temp->next->val==data)         //if you remove ->next next to next value is deleted
	    {
		printf("\n\t\t\t\t making changes...");
		extra=temp->next;           //take the link to be deleted
		temp->next=temp->next->next;      // join the deleted
		free(extra);              // finally librate the link..
		break;
	    }
	   // printf("%d\n",cnt);
	    temp=temp->next;
	  //printf("\n\t\t\t\t\t not found..cnt=%d",cnt);
	 // return;
	  }
	  return;
   }
```

