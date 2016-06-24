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

* 什么是ART

> Android操作系统已经成熟，Google的Android团队开始将注意力转向一些底层组件，其中之一是负责应用程序运行的Dalvik运行时。Google开发者已经花了两年时间开发更快执行效率更高更省电的替代ART运行时。 ART代表Android Runtime，其处理应用程序执行的方式完全不同于Dalvik，Dalvik是依靠一个Just-In-Time (JIT)编译器去解释字节码。开发者编译后的应用代码需要通过一个解释器在用户的设备上运行，这一机制并不高效，但让应用能更容易在不同硬件和架构上运 行。ART则完全改变了这套做法，在应用安装时就预编译字节码到机器语言，这一机制叫Ahead-Of-Time (AOT）编译。在移除解释代码这一过程后，应用程序执行将更有效率，启动更快。

* ART优点
  * 系统性能的显著提升。
  * 应用启动更快、运行更快、体验更流畅、触感反馈更及时。
  * 更长的电池续航能力。

* ART缺点
  * 更大的存储空间占用，可能会增加10%-20%。
  * 更长的应用安装时间。


##AndroidManifest.xml文件
---

```xml
<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    package="com.example.jonesleborn.myapplication">

    <application
        android:allowBackup="true"
        android:icon="@mipmap/ic_launcher"
        android:label="@string/app_name"
        android:supportsRtl="true"
        android:theme="@style/AppTheme">
        <activity android:name=".MainActivity">
            <intent-filter>
                <action android:name="android.intent.action.MAIN" />

                <category android:name="android.intent.category.LAUNCHER" />
            </intent-filter>
        </activity>
    </application>

</manifest>
```


