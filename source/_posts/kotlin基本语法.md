---
title: kotlin基本语法
date: 2018-09-11 15:00:58
tags:	[kotlin]
categories: [Kotlin]
---

Kotlin是JetBrains推出项目，是一种在Java虚拟机上运行的静态类型编程语言，也可以被编译成为JavaScript源代码。在2011年7月推出之前，它已被开发一年之久。直到2016年2月15日，官方发布了第一个稳定的release版本 —— Kotlin v1.0

## 变量的定义 

```kotlin
val PI: Double = 3.1415	//val 声明的为常量, 赋值后不能修改或重新赋值
var age: Int = 20		//var 声明的为变量
var count = 15 	 //自动推断数据类型为 `Int`
var name: String	//声明字段如果没有初始值,数据类型不能省略
name = "张三"
```
## 模板表达式

模板中既可以使用简单变量,也可以使用任意表达式
```kotlin
fun main(args: Array<String>){
	val name = "kotlin"
	val age = 20
	
	println("name=${name}, age=${age}") //输出结果: name=kotlin, age=20
	println("name=${name.replace("k", "K")}, age=${age + 2}") //输出结果: name=Kotlin, age=22
}

```

## 函数的定义

函数的声明使用**`fun`**关键字
定义一个函数,接收两个`Int`的参数, 返回值也为`Int`类型

```kotlin
	fun add(a: Int, b: Int): Int {
		return a + b
	}
	
	//如果函数体只有一条语句可以省略{}使用表达式
	fun add(a: Int, b: Int) = a + b
```
返回`Unit`的函数
如果一个函数没有返回值,那么函数的返回值类型为`Unit`, 这个数据类型可以省略不写,跟`Java`中的`void`类似
```kotlin
	fun say(msg: String): Unit {
		println("say $msg")
	}
	
	//等同于:
	fun say(msg: String) {
		println("say $msg")
	}
	
	//等同于:
	fun say(msg: String) = println("say $msg")
```

## 函数的默认参数
```kotlin
	fun printLog(tag: String = "XY", msg: String) {
		println("$tag->$msg")
	}
	
	fun main(args: Array<String>) {
		printLog("log", "this is log") //输出 log->this is log	
		//默认参数在无默认参数之前,函数必须使用命名参数来调用
		printLog(msg = "hello world") //输出 XY->hello world
	}

```



