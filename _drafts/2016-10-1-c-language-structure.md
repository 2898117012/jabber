---
layout: post
comments: true
title: C语言结构
categories: [c]
description: C语言结构
keywords: c, c++,c语言,c语言入门
---

定义了结构相当于定义了一个新的数据类型。
定义结构用关键字 struct 引导
如：
struct hu
{
	int i;
	char name;
};
就定义了一种hu的数据类型。
要声明这种类型的变量用
struct hu ww;
这样就声明了一种 hu 的类型变量。
初始化这个变量可以这样写
hu={1,hukei};
也可以动态读入
如
scanf("%d",&ww.i);
gets(ww.name);
