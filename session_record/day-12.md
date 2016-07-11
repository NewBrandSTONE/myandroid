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