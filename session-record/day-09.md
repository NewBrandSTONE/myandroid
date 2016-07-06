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

2.任务栈

* singleTop：如果下一次要新建一个Activity，跟栈顶的是同样的Activity，则不会创建新的Activity

* singleTask：首先判断任务栈中，有没有该界面，如果没有则创建，然后显示；如果有先判断是否在栈顶，如果是，则什么都不做；如果不在栈顶，则将该activity放到栈顶，再删除原来在它任务栈上面的所有任务。