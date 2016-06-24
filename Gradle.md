# Gradle

##什么是Gradle？
---
Gradle是一种依赖管理工具，基于Groovy语言，面向Java应用为主，它抛弃了基于XML的各种繁琐配置，取而代之的是一种基于Groovy的内部领域特定（DSL）语言。

##Gradle的基本概念
---
以stormzhang的开源项目9GAG为例说明，与Gradle有关的文件如下几个：

![](/images/gradle-01.jpeg)

1.9GAG/app/build.gradle

这个文件是app文件夹下这个Module的gradle配置文件，也可以算是整个项目最主要的gradle配置文件，我们来看下这个文件的内容：

```xml
// 声明是Android程序
apply plugin: 'com.android.application'

android {
    // 编译SDK的版本
    compileSdkVersion 21
    // build tools的版本
    buildToolsVersion "21.1.1"

    defaultConfig {
        // 应用的包名
        applicationId "me.storm.ninegag"
        minSdkVersion 14
        targetSdkVersion 21
        versionCode 1
        versionName "1.0.0"
    }

    // java版本
    compileOptions {
        sourceCompatibility JavaVersion.VERSION_1_7
        targetCompatibility JavaVersion.VERSION_1_7
    }

    buildTypes {
        release {
            // 是否进行混淆
            minifyEnabled false
            // 混淆文件的位置
            proguardFiles getDefaultProguardFile('proguard-android.txt'), 'proguard-rules.txt'
        }
    }

    // 移除lint检查的error
    lintOptions {
      abortOnError false
    }
}

dependencies {
    // 编译libs目录下的所有jar包
    compile fileTree(dir: 'libs', include: ['*.jar'])
    compile 'com.android.support:support-v4:21.0.2'
    compile 'com.etsy.android.grid:library:1.0.5'
    compile 'com.alexvasilkov:foldable-layout:1.0.1'
    // 编译extras目录下的ShimmerAndroid模块
    compile project(':extras:ShimmerAndroid')
}
```


