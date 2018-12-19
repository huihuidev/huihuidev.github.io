---
title: 'kotlin变量,常量,注释'
date: 2018-12-19 11:39:23
tags: [kotlin]
categories: [Kotlin]
---

## 定义变量,常量
**声明普通变量**
`Kotlin` 中定义变量,常量跟`Java`中有很大区别, `kotlin`中必须使用`var`, `val`关键字修饰
```kotlin
定义变量: 变量可读可写, 定义后可重复赋值, 相当于Java中的普通变量
var <变量标识符>: <数据类型> = <初始化值>

定义常量: 常量可读不可写,一旦定义不能修改其值, 相当于Java中final修饰的常量
val <常量标识符>: <数据类型> = <初始化值>
```

```kotlin
var name: String = "kotlin"	//声明时直接赋值
var age: Int 	 //无初始化值时不能省略数据类型
age = 100		//先声明后赋值
var sex = 1		//自动推断数据类型 Int

val PI: Double = 3.1415 //声明常量直接赋值
// PI = 3.20 此时会报语法错误,val修饰的常量不能重新赋值
val title: String		//声明常量,暂不赋值
title = "kotlin NB"	//未赋值的常量可以赋值一次
```

**声明可空变量**
`Java`中声明的变量不用关心是否为空,只需要在用到的时候添加非空判断即可,否则就会出现著名的`NullPointException`,这样就可能无形的增加了无用代码.在`Kotlin`中我们就可以避免这样无用的代码判断,我们可以根据情况来声明变量是否可以为null(可空变量),如果变量不可为空就使用上面我们定义普通变量的形式定义.
```kotlin
可空变量的声明格式:
var <变量标识符>: <数据类型>? = <初始值>/null

var name: String? = null
var title: String? = "kotlin"
var age: Int?
```
说明:可空变量声明时数据类型不能省略,并且数据类型后面一定要添加`?`来表示变量是可以为空的

## const修饰的常量
> const只能修饰`val`声明的常量, 不能修饰`var`声明的变量
> const修饰常量只能位于顶层或者`object`声明的对象,或者`companion object` 声明的伴生对象中
> const声明的常量必须直接赋值
> const声明的属性不加限定符的默认为public, 只用`val`声明的属性限定符默认为private

## 注释
`kotlin`语言和`Java`语言一样,都支持在程序里面编写注释,来提高代码的可读性
* 单行注释(以`//`开头)
```kotlin
 //这是单行注释
```
* 多行注释(块注释, 以`/*`开头, `*/`结尾)

```kotlin
/* 多行注释
    代码块一
    代码块二
 	*/
```
`kotlin`的多行注释跟`Java`不同的是`kotlin`的多行注释可以嵌套使用,`Java`语言不支持嵌套多行注释
```Java

class Person{
//下面的嵌套注释在java中是错误的, 在kotlin中是正确的
	/*public String name;
	  /*public int sex;
	  */
	 public int age; 
	 */
}

```
* 类注释, 方法注释(以`/**`开头, 以`*/`结尾, 语法同`Java`相同)

```kotlin
/**
 * 定义类
 * /
class Person {

}

/**
 * 定义一个方法
 * /
 fun add(a: Int, b: Int): Int {
 	return a + b
 }
```

