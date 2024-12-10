#include<stdio.h>
struct student {
	char name [50];
	int marks;
};
int main()
{
int n,i;
float total=0,average;
printf("enter the number of students:");
scanf("%d",&n);
struct student students[n];
for(i=0;i<n;i++){
	printf("\n enter detailsfor student %d:\n",i++);
	printf("name:");
	scanf("%s",students[i].name);
	printf("marks:");
	scanf("%d",&students[i].marks);
	total+=students[i].marks;
}
average=total/n;
printf("\n student details:\n");
for(i=0;i<n;i++){
	printf("%s:%d marks\n",students[i].name,students[i].marks);
}
printf("\n total marks:%2f/n",total);
printf("average marks:%2f/n",average);
return 0;
}
