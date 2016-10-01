---
layout: post
comments: true
title: C语言条件结构
categories: [c]
description: C语言条件结构
keywords: c, c++,c语言,c语言入门
---

多重if结构
if(<条件>)
<语句块>
else if(<条件>)
<语句块>
else if(<条件>)
<语句块>
嵌套if
if(<表达式1>)
	if(<表达式2>)
else
<语句块>

switch结构
switch(表达式)
{
	case 常量表达式：
		（语句块）；
		break;
	case 常量表达式：
		（语句块）；
		break;
	case 常量表达式：
		（语句块）；
		break;
	default:
		（语句块）；
}
在case后的各常量表达式值不能相同，否则会出现错误
default 可以省略
if-else-if可用与一到三路的分支比较好
switch可用与多重分支
条件运算符
expr1?expr2:pxpr3;
如：max=num1>num2?num1:num2;

