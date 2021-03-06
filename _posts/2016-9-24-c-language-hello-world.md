---
layout: post
comments: true
title: C语言Hello World实例详解
categories: [c]
description: C语言Hello World实例详解
keywords: c, c++,c语言,c语言入门
---
麻雀虽小，五脏俱全。通过C语言编程入门之Hello World实例了解程序的开发，运行流程。

## 实例代码
```c 
#include <stdio.h>
void main(){
     printf("Hello World!");
}
```

## 程序说明
- #include 称为预处理语句，因为在编译器开始工作之前，先对这些命令进行预处理。
- <stdio.h> 以.h为后缀的文件被称为头文件，可以是标准库文件，也可以是自定义文件。程序中如用到标准输入输出函数时，就要包含stdio.h头文件。
- main()函数是C程序的处理起点，可以返回一个整数值(int)，也可以不返回(void)。
- {} 语句块符号 { 表示语句块的开始。} 表示语句块的结束。

> 我们编写的是C的源程序，源程序经过编译成目标文件然后连接成可执行文件。

- /* */  多行注释
- // 单行注释

## 返回整数的实例
```c
#include <stdio.h>
int main(){ 
    printf("Hello World!");
    return 0;
}
```

## 程序说明
- return 关键词表示返回结果。

## 关于stdio.h头文件的函数
```c
int getchar()//从标准输入设备读入一个字符
int putchar()//向标准输出设备写出一个字符
int scanf(char*format[,argument…])//从标准输入设备读入格式化后的数据
int printf(char*format[,argument…])//向标准输出设备输出格式化字符串
char gets(char*string)//从标准输入设备读入一个字符串
int puts(char*string)//向标准输出设备输出一个字符串
int sprintf(char*string,char*format[,…])//把格式化的数据写入某个字符串缓冲区
int fflush(FILE *stream) //清除读写缓冲区，需要立即把输出缓冲区的数据进行物理写入时
void rewind(FILE *stream) //将文件内部的位置指针重新指向一个流（数据流/文件）的开头
```

- [示例代码](https://github.com/2898117012/c-lang-demo/tree/master/hello-world){:target="_blank"}

> 欢迎大家加入`一起学C语言QQ群：474879609`