# day-09

1.Activity生命周期

 * onDestroy-AC销毁 TextUtils可以判断字符串是否为空`TextUtils.isEmpty(phone)`

 * onStop当当前的界面被隐藏掉的时候，就会调用该方法

 * 当当前界面被显示的时候调用onStart方法 

 * onPause 所有的控件都失去了焦点，不能跟用户进行交互

 * onResume 从暂停中或者onPasuse中恢复