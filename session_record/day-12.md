# day-12

##在Android中使用测试方法需要配置的内容

1.在AndroidManifest.xml文件中配置

```xml
<uses-sdk>
...
</uses-sdk>

<!--需要指定AndroidTest的包以及需要测试的目标类-->
<instrumentation android:name="android.test.InstrumentationTestRunner"
  android:targetPackage="需要测试的目标类"
></instrumentation>

<application>
...
<!--需要声明一个使用的类库-->
<uses-library android:name="android.test.runner" />
</application>
```

2.配置内容提供者

通过这个URI系统能够精确的知道，我们要访问的是哪个provider
exported="true" // 可以导出数据
```xml
<provider android:name="对应Provider的全限定名" android:authorites="内容提供者的地址，相当于主机名,就是对应的uri"
android:exported="true" 
></provider>
```

3.拿到contentResolver
```java
ContentResolver cr = getContentResolver();
```

4.使用ContentValues 插入不同字段的数据，记得要values.clear()一下，如果是插入相同的数据，则不用clear

5.代码块、静态代码块、构造方法执行的先后顺序

对象的初始化顺序:首先执行父类静态的内容，父类静态的内容执行完毕后，接着去执行子类的静态的内容，当子类的静态内容执行完毕之后，再去看父类有没有非静态代码块，如果有就执行父类的非静态代码块，父类的非静态代码块执行完毕，接着执行父类的构造方法；父类的构造方法执行完毕之后，它接着去看子类有没有非静态代码块，如果有就执行子类的非静态代码块。子类的非静态代码块执行完毕再去执行子类的构造方法。总之一句话，静态代码块内容先执行，接着执行父类非静态代码块和构造方法，然后执行子类非静态代码块和构造方法。 
而且子类的构造方法，不管这个构造方法带不带参数，默认的它都会先去寻找父类的不带参数的构造方法。如果父类没有不带参数的构造方法，那么子类必须用supper关键子来调用父类带参数的构造方法，否则编译不能通过。 

6.XML标签中的standalone是什么意思

// standalone  用来表示该文件是否呼叫其它外部的文件。若值是 ”yes” 表示没有呼叫外部文件，若值是 ”no” 则表示有呼叫外部文件。默认值是 “yes”
xs.startDocument("utf-8", true);