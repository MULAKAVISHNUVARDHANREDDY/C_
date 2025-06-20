# BIIWISE OPERATORS
## QUESTIONS AND ANSWERS
- program to set ith bit of a number
```
#include<stdio.h>
unsigned int setbit(unsigned int num,int i)
{
    return num|=(1<<i);
}
int main()
{
    unsigned int num =10;
    int i=2;
    unsigned int result =setbit(num,i);
    printf("Original: %u (Binary: %X)\n",num,num);
    printf("After setting bit%d: %u (Binary: %X)\n",i,result,result);
    return 0;
}
```
