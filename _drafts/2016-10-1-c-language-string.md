---
layout: post
comments: true
title: C语言字符串
categories: [c]
description: C语言字符串
keywords: c, c++,c语言,c语言入门
---

字符串是用双引号括起来的任意字符序列。
字符串是多个连续的字符所以保存的时候可以用数组
a[10]可存9个字符，其中一个存'\0'
scanf()中输入不充许存在空格。
所以常用gets()输入
如：gets(a);
用puts输出
如:puts(a);
字符指针
实际应用中人们常用字符指针指向字符数组的元素，以便通过这种指针使用字符数组的内容。最常见的情况是令字符指针指向字符串。
如：char *p="C Language";
字符指针数组
如：
char *name[]={"Apple","Pear","Banana","peach"};
就相当于
name[0]指向"Apple";
name[1]指向"Pear";