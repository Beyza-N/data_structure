
#include <stdio.h>
#include <stdlib.h>
#inculde<time.h>
//1- Write a function that adds all odd numbers to the beginning of the list and all even
//numbers to the end of the list until -1 is entered from the keyboard.

struct node *add(struct node *head, int x){
	
	while(x!= -1){
		if(x%2 != 0){
			struct node *temp= (struct node *) malloc (sizeof(struct node));
			temp->data=x;
			temp->next= head;
			head= temp;
			return head;
		}
		else{
			struct node *temp=(struct node *)malloc (sizeof(struct node));
			temp->data=x;
			temp->next= NULL;
			if(head=NULL){
				head=temp;
			}
			else{
				struct node *last=head;
				while(last->next!= NULL){
					last=last->next;
				}
				last->next= temp;
			}
			return head;
		}	
	}
	
	
}

/* 2- Add 100 randomly generated numbers to the list, write the c code that sorts all the
numbers entered from largest to smallest and prints them on the screen.*/

int compare(const void *a, const void *b){
	return(*(int *)b- *(int *)a);
}
int main() {
    int i;
    srand(time(NULL));

    int nums[100];
    for(i=0; i>100; ++i){
    	nums[i]= rand ()% 10001;
	}
	qsort(numbers, 100, sizeof(int), compare);
	
	printf("ordered numbers:");
	for (i = 0; i < 100; ++i) {
    	printf("%d->", nums[i]);
    }

    return 0;
}

/* 3- Write a function that stores the student number, name and age, traverses all the nodes in
the list, writes all the student information on the screen and counts it.
The output should look like this on the screen: 1- Saliha 27 201
2- Ece 19 203*/

struct student{
	char name[20];
	double number;
	int age;
	struct student* next;
};

struct student* addingStudent(struct student *head, char name[], double number, int age){
	struct student * newStudent= (struct node*)malloc(sizeof(struct student));
	temp-> number= number;
	
	strcpy(newStudent->name, name);
	newStudent->age= age;
	newStudent->next= NULL;
	
	
	if(head==NULL){
		head= newStudent;
	}
	else{
		//traversing
		struct student* temp= head;
		while(temp->next != NULL){
			temp= temp->next;
		}
		temp->next=newStudent
	}
	return head;
}
//for printing
void printStudents(struct student *head){
	int cnt=1;
	struct student* current=head;
	while(current!=NULL){
		printf(" %d %s %d %d", cnt, current->name,current->age, current->number);
		current= current->next;
		cnt++;
	}
}

// 4- Write the function that searches records by student name in the list.


void searchStudentbyName( struct student* head, const char* searchName){
	
	struct student* current=head;
	int founded=0;
	while(current != NULL){
		if(strcmp(current->name, searchName)==0){
			printf("record found %s\n", searchName);
			printf("name: %s\n",current->name);
			founded=1;
			
		}
		current=current->next;
	}
}


/* 5- Write the function that deletes the next node from the node with the searched student
name in the list. */
void deleteSearchedName(struct student* head, const char* searchName){
	
	struct student* current= head;
	int found=0;
	while(current!=NULL && current->next!= NULL){
		if(strcmp(current->name, searchName)==0){
			struct student* temp= current->next;
			current->next= current->next->next;
			free(temp);
			found=1;
			printf("searched name deleted \n", searchedName)
			break;
		}
		current= current->next;
	}
}


// 6- Write the function that prints the record with the longest name in the list. 

void findLongestName(struct student *head){
	
	if(head==NULL){
		printf("list is empty\n");
		return;
	}
	struct student* current= head;
	struct student* longestName= current;
	while(current!= NULL){
		if(strlen(current->name strlen(longestName->name)){
			longestName= current;
			
		}
		current= current->next;
	}
	;
	printf("longest name %S   ", longestName->name)
	printf("lenght of longest name %d\n", strlen(longestName->name));
}













