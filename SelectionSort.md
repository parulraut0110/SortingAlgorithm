```c
#include <stdio.h>

int main()
{
    int a[] = {6,5,1,10,7};
    int n = 5, minpos, minval, temp;
    for(int i = 0; i < n-1; i++) {
      minpos = i;
      minval = a[minpos];
      for(int j = i + 1; j < n; j++)
        if(a[j] < minval) {
          minpos = j;
          minval = a[j];
        }
        temp = a[i];
        a[i] = minval;
        a[minpos] = temp;
    }
    printf("\n");
    for(int i =0; i < n; i++)
      printf(" %d ", a[i]);
    return 0;
}
```
![image](https://github.com/user-attachments/assets/4cb98e11-fbd7-4a82-9c3a-88c7d847166e)
