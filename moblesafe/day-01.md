# day-01

1.欢迎界面做什么

* 检测网络是否连通。
* 初始化数据库。
* 联网检测版本是否有更新。

2.访问网络记

* 需要在子线程中操作
* 需要AndroidManifest.xml中配置对应的网络权限

```java
// 1.得到响应的url
URL url = new URL(getResource.getString(R.string.url));
// 可以将URL地址，放在values/strings.xml文件中
// getResource.getString(R.string.url)
// 2.得到连接
HttpURLConnection conn = (HttpURLConnection) url.openConnection();
// 3.设置相关的访问方法
conn.setRequestMethod("GET");
// 4.设置访问超时时间
conn.setConnectionTimeout(5000);
// 5.获得服务器返回的请求码
int code = conn.getResponseCode();
if (code == 200) {
  // 说明连接是成功的
}
```

