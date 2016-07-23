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
  if (version > AppInifoUtils.getVersionCode()) {
    // 说明软件需要更新
  } else {
    // 直接跳到主界面
  }
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

`IntentUtils`

```java
public static void startIntent(Activity context, Class clazz, long delayTime) {
  new Thread() {
    SystemClocl.sleep(delayTime);
    Intent intent = new Intent(context, clazz);
    // 启动一个Activity
    context.startActivity(intent);
  }
}
```

3.消息传递机制

* 只有在主线程中才能new AlertDialog
* 使用`Message msg = Message.Obtain()`

4.下载文件的时候需要使用到断点续传`Xutils`第三方jar包

5.setDataAndType

在使用Intent.setType\/setData的时候，这两句必须要合并在一起，如何不合并在一起的话，执行setType\/setData方法之后，就会把数据清空。

6.APK的签名

`Generate Signed APK` 打包出来的是releas版本的

7.sp是用在text的文字上面的像素单位

8.GridView

显示有多少行增加属性`numColumns`

_**9.图片放到drable和mdp里面有什么区别?**_

10.去掉GridView中的点击背景颜色
`android:listSelector="@android:color/transparent"`

11.选择器selector
可以设置按下去对应显示的图片，以及没有点击时的图片。

12.checkbox获取焦点的事件要默认关闭。
