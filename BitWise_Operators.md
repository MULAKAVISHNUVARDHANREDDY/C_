# BITWISE OPERATORS
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
11.Program to check if number is power of 2.
```
#include<stdio.h>
int ispower2(int num)
{
    return (num>0)&&((num&(num-1))==0);
}
int main()
{
    int num;
    printf("Enter a number: ");
    scanf("%d",&num);
    if(ispower2(num))                               
    {
        printf("%d is power of 2\n",num);
    }
    else{
        printf("%d is Not power of 2\n",num);
    }
    return 0;
}
```
12.Program to Convert little endian to bigendian.
```
#include<stdio.h>
unsigned int convertendian(unsigned int num)
{
    return ((num & 0x000000FF)<<24)|
            ((num & 0x0000FF00)<<8)|
            ((num & 0x00FF0000)>>8)|
            ((num & 0xFF000000)>>24);
}
int main()
{
    unsigned int num;
    printf("Enter a 32 bit number in hexadicimal format: ");
    scanf("%x",&num);
    unsigned int convertedNUM=convertendian(num);
    printf("Big-endian representation:0x%x\n",convertedNUM);
}
```
13.Program to Convert uppercase Alphabets to lowercase.
```
#include<stdio.h>
void uppertolower(char *str)
{
    for(int i=0;str[i]!='\0';i++)
    {
        if(str[i]>='A' && str[i]<='Z')
        {
            str[i]|=' ';
        }
    }
}
int main()
{
    char text[]="HELLO WORLD! BITWISE OPERATORS ARE COOL.";
    printf("Original: %s\n",text);
    uppertolower(text);
    printf("Lower case: %s\n",text);
    return 0;
}
```
14.Program to Convert Lowercase Alphabets to uppercase.
```
#include<stdio.h>
void lowertoupper(char *str)
{
    for(int i=0;str[i]!='\0';i++)
    {
        if(str[i]>='a' && str[i]<='z')
        {
            str[i]&='_';
        }
    }
}
int main()
{
    char vis[]="mulaka vishnu vardhan reddy";
    printf("Original: %s\n",vis);
    lowertoupper(vis);
    printf("Lower case: %s\n",vis);
    return 0;
}
```
15.Program to Inverts Alphabets Case
```
#include<stdio.h>
void toggle(char *str)
{
    for(int i=0;str[i]!='\0';i++)
    {
        if(str[i]>='A' && str[i]<='Z' || str[i]>='a' && str[i]<='z')
        {
            str[i]^=' ';
        }
    }
}
int main()
{
    char vis[]="VishnuVARDHANrEdDy";
    printf("Original: %s\n",vis);
    toggle(vis);
    printf("Lower case: %s\n",vis);
}
```
16.Program to find letter poisiton in an alphabet.
```
#include<stdio.h>
void findletter(char letter)
{
    if((letter>='A' && letter<='Z'))
    {
        printf("position of '%c'in alphabet: %d\n",letter,letter-'A'+1);
    }
    else if((letter>='a' && letter<='z'))
    {
        printf("position of '%c' in alphabet: %d\n",letter,letter-'a'+1);
    }
    else{
        printf("'%c' is not an alphabet letter.\n",letter);
    }
}
int main()
{
    char letter;
    printf("Enter a letter: ");
    scanf("%c",&letter);
    findletter(letter);
    return 0;
}
```
17.Program to count setbits in number.
```
#include<stdio.h>
int countsetbits(unsigned int n)
{
    int count=0;
    while(n)
    {
        count+=n&1;
        n>>=1;
    }
    return count;
}
int main()
{
    unsigned int num;
    printf("Enter a number; ");
    scanf("%u",&num);
    printf("Number  of sets bits: %d\n",countsetbits(num));
    return 0;
}
```
18.Program for addition method for swapping the two variables without using a third variable.
```
#include<stdio.h>
int main()
{
    int a=5,y=10;
    printf("Before swapping: a=%d,y=%d\n",a,y);
    a=a+y;
    y=a-y;
    a=a-y;
    printf("After swapping: a=%d, y=%d\n",a,y);
    return 0;
}
                   or                          
// swap two variables without third variable using XOR.
#include<stdio.h>
int main()
{
    int a=5,y=10;
    printf("Before swapping:a= %d,b=%d\n",a,y);
    a=a^y;
    y=a^y;
    a=a^y;
    printf("After Swapping: a=%d,y=%d\n",a,y);
    return 0;
}
```
19. Program to convert a Binary to Decimal.
```
#include<stdio.h>
#include<string.h>
int binarytodecimal(const char *binary)
{
    int decimal=0;
    int length=strlen(binary);
    int base=1;
    for(int i=length-1;i>=0;i--)
    {
        if(binary[i]=='1')
        {
            decimal+=base;
        }
        base*=2;
    }
    return decimal;
}
int main()
{
    char binary[32];
    printf("Enter a binary number: ");
    scanf("%s",binary);
    printf("Decimal equivalent: %d\n",binarytodecimal(binary));
    return 0;
}
```
20.Program to swap evenoddbits.
```
#include<stdio.h>
unsigned int swapevenoddbits(unsigned int num)
{
    unsigned int even_bits=num& 0xAAAAAAAA;
    unsigned int odd_bits=num& 0x55555555;
    even_bits>>=1;
    odd_bits<<=1;
    return (even_bits|odd_bits);
}
int main()
{
    unsigned int num;
    printf("Enter the number:");
    scanf("%d",&num);
    unsigned int result=swapevenoddbits(num);
    printf("original number: %u\n",num);
    printf("Swapped number: %u\n",result);
    return 0;
}
```
