#include<stdio.h>
int main()
{
   int a[20],i,t=0,se,n;
   printf("enter the size: ");
   scanf("%d",&n);
   printf("enter the elements:");
   for(i=0;i<n;i++)
   {
     scanf("%d",&a[i]);
   }
   printf("enter search element:");
   scanf("%d",&se);
   for(i=0;i<n;i++)
   {
     if(a[i]==se)
     {
     printf("the element is found at location %d",i+1);
     t=1;
     break;
     }
   }
   if(t==0)
   printf("the element is not found at any location ");
}
