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