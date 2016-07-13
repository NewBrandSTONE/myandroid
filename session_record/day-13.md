# day-13

1.布局文件中android:width与android:layout_width的区别是什么?


2.将bitmap保存到文件中

```java
FileOutputStream fous = openFileOutput("test.png", MODE_PRIVATE);
bitmap.compress(Bitmap.CompressFormat.PNG, 100, fous);
```