# day-10

1. intent

* intent.setType()设置MIME类型

---

2. 自定义广播

* sendOrderedBroadcast(intent)有序广播
  *  

* sendBroadcast()无序广播
  * 广播接收者的接收顺序是不固定的，可以认为它们几乎是同时接收到的。

* Bundle 包含一切想要携带的数据

* 如何选型
  * 广播接受者需要顺序 广播接受者可以拦截的数据 可以修改数据的时候 选择有序广播

* 广播接收者不能执行耗时操作，如果5秒时间内App没有响应，则弹出ANR(Application not response)

* SystemClock.sleep(ms); 让系统睡一下

* BroadCastReceiver的 onReceive方式是在主线程里面运行的

* 锁屏与解锁是一个比较频繁的操作，此时广播的接收者不需要通过Manifest.xml这个配置文件来配置，而是使用Java代码来进行注册，记得注册之后调用注销的方法(否则会报错)

```java
// onCreate()方法中，通过代码来注册一个广播接收者
IntentFilter filter = new IntentFilter();
filter.addAction(Intent.ACTION_SCRREN_OFF); // 设置多个action
filter.addAction(Intent.ACTION_SCRREN_ON); // 设置多个action
registerReceiver(new SrceenReceiver(), filter); // 第一个参数是自己新建的类

// onDestroy中
  super.onDestroy();
  unregisterReceiver()screenRegester);
```

---

3. Service

* 没有界面 后台一直运行 可以与界面进行交互，已经脱离了应用，即使应用关闭了，服务也能在后台自己运行。

* getSystemService(String name)//name指定->获取系统级的服务

* 如果想找几个常量，定义在一个类里，去找它的相关类

* 测试的时候，打电话的声音从MIC中来(MediaRecorder.AuiudioSource.MIC)

* 服务的onCreate方法中也不应该执行耗时操作

* 让Service每三秒打印一句话

```java
Timer timer = new Timer();
// 每三秒打印一句话
// delay要延迟的描述
timer.schedule(new TimerTask(){
  public void run() {
    Log.v("Oz", "Service");
  }, 3000, 3000);
}, delay, period);
```

* Service的onCreate方法也是运行在主线程上面的

* 服务与子线程的区别
  * 应用的进程被杀死(整个应用就退出了) 服务先被杀死，然后在被创建(先调用了onDestory方法，然后又调用了onCreate方法)
  * 应用的子线程被杀死 子线程也同样被杀死，不会再创建了


  

