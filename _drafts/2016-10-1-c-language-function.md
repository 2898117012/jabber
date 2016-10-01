---
layout: post
comments: true
title: C语言函数
categories: [c]
description: C语言函数
keywords: c, c++,c语言,c语言入门
---

函数是一个功能单一的代码块。为了方便重复使用。
内置函数，
内置函数由C语言系统提供，用户无须定义，也不必在程序中作类型说明。
自定义函数
函数定义
返回值类型 函数名（参数类型 参数名）；
无定义参数可定成为(), void.
函数原形是指在开始没有写函数的内容，只是先说明。放在main()前。
如 void hu();
如果在直接在下面写函数的内容不要";"号。
函数返回值
return <表达式>
存储类型
auto		自动变量		我们一般声明的变量为自动变量，它的生存期是在某个函数内
static		静态变量		它的生存期是在整个程序

math.h的内置函数
double sqrt(double x)		计算x的平方根
double pow(double x,double y)	计算x的y次幂
double ceil(double x)		求不小于x的最小整数,并以double形式显示
double floor(double x)		求不大于x的最大整数,并以double形式显示

Ctype.h的内置函数
int toupper(int x)		如果x为小写字母，则返回对应的大写字母
int tolower(int x)		如果x为大写字母，则返回对就的小写字母

stdlib.h的内置函数
int rand(void)			产生一个随机数  可以在调用rand()函数之前调用srand((unsigned)time(NULL)),这样以time函数值做为种子
void exit(int retval)		终止程序

String.h的内置函数
strlen(String)			计算字符串的长度
strcpy(dest,src)		dest是目标字符串，src是源字符串.用于将一个字符串复制到别一个字符串
strcmp(str1,str2)		用于比较两个字符串的函数,相同返回0，str1大于str2返回正值,str1小于str2返回负值
strcat(dest,src)		dest是目标字符串,src是源字符串,用于将src加到dest里		
