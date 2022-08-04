它的工作原理是通过构建有序序列，对于未排序数据，在已排序序列中从后向前扫描，找到相应位置并插入。

O(N^2)


```C++
#include<stdio.h>
int main()
{
	int a[10]={1,4,3,5,9,0,8,2,7,6};
	int i=0,j=0;
	int tmp=0;
	
	for(i=1;i<10;i++)
	{
		for(j=i-1;j>=0;j--){
			if(a[j+1]<a[j]){
				tmp=a[j+1];
				a[j+1]=a[j];
				a[j]=tmp;
			}
			else{
				break;
			}
		}
	}
	
	for(i=0;i<10;i++){
		printf("%d ",a[i]);
	}
	return 0;
}
 
```