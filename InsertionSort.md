```c
#include <stdio.h>
int main() {   
  int a[] = {13, 7, 1, 19, 21,8, 12};
  int n = 7, key;
  int k;
  
  for(int i = 0; i < n-1; i++) {
      key = a[i+1];
      for(k = i; k >= 0; k--) {
        if(a[k] > key) 
          a[k+1] = a[k];
        else {
          a[k+1] = key;
          break; 
        }
      }
      if(k<0) 
        a[0] = key;
      
      printf("\n i : %d ", i);
      for(int r = 0; r < n; r++) 
        printf(" %d ", a[r]);
    
  }
  for(int i = 0; i < n; i++) 
    printf(" %d ", a[i]);
}

```
![image](https://github.com/user-attachments/assets/b9099ba5-4595-4562-88ef-25500b464eab)
