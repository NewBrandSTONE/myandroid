# day-01

1.欢迎界面做什么

* 检测网络是否连通。
* 初始化数据库。
* 联网检测版本是否有更新。

2.访问网络记

* 需要在子线程中操作
* 需要AndroidManifest.xml中配置对应的网络权限

`SplahActivity.java`
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
  // 得到服务器返回的输入流
  InputStream is = conn.getInputStream();
  // 将输入流转换为String字符串
  String jsonString = StringUtils.readInputStream(is);
  // 解析Json类型的数据
  JSONObject jsonObject = new JSONObject();
  int version = jsonObject.getInt("version");
  Sting downloadURL =  jsonObject.getString("dowloadUrl");
  String des = jsonObject.getString("des");
}
```

`StringUtils.java`
```java
public static String readInputStream(InputStream ins) {
  ByteArrayOutputStream boas = new ByteArrayOutputStream();
  byte[] bufere = new byte[1024];
  int len = -1;
  while((len = is.read(bufere)) != -1) {
    boas.write(bufere, 0, len);
  }
  ins.close();
  boas.close();
  return boas.toString();
  finally {
    boas.close();
  }
}
```
