---
layout: post
comments: true
title: C语言循环结构
categories: [c]
description: C语言循环结构
keywords: c, c++,c语言,c语言入门
---

C语言循环控制语句提供了`while`语句、`do`-`while`语句和`for`语句来实现循环结构。程序中的循环此在特定的条件下重复执行。

## 表达式结构

### `while`结构

```c
int i = 10;
while(i--){ //i--是条件
   //语名块 i>0 时执行
}
```

> 用于在特定的条件为真的情况下重复执行（先判断后执行）

### `do`、`while`结构

```c
int i = 10;
do{ 
   //语名块 i>0 时执行
}while(i--);//i--是条件
```

> 用于在特定的条件为真的情况下重复执行，至少执行一次（先执行，后判断）

### `for`结构

```c
for(int i=0;i<=10;i++){
   //语名块 i<=10 时执行
}
```

> for ( [表达式 1]; [表达式 2 ]; [表达式3] )

- 表达式1：一般为赋值表达式，给控制变量赋初值；
- 表达式2：关系表达式或逻辑表达式，循环控制条件；
- 表达式3：一般为赋值表达式，给控制变量增量或减量；

> 用于在特定的条件为真的情况下重复执行（先判断后执行）

#### `break;`

```c
#include <stdio.h>
int main(void) {
    for(int i=0;i<=10;i++){
        if(i==5){
            break;
        }
        printf("%d\n",i);
    }
    return 0;
}
/***
 * output
 * 0
 * 1
 * 2
 * 3
 * 4
 ***/
```
> 可使程序终止循环而执行后面的语句，可在条件结构和循环结构中使用。

#### `continue;`

```c
#include <stdio.h>
int main(void) {
    for(int i=0;i<=10;i++){
        if(i==5){
            continue;
        }
        printf("%d\n",i);
    }
    return 0;
}
/***
 * output
 * 0
 * 1
 * 2
 * 3
 * 4
 * 6
 * 7
 * 8
 * 9
 * 10
 ***/
```
> 只能用在循环里，作用是跳过循环体中剩余的语句而准备执行下一次循环。

- [示例代码](https://github.com/2898117012/c-lang-demo/tree/master/while){:target="_blank"}

> 欢迎大家加入`一起学C语言QQ群：474879609`