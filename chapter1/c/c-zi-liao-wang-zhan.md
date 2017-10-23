## 关于 C 语言的资料的网站

[C library function - fgets()](https://www.tutorialspoint.com/c_standard_library/c_function_fgets.htm)

Read file in C:
``` c
include <stdio.h>

int main () {
   FILE *fp;
   char str[60];

   /* opening file for reading */
   fp = fopen("file.txt" , "r");
   if(fp == NULL) {
      perror("Error opening file");
      return(-1);
   }
   if( fgets (str, 60, fp)!=NULL ) {
      /* writing content to stdout */
      puts(str);
   }
   fclose(fp);
   
   return(0);
}
```
