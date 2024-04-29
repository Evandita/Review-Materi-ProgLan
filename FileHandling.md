# File Handling

## Read ONE string from a file

```c
#include <stdio.h>

int main() {
    FILE *ptr;
    char buffer[1000];

    ptr = fopen("file.txt", "r");

    if (ptr == NULL) {
        printf("There is an error\n");
        return 1;
    }

    fscanf(ptr, "%[^\n]s", buffer);
    printf("%s\n", buffer);

    fclose(ptr);

}
```

## Read ALL string from a file

```c
#include <stdio.h>

int main() {
    FILE *ptr;
    char buffer[1000];

    ptr = fopen("file.txt", "r");

    if (ptr == NULL) {
        printf("There is an error\n");
        return 1;
    }

    while (fscanf(ptr, "%s", buffer) != EOF) {
        printf("%s\n", buffer);
    }

    fclose(ptr);

}
```

## Write to a file

```c
#include <stdio.h>

int main(void){
    FILE *ptr;

    ptr = fopen("file.txt", "w");

    if (ptr == NULL) {
        printf("There is an error\n");
        return 1;
    }

    fprintf(ptr, "I am writing\n");

    fclose(ptr);

    return 0;
}
```

## Append to a file

```c
#include <stdio.h>

int main(void){
    FILE *ptr;     

    ptr = fopen("file.txt", "a"); 

    if (ptr == NULL) {
        printf("There is an error\n");
        return 1;       
    }

    fprintf(ptr, "I am appending\n");

    fclose(ptr);    

    return 0;
}
```