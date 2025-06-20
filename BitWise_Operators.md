# BIIWISE OPERATORS
## QUESTIONS AND ANSWERS
1.program to set ith bit of a number.
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
2.Program to clear the ith bit of a number.
```
#include<stdio.h>
unsigned int clearbit(unsigned int num,int i)
{
    return num&=~(i<<i);
}
int main()
{
    unsigned int num=10;
    int i=1;
    unsigned int result =clearbit(num,i);
    printf(" original: %u",num);
    printf("After clearing bit%d: %u",i,result);
    return 0;
}
```
3.Program to toggle ith bit of an number.
```
#include<stdio.h>
void toggle_bit(int *num,int i)
{
    *num^=(1<<i);
}
int main()
{
    int num=29;
    int i=3;
    printf("before toggle bit %d: %d\n",i,num);
    toggle_bit(&num,i);
    printf("After toggling bit%d: %d",i,num);
    return 0;
}
```
4.count zeroes and ones in an number.
```
#include<stdio.h>
int setbit(int num,int size)
{
    int one=0,zero=0;
    for(int i=0;i<size;i++)
    {
        if(num&(1<<i))
        {
            one++;
        }
        else
        {
            zero++;
        }
    }
    printf("one: %d\n",one);
    printf("zero: %d\n",zero);
}
int main()
{
    int num;
    scanf("%d",&num);
    int size=sizeof(int)*8;
    setbit(num,size);
    return 0;
}
```
5.Program to reverse bit positions in an particular number.
```
#include<stdio.h>
unsigned int reversebits(unsigned int num)
{
    unsigned int reversed =0;
    int size=sizeof(num)*8;
for(int i=0;i<size;i++)
{
    if(num&(i<<i))
    {
        reversed |=(1<<(size-1-i));
    }
}
return reversed;
}
int main()
{
    unsigned int num=45;
    unsigned int reversed=reversebits(num);
    printf("Original: %u,reversed: %u\n",num,reversed);
    return 0;
}
```
6.Write a c program to set m to n bits number.
```
#include<stdio.h>
unsigned int setbits(unsigned int num,int m,int n)
{
    unsigned int mask=((1<<(n-m+1))-1)<<m;
    return num|mask;
}
int main()
{
    unsigned int num=10;
    int m=1,n=3;
    unsigned int result=setbits(num,m,n);
    printf("Original: %u(Binary: %X)\n",num,num);
    printf("After setting bits %d to %d: %u(Binary: %X)\n",m,n,result,result);
    return 0;
}
```
7.write a c program to reset m to n bits number.
```
#include<stdio.h>
unsigned int resetbits(unsigned int num,int m,int n)
{
    unsigned int mask=((1<<(n-m+1))-1)<<m;
    return num&~mask;
}
int main()
{
    unsigned int num=10;
    int m=1,n=3;
    unsigned int result =resetbits(num,m,n);
    printf("Original Number: %u(Binary: %X)\n",num,num);
    printf("After resetting bits %d to %d: %u(Binary: %X)\n",m,n,result,result);
    return 0;
}
```
8.program to toggle m to n bits.
```
#include<stdio.h>
unsigned int togglebits(unsigned int num,int m,int n)
{
    unsigned int mask=((1<<(n-m+1))-1)<<m;
    return num^mask;
}
int main()
{
    unsigned int num=10;
    int m=1,n=3;
    unsigned int result=togglebits(num,m,n);
    printf("Original Number: %u(Binary: %X)\n",num,num);
    printf("After toggling bits %d to %d: %u(Binary: %X)\n",m,n,result,result);
    return 0;
}
```
9.Program to convert decimal to binary using mathematical operations.
```
#include<stdio.h>
void decimaltobinary(int num)
{
    int binary[32]; // Array to store binary digits
    int i=0;
    while(num>0)
    {
        binary[i]=num%2; // get remainder(binary digit)
        num/=2; //Divide number by 2
        i++;
    }
    printf("Binary Equivalent: ");
    for(int j=i-1;j>=0;j--)
    {
        printf("%d",binary[j]);
    }
    printf("\n");
}
int main()
{
    int num;
    printf("Enter a Decimal number: ");
    scanf("%d",&num);
    decimaltobinary(num);
    return 0;
}
```
10 Program to convert Decimal to binary in bitwiseoperaters.
```
#include<stdio.h>
void decimaltobinary(int num)
{
    for(int i=31;i>=0;i--)
    {
        printf("|%d",(num >> i) &1);
    }
    printf("\n");
}
int main()
{
    int num;
    printf("Enter a decimal number: ");
    scanf("%d",&num);
    decimaltobinary(num);
    return 0;
}
```
