---
layout: post
comments: true
title: C语言变量和数据类型
categories: [c]
description: C语言变量和数据类型
keywords: c, c++,c语言,c语言入门
---
变量可以通过变量名访问。在指令式语言中，变量通常是可变的；由于变量让你能够把程序中准备使用的每一段数据都赋给一个简短、易于记忆的名字，因此它们十分有用。
## 什么是变量
变量是一种使用方便的占位符，用于引用计算机内存地址，该地址可以存储Script运行时可更改的程序信息。变量可以通过变量名访问。在指令式语言中，变量通常是可变的；由于变量让你能够把程序中准备使用的每一段数据都赋给一个简短、易于记忆的名字，因此它们十分有用。其值可变的量叫做变量。每个变量都有自己的生命周期和内存地址。

### 变量命名
在C语言中变量名可以由字母A-Z和a-z数字0-9，和下划线组合而成。

### 变量使用原则
- 先声明
- 再赋值
- 后使用

## 变量种类
- 全局变量
- 局部变量

### 全局变量
在函数外部申明的变量叫全局变量，可以在任何一个函数中使用。多个函数中使用相同的变量，变量值是共享的。
```c
#include <stdio.h>
void show();
int age = 0;
int main(void) { 
	show();
	printf("my age:%d",age);
	return 0;
}
void show(){
    age = 10;
}
//output my age:10
```

> `int age = 0;` 是申明一个变量，因为在函数外，所以`age`是全局变量。

### 局部变量
在函数内申请的变量叫局部变量，局部变量只能在当前函数中使用。
```c
#include <stdio.h>
int main(void) { 
	int age = 10
	printf("my age:%d",age);
	return 0;
}
//output my age:10
```

> 这里的`age`是一个局部变量

## 如何申明变量
申明一个变量，由数据类型和变量名组成。
```c
//无初始值
int age; 
double money;
//设置初始值
int myage = 20;
double myMoney = 1000;
```
## 什么叫常量
在程序中保持不变的量叫做常量。定义常量用来代替相同的且不变的值。如 PI = 3.1415926
> 常量使用之前必须定义用 `#define`

```c
#define PI 3.1415926
```
### 使用示例

```c
#include <stdio.h>
#define PI 3.1415926
int main(void) {
    #define AGE 20
    printf("PI:%f\n",PI);
    printf("AGE:%d\n",AGE);
    return 0;
}
/***
 * output
 * PI:3.141593
 * AGE:20
 ***/
``` 

## 数据类型
<table>
	<caption>C语言数据类型</caption>
	<thead>
		<tr>
			<th>类型名称</th>
			<th>说明</th>
			<th>字节数</th>
			<th>取值范围</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>int</td>
			<td>整型</td>
			<td>16位</td>
			<td>-32768至+32767</td>
		</tr>
		<tr>
			<td>short int</td>
			<td>短整型</td>
			<td>16位</td>
			<td>0至65535</td>
		</tr>
		<tr>
			<td>long int</td>
			<td>长整型</td>
			<td>32位</td>
			<td>-2147483648至2147483647</td>
		</tr>
		<tr>
			<td>unsigned long int</td>
			<td>无符号长整型</td>
			<td>32位</td>
			<td>0至4294967295</td>
		</tr>
		<tr>
			<td>unsigned short int</td>
			<td>无符号短整型</td>
			<td>16位</td>
			<td>0至65535</td>
		</tr>
		<tr>
			<td>float</td>
			<td>单精度浮点型</td>
			<td>32位</td>
			<td>10e-38至10e38</td>
		</tr>
		<tr>
			<td>double</td>
			<td>双精度浮点型</td>
			<td>64位</td>
			<td>10e-308至10e308</td>
		</tr>
		<tr>
			<td>char</td>
			<td>字符型</td>
			<td>8位</td>
			<td>-128至+127</td>
		</tr>
	</tbody>
</table>

## 输入和输出

## 转义符

## 常用转换字符串列表

## 算术运算符

## 类型转换
- 自动类型转换按从小到大顺序排列

> `short` > `int` > `long` > `float` > `double`

- 强制类型转换

```c
int c=(int)a/b;
```