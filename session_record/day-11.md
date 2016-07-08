# day-11

1.Service

* Service和Activity都是继承了context

* 在MainActivity中通过 bindService(Intent,ServiceConnection , flags);启动一个服务

* IBinder 进程间通讯的一个接口

* 为什么通过接口实现的类，就不能通过反射调用类中的私有方法

* 只要某个组件调用了bindService(可以与数据进行交互)，当组件销毁的时候，对应的service也销毁了,然而使用startService的不会跟组件一起销毁（不能跟数据进行交互）

* 不要多次绑定服务，不要多次解绑服务