```c
/* Quick Sort  
 * pivot at last index 
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
  int pivot = a[high];
  printf("\n pivot:%d, low:%d, high:%d\n", pivot,low,high);
  int left = low-1;
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
  int in[] = {11, 23, 43, 19, 6, 12, 17};
  qs(in, 0, 6);
  for(int i=0; i<7; i++)
     printf(" %d ", in[i]);
    
  return 0;
}
```

![image](https://github.com/user-attachments/assets/f6dff9d0-68fb-44da-ad68-a57a2bf6cd0f)
