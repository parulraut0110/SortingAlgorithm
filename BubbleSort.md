# BubbleSort Using One For Loop

Details: - [MEDIUM BLOG](https://medium.com/@parulraut0110/bubble-sort-implementation-using-a-single-for-loop-in-c-9e60eb2574f9)

Run On :- [One Compiler](https://onecompiler.com/c/42zdf2nss)

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


![image](https://github.com/user-attachments/assets/f0af9aba-115a-4666-94d6-eec0e444ca2e)

