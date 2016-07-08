# day-11

1.Service

* Service和Activity都是继承了context

* 在MainActivity中通过 bindService(Intent,ServiceConnection , flags);启动一个服务

* IBinder 进程间通讯的一个接口

* 为什么通过接口实现的类，就不能通过反射调用类中的私有方法