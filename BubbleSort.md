## BubbleSort # Using One For Loop

```c
#include <stdio.h>

int main() {
    int a[] = {22, 33, 55, 44, 11};
    int n = sizeof(a) / sizeof(a[0]);

    
    for (int i = 0; i < n - 1; i++) {
        if (a[i] > a[i + 1]) {
            
            int temp = a[i];
            a[i] = a[i + 1];
            a[i + 1] = temp;
        }

        
        printf("Array after iteration %d:\n", i + 1);
        for (int j = 0; j < n; j++) {
            printf(" %d", a[j]);
        }
        printf("\n");

        
        if (i == n - 2) {
            n = n - 1; 
            i = -1;    
        }
    }
    
    printf("Sorted Array\n");
    for (int j = 0; j < sizeof(a) / sizeof(a[0]); j++) {
            printf(" %d", a[j]);
    }

    return 0;
}
```
