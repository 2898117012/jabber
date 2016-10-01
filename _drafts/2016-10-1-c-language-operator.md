---
layout: post
comments: true
title: C语言运算符
categories: [c]
description: C语言运算符
keywords: c, c++,c语言,c语言入门
---

## 算术运算符
<table>
	<thead>
		<tr>
			<th>运算符</th>
			<th>说明</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>+</td>
			<td>加</td>
		</tr>
		<tr>
			<td>-</td>
			<td>减</td>
		</tr>
		<tr>
			<td>*</td>
			<td>乘</td>
		</tr>
		<tr>
			<td>/</td>
			<td>除</td>
		</tr>
		<tr>
			<td>%</td>
			<td>取余</td>
		</tr>
		<tr>
			<td>++</td>
			<td>自增</td>
		</tr>
		<tr>
			<td>--</td>
			<td>自减</td>
		</tr>
	</tbody>
</table>

- 一元运算符是指那些只处理一个操作的运算符。如“++，--”
- 二元运算符是指处理两个操作的运算符。	如“+、-、*、/、%”

变量和（或）常量与符号的组合称为表达式
赋值运算符
运算符		相当于	
+=		a=a+b
-=		a=a-b
*=		a=a*b
/=		a=a/b
%=		a=a%b
关系表达式
>		大于	
<		小于	
>=		大于等于
<=		小于等于
==		等于
!=		不等于
条件结构
if结构
if(<条件>)
<语句块>
if--else结构
if(<条件>)
<语句块>
else
<语名块>
逻辑运算符
&&		与
||		或
!		非
0表示假1表示真，在C语言中非0为真
sizeof运算符
如：sizeof(int)计算运算符占用内存的大小
运算符优先级
()
!、++、--、sizeof
*、/、%
+、-
<、<=、>、>=
==、!=
&&
||
=、+=、-=、*=、/=、%=
