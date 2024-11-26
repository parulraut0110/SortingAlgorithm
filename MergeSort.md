#include <stdio.h>
#define size 8

int output[size];

void swap(int *x, int *y) {
  int temp = *x;
  *x = *y;
  *y = temp;
}


void merge(int a[], int b[], int sizeA, int sizeB) {
  int i, j, k;
  int c[sizeA + sizeB]; 
  
  
  for (i = 0, j = 0, k = 0; i < sizeA && j < sizeB;) {
    if (a[i] <= b[j])
      c[k++] = a[i++];
    else
      c[k++] = b[j++];
  }
  
  
  while (i < sizeA)
    c[k++] = a[i++];
  
  
  while (j < sizeB)
    c[k++] = b[j++];
  
  
  for (i = 0; i < sizeA + sizeB; i++)
    a[i] = c[i];
}


void mergeSort(int a[], int low, int high) {
  if (low < high) {
    int mid = (low + high) / 2;

    
    mergeSort(a, low, mid);
    mergeSort(a, mid + 1, high);

    
    merge(&a[low], &a[mid + 1], mid - low + 1, high - mid);
  }
}

int main() {
  int in[] = {11, 7, 19, 3, 29, 1, 8, 13};
  int n = 8;

  
  mergeSort(in, 0, n - 1);

  
  printf("Sorted array: ");
  for (int i = 0; i < n; i++) 
    printf("%d ", in[i]);
  printf("\n");

  return 0;
}
