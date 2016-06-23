# Android Introduction

##JVM跟DVM的比较
---

| 区别 | JVM | DVM
| -- | -- | -- |
| 编译后文件的格式 | .java -> .class -> .jar | .java -> .class -> .dex -> .apk
| 基于的架构 | 基于栈的架构 | 基于内存器的架构


* 什么是栈

> 内存中的一种数据结构

* 什么是寄存器

> 寄存器是CPU中的一个存储单元


> `栈`是保存在`内存`中的,`寄存器`是保存在`CPU`中的

* 为什么.apk的文件里面只有一个classes.dev的文件

> 因为将所有的.class打包成一个文件，这样子移动的速度比较快。
> 
> 因为无论是.class文件或者是.dex文件，都有一个header，
>
> 如果有一千个文件，就会有一千个header这样处理起来非常慢

