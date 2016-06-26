# day-02

1.viewgroup无法对子控件的排布进行控制，所以不能写布局文件的在最顶上

2.Tablerow，android中唯一不用指定宽高的控件

3.dp是宽高的单位，sp是字体的单位

4.AS中打印System.out.println()的快捷键是sout

5.scollview只能包含一个组件

6.Calender获取年月日

***7.xml中@+id与@id的区别***

8.WebView 默认js不能加载，必须要获取了settings才行

settings.setJavaScriptEnable(true);

点击网页的时候是默认打开了一个浏览器

wv.setWebViewCilent(new WebViewClient() {
  return super.showOverriderURLEncoding
});