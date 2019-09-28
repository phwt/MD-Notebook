## `swap`
```c 
 void swap(double *arg1, double *arg2){
    double temp = *arg1;
    *arg1 = *arg2;
    *arg2 = temp;
}
```
    
## `sort`
```c    
for(int i=0; i<19; i++){
    for(int j=i+1; j<20; j++){
        if(strcmp(name_list[i], name_list[j]) > 0){
            strcpy(sname, name_list[i]);
            strcpy(name_list[i], name_list[j]);
            strcpy(name_list[j], sname);
        }
    }
}
```
    
## `find` (Using `strchar()`)

```c
#include <stdio.h>
#include <string.h>

int main ()
{
  char str[] = "This is a sample string";
  char * pch;
  printf ("Looking for the 's' character in \"%s\"...\n",str);
  pch=strchr(str,'s');
  while (pch!=NULL)
  {
    printf ("found at %d\n",pch-str+1);
    pch=strchr(pch+1,'s');
  }
  return 0;
}
```
