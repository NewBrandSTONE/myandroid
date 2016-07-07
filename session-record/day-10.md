# day-10

1. intent

* intent.setType()设置MIME类型

2. 自定义广播

* sendOrderedBroadcast(intent)有序广播
  *  

* sendBroadcast()无序广播
  * 广播接收者的接收顺序是不固定的，可以认为它们几乎是同时接收到的。

* Bundle 包含一切想要携带的数据

* 如何选型
  * 广播接受者需要顺序 广播接受者可以拦截的数据 可以修改数据的时候 选择有序广播


* 5秒时间内App没有响应，则弹出ANR(Application not response)

* SystemClock.sleep(ms); 让系统睡一下

* BroadCastReceiver的 onReceive方式是在主线程里面运行的

3. Service

* getSystemService(String name)//name指定->获取系统级的服务

* 如果想找几个常量，定义在一个类里，去找它的相关类

* 测试的时候，打电话的声音从MIC中来(MediaRecorder.AuiudioSource.MIC)


  

