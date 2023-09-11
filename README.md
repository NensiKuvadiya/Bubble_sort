# Bubble_sort
#include <stdio.h>
#include <sys/time.h>

int main () {
    int n,flag,a[20],temp;
    printf("Enter number of element:");
    scanf("%d",&n);

    // Start measuring time
    struct timeval begin, end;
    gettimeofday(&begin, NULL);
    for(int i=1;i<=n;i++)
    {
        scanf("%d",&a[i]);
    }
    for(int i=1;i<=n;i++)
    {
        for(int j=1;j<n;j++)
        {
            if(a[j]>a[j+1])
            {
                temp=a[j];
                a[j]=a[j+1];
                a[j+1]=temp;
                flag=1;
            }
        }
        for(int k=1;k<=n;k++)
        {
            printf("%d\t",a[k]);
        }
        printf("\n");
    }
   gettimeofday(&end, NULL);
    long seconds = end.tv_sec - begin.tv_sec;
    long microseconds = end.tv_usec - begin.tv_usec;
    long elapsed = seconds + microseconds*1e-6;
    for(int i=1;i<=n;i++)
    {
        printf("%d\t",a[i]);
    }
   printf("Time measured: %ld seconds.\n", elapsed);
}
    
