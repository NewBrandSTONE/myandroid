# day-09

1. Activity生命周期

 * onDestroy-AC销毁 TextUtils可以判断字符串是否为空`TextUtils.isEmpty(phone)`

 * onStop当当前的界面被隐藏掉的时候，就会调用该方法

 * 当当前界面被显示的时候调用onStart方法 

 * onPause 所有的控件都失去了焦点，不能跟用户进行交互

 * onResume 从暂停中或者onPasuse中恢复

 * 横竖屏切换的时候，会导致Activity重新绘制
   * 要么只能横屏要么只能竖屏在Manifest中配置`<activity android:screenOrientation=`
   * 告诉手机忽略掉横竖屏所引起的生命周期问题`<activity android:configChanges="orientation|keyboradhidden">`

2. 任务栈

* singleTop：如果下一次要新建一个Activity，跟栈顶的是同样的Activity，则不会创建新的Activity

* singleTask：首先判断任务栈中，有没有该界面，如果没有则创建，然后显示；如果有先判断是否在栈顶，如果是，则什么都不做；如果不在栈顶，则将该activity放到栈顶，再删除原来在它任务栈上面的所有任务。

* singleInstance的界面，独有自己的一个任务栈，该任务栈其他页面不能存放；如果已经出现了该界面，接下来再次启动该界面，没有效果；如果该界面已经创建，而且手机当前显示的是其他的界面，此时想启动该界面，那么会将该任务栈提前。

3. 广播

* 监听电话外拨是一个敏感操作，需要在Manifest中配置对应的权限。

* 应用不用运行也能接受到广播

* 单纯的读取SD卡的状态不需要权限

* 数据可以通过intent传输或者Bundle传递（Bundle只是把所有想要传递的数据封装起来了,内部是一个HashMap）

* 采用二进制的报文 bundle.get("pdus");

* 取消广播 abortionBrocast?

* 关心安装包是否被安装或者卸载，需要添加`<data:schma:package>`


4. 复习

* HttpUrlConnneticon


* HttpClient

* 获取sd卡的路径 Enviroment.getExtranlStorage();

