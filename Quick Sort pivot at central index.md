```c
/* Quick Sort  
 * pivot at central index 
 */


#include <stdio.h>
int partition(int [], int , int );
void swap(int *x, int *y) {
  int temp = *x;
  *x = *y;
  *y = temp;
}

void qs(int a[], int low, int high) {
  int split_at;
  if(low < high) {
    split_at = partition(a, low, high);
    qs(a, low, split_at-1);
    qs(a, split_at+1, high);
  }
}

int partition(int a[], int low, int high) {
  int pivotPos = (high + low) / 2;
  int pivot = a[(high + low)/2];
  printf("\n pivot:%d, low:%d, high:%d\n", pivot,low,high);
  int left = low-1;
  swap(&a[pivotPos], &a[high]);
  
  for(int i=low; i<high; i++) 
     if(a[i] < pivot) {
       swap(&a[++left], &a[i]);
       printf("\n");
       for(int j=0; j<7; j++)
         printf(" %d ", a[j]);
     }
  swap(&a[++left], &a[high]);
  return left;
}

int main() {
  //int in[] = {11, 23, 43, 19, 6, 12, 17};
  //int in[] = {1, 2, 3, 4, 5, 6, 7};
  int in[] = {7, 6, 5, 4, 3, 2, 1};
  qs(in, 0, 6);
  printf("\n Sorted Array : \n");
  for(int i=0; i<7; i++)
     printf(" %d ", in[i]);
    
  return 0;
}

```
