# day-13

1.布局文件中android:width与android:layout_width的区别是什么?


2.将bitmap保存到文件中

```java
FileOutputStream fous = openFileOutput("test.png", MODE_PRIVATE);
bitmap.compress(Bitmap.CompressFormat.PNG, 100, fous);
```

3.在做画画板的时候，在ACTION_MOVE里面将mStartX = mEndX 同理Y轴也是一样

4.SeekBar相关知识

```xml
<!--设置最大值-->
android:max="256"
<!--设置当前值-->
android:progress="128"
```

5.代码中获取seekBar的值

```java
seekBar.getProgress();
```

6.HandleMessage的使用注意事项

HandleMessage一般是定义在主线程中的，而且需要使用静态修饰，因为有可能其他很多的类需要使用这个HandleMessage，如果不设置成静态的话，可以通过传参的方式解决，但是这样容易出现问题。

```java
// 在另外一个类中获取到主线程的HandleMessage
// new 一个Message对象
Message msg = MainActivity.handle.obtainMessage();
// 可以通过键值对的方式bundle
Bundle bundle = new Bundle();
bundle.putInt("duration", duration);
bundle.putInt("currentPosition", currentPosition);
msg.put(bundle);
MainActivity.handler.sendMessage(msg);
```