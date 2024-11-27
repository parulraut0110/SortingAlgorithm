## Code:

```c
/* Quick Sort  
 * pivot at first index 
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
  int pivot = a[low];
  printf("\n pivot:%d, low:%d, high:%d\n", pivot,low,high);
  int right = high + 1;
  for(int i=high; i>low; i--) 
     if(a[i] > pivot) {
       swap(&a[--right], &a[i]);
       printf("\n");
       for(int j=0; j<7; j++)
         printf(" %d ", a[j]);
     }
  swap(&a[--right], &a[low]);
  return right;
}

int main() {
  int in[] = {11, 23, 43, 19, 6, 12, 17};
  qs(in, 0, 6);
  printf("\n");
  for(int i=0; i<7; i++)
     printf(" %d ", in[i]);
    
  return 0;
}
```


### Output

![image](https://github.com/user-attachments/assets/57f5ce96-be03-44f1-b998-10e63b1a30c4)
