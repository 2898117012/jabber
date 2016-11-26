---
layout: post
comments: true
title: C语言运算符
categories: [c]
description: C语言运算符
keywords: c, c++,c语言,c语言入门
---

C语言运算符是说明特定操作的符号，它是构造C语言表达式的工具。C语言的运算异常丰富，除了控制语句和输入输出以外的几乎所有的基本操作都作为运算符处理。除了常见的三大类，算术运算符、关系运算符与逻辑运算符之外，还有一些用于完成特殊任务的运算符，比如位运算符。

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

## 赋值运算符

<table>
	<thead>
		<tr>
			<th>运算符</th>
			<th>说明</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>+=</td>
			<td>a=a+b</td>
		</tr>
		<tr>
			<td>-=</td>
			<td>a=a-b</td>
		</tr>
		<tr>
			<td>*=</td>
			<td>a=a*b</td>
		</tr>
		<tr>
			<td>/=</td>
			<td>a=a/b</td>
		</tr>
		<tr>
			<td>%=</td>
			<td>a=a%b</td>
		</tr>
	</tbody>
</table>

## 关系运算符

<table>
	<thead>
		<tr>
			<th>运算符</th>
			<th>说明</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>></td>
			<td>大于</td>
		</tr>
		<tr>
			<td><</td>
			<td>小于</td>
		</tr>
		<tr>
			<td>>=</td>
			<td>大于等于</td>
		</tr>
		<tr>
			<td><=</td>
			<td>小于等于</td>
		</tr>
		<tr>
			<td>==</td>
			<td>等于</td>
		</tr>
		<tr>
			<td>!=</td>
			<td>不等于</td>
		</tr>
	</tbody>
</table>

## 逻辑运算符

<table>
	<thead>
		<tr>
			<th>运算符</th>
			<th>说明</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>&&</td>
			<td>与</td>
		</tr>
		<tr>
			<td>||</td>
			<td>或</td>
		</tr>
		<tr>
			<td>!</td>
			<td>非</td>
		</tr>
	</tbody>
</table>

> 0表示假,1表示真。在C语言中非0为真

### 条件运算符

```c
expr1 ? expr2 : pxpr3;
```

> 如：max=num1>num2?num1:num2;

### sizeof运算符

> 如：`sizeof(int)`计算运算符占用内存的大小

## 运算符优先级

> `()` 高于 `!`、`++`、`--`、`sizeof` 高于 `*`、`/`、`%` 高于 `+`、`-` 高于 `<`、`<=`、`>`、`>=` 高于 `==`、`!=` 高于 `&&` > `||` 高于 `=`、`+=`、`-=`、`*=`、`/=`、`%=`

- 一元运算符是指那些只处理一个操作的运算符。如`++`，`--`
- 二元运算符是指处理两个操作的运算符。	如`+`、`-`、`*`、`/`、`%`

> 变量和（或）常量与符号的组合称为表达式

## 位运算符

<table>
	<thead>
		<tr>
			<th>运算符</th>
			<th>说明</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>&</td>
			<td>按位`与`运算符</td>
		</tr>
		<tr>
			<td>|</td>
			<td>按位`或`运算符</td>
		</tr>
		<tr>
			<td>^</td>
			<td>按位`异或(EOR)`运算符</td>
		</tr>
		<tr>
			<td>~</td>
			<td>按位`非`运算符,也称为1的补位运算符</td>
		</tr>
		<tr>
			<td><<</td>
			<td>按位`左移`运算符</td>
		</tr>
		<tr>
			<td>>></td>
			<td>按位`右移`运算符</td>
		</tr>
	</tbody>
</table>

### 示例

```c
#include <stdio.h>
void reverse(char *s,int len){
    int i;
    for(i= 0;i<len/2;i++){
        char ch = s[i];
        s[i] = s[len-i-1];
        s[len-i-1] = ch;
    }
}
void dec2bin(int n,char *s){
    int i = 0;
    do{
        s[i++] = n % 2 ? '1' : '0' ;
        n /= 2;
    }while(n);
    s[i] = 0;
    reverse(s,i);
}
int main(void) {
    int x = 100;
    int y = 6;
    int z = x & y;
    char x_str[25];
    char y_str[25];
    char z_str[25];
    dec2bin(x,x_str);
    printf("x 二进制值为：%s\n",x_str);
    dec2bin(y,y_str);
    printf("y 二进制值为：%s\n",y_str);
    dec2bin(z,z_str);
    printf("z 二进制值为：%s\n",z_str);
    return 0;
}
/***
 * x 二进制值为：1100100
 * y 二进制值为：0000110
 * z 二进制值为：0000100
 ***/
```

- [示例代码](https://github.com/2898117012/c-lang-demo/tree/master/operator){:target="_blank"}

> 欢迎大家加入`一起学C语言QQ群：474879609`