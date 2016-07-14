# day-14

1.Android中也有类似的刷新UI的线程

这个是直接在UI线程中的，并不需要调用RunOnUIThread
new Handler().postDelay(new Runnable(), 延迟时间);