# Android Introduction

##JVM跟DVM的比较
---

| 区别 | JVM | DVM
| -- | -- | -- |
| 编译后文件的格式 | .java -> .class -> .jar | .java -> .class -> .dex -> .apk
| 基于的架构 | 基于栈的架构 | 基于内存器的架构

* 什么是.dex格式

> .dex格式是专门为`Darlvik`设计的一种压缩格式，适合内存和处理器有限的系统


* 什么是栈

> 内存中的一种数据结构

* 什么是寄存器

> 寄存器是CPU中的一个存储单元
>
> `栈`是保存在`内存`中的,`寄存器`是保存在`CPU`中的
> 
> 在`DVM`中寄存器里面保存的是内存地址，在`JVM`中栈里面保存的是内存地址

* 为什么.apk的文件里面只有一个classes.dev的文件

> 因为将所有的.class打包成一个文件，这样子移动的速度比较快。
> 
> 因为无论是.class文件或者是.dex文件，都有一个header，
>
> 如果有一千个文件，就会有一千个header这样处理起来非常慢


##Dalvik和ART的区别
---
* 什么是Dalvik

> Dalvik是Google公司自己设计用于Android平台的Java虚拟机。Dalvik虚拟机是Google等厂商合作开发的Android移动设备平台的核心组成部分之一。它可以支持已转换为 .dex（即Dalvik Executable）格式的Java应用程序的运行，.dex格式是专为Dalvik设计的一种压缩格式，适合内存和处理器速度有限的系统。Dalvik 经过优化，允许在有限的内存中同时运行多个虚拟机的实例，并且每一个Dalvik 应用作为一个独立的Linux 进程执行。独立的进程可以防止在虚拟机崩溃的时候所有程序都被关闭。


