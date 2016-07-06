# day-09

1.Activity生命周期

 * onDestroy-AC销毁 TextUtils可以判断字符串是否为空`TextUtils.isEmpty(phone)`

 * onStop当当前的界面被隐藏掉的时候，就会调用该方法

 * 当当前界面被显示的时候调用onStart方法 

 * onPause 所有的控件都失去了焦点，不能跟用户进行交互

 * onResume 从暂停中或者onPasuse中恢复

 * 横竖屏切换的时候，会导致Activity重新绘制
   * 要么只能横屏要么只能竖屏在Manifest中配置`<activity android:screenOrientation=`
   * 告诉手机忽略掉横竖屏所引起的生命周期问题`<activity android:configChanges="orientation|keyboradhidden">`