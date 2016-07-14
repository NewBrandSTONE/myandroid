# day-14

1.Android中也有类似的刷新UI的线程

这个是直接在UI线程中的，并不需要调用RunOnUIThread
new Handler().postDelay(new Runnable(), 延迟时间);

2.Android中设置横屏

在AndroidManifest.xml中配置
android:screenOrientation="landscape"

```xml
<application
        android:allowBackup="true"
        android:icon="@mipmap/ic_launcher"
        android:label="@string/app_name"
        android:supportsRtl="true"
        android:theme="@style/AppTheme">
        <activity
            android:name=".MainActivity"
            android:screenOrientation="landscape">
            <intent-filter>
                <action android:name="android.intent.action.MAIN" />

                <category android:name="android.intent.category.LAUNCHER" />
            </intent-filter>
        </activity>
    </application>
```

3.直播

不使用mediaplay，使用FFMpeg RTMP协议
