---
layout: post
comments: true
title: C语言条件结构
categories: [c]
description: C语言条件结构
keywords: c, c++,c语言,c语言入门
---

条件表达式由条件运算符构成，并常用条件表达式构成一个赋值语句。执行顺序是从右到左依次判断。

## 表达式结构

### `if`结构

```c
if(a==b){//a==b是条件
   //语名块 a==b 时执行
}
```

### `if`、`else`结构

```c
if(a==b){//a==b是条件
   //语名块 a==b 时执行
}else{ 
   //语名块 a!=b 时执行
}
```

### 多重`if`结构

```c
if(a==b){//a==b是条件
   //语名块 a==b 时执行
}else if(a==c){//a==c是条件
   //语名块 a==c 时执行
}else if(a==d){//a==d是条件
   //语名块 a==d 时执行
}else{ 
   //语名块 a!=b,c,d 时执行
}
```

### 嵌套`if`结构
```c
if(a==b){//a==b是条件
   //语名块 a==b 时执行
   if(a==5){//a==5是条件
      //语名块 a==5 时执行
   }else{ 
      //语名块 a!=5 时执行
   }
}else{ 
   //语名块 a!=b 时执行
   if(a==c){//a==c是条件
      //语名块 a==c 时执行
   }else{ 
      //语名块 a!=c 时执行
   }
}
```

### `switch`结构

```c
switch(a){//a是变量
   case b：//b是常量
      //语句块 a==b时执行
      break; //跳出switch
   case c：
      //语句块 a==c时执行
      break; //跳出switch
   case d：
      //语句块 a==d时执行
      break; //跳出switch
   default:
      //语句块 
}
```

- 在`case`后的各常量表达式值不能相同，否则会出现错误
- default 可以省略

> 多重if结构用于一到三路的分支比较好，switch可用于多重分支

#### 有`break`的`switch`结构 示例

```c
#include <stdio.h>
int main(void) {
   int a = 5;
   switch(a){
      case 4:
         printf("%d\n",4);
         break;
      case 5:
         printf("%d\n",5);
         break;
      case 6:
         printf("%d\n",6);
         break;
      default:
         printf("default");
   }
   return 0;
}
/*** output
 * 5
 ***/
```

#### 无`break`的`switch`结构 示例

```c
#include <stdio.h>
int main(void) {
   int a = 5;
   switch(a){
      case 4:
         printf("%d\n",4);
      case 5:
         printf("%d\n",5);
      case 6:
         printf("%d\n",6);
      default:
         printf("default");
   }
   return 0;
}
/*** output
 * 5
 * 6
 * default
 ***/
```

- [示例代码](https://github.com/2898117012/c-lang-demo/tree/master/switch){:target="_blank"}