---
layout: post
title: Javascript闭包
categories: [javascript, closure]
description: Javascript闭包
keywords: javascript, closure
---

## 不使用闭包
```javascript
function myFather(myage){
	var age = 20;
	var fatherAge = myage+age;
	return fatherAge;
}
var men = myFather(6);
console.log(men); // output 26
var woMen = myFather(10);
console.log(woMen); // output 30
```

## 使用闭包
```javascript
function myFather(){
    var myage = 6;
    return function(age){
        return myage + age;
    }
}
var men = myFather();
console.log(men(20)); // output 26
console.log(men(24)); // output 30
```

> 闭包是一种设计原则(开放-封闭原则)，它通过分析上下文，来简化用户的调用，让用户在不知晓的情况下，达到他的目的；