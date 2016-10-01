---
layout: post
comments: true
title: C语言指针
categories: [c]
description: C语言指针
keywords: c, c++,c语言,c语言入门
---

指针是指向一个变量（或）常量和数组的一个内存空间，只能存内存地址。
每一个指针只能指向一种特定类型的变量。
指针定义
数据类型 *指针名；
指针赋值
如：int *p,a;
    p=&a;	
指针p指向变量a,此时a==*p;
   *p=15;
此时a也会等于18

