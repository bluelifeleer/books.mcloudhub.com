### WebView

```
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    package="com.example.bluelifeleer.webview_learn">
    <uses-permission android:name="android.permission.INTERNET"/>
    ...
</manifest>
```

#### 添加webView视图控件

```
<WebView
    android:id="@+id/webViewContainer"
    android:layout_width="match_parent"
    android:layout_height="match_parent" />
```

#### 导入包

```
//import android.webkit.WebSettings;
import android.webkit.WebChromeClient;
import android.webkit.WebView;
import android.webkit.WebViewClient;
```

#### 实例

```
private WebChromeClient webChromeClient = new WebChromeClient(){
    public void onProgressChanged(WebView view, int newProgress) {
        if (newProgress < 100) {
            String progress = newProgress + "%";
        } else {
        }
    }

    //获取Web页中的title用来设置自己界面中的title
    //当加载出错的时候，比如无网络，这时onReceiveTitle中获取的标题为 找不到该网页,
    //因此建议当触发onReceiveError时，不要使用获取到的title
    @Override
    public void onReceivedTitle(WebView view, String title) {
        MainActivity.this.setTitle(title);
    }
};

//        settings = webView.getSettings();
webView = findViewById(R.id.webViewContainer);
//        // 启用HTML5 DOM storage API，默认值 false
//        settings.setDomStorageEnabled(true);
//        // 定位(location)
//        settings.setGeolocationEnabled(true);
//        // 是否保存表单数据
//        settings.setSaveFormData(true);
//        // 是否当webview调用requestFocus时为页面的某个元素设置焦点，默认值 true
//        settings.setNeedInitialFocus(true);
//        // 是否支持viewport属性，默认值 false
//        // 页面通过`<meta name="viewport" ... />`自适应手机屏幕
//        settings.setUseWideViewPort(true);
//        // 是否使用overview mode加载页面，默认值 false
//        // 当页面宽度大于WebView宽度时，缩小使页面宽度等于WebView宽度
//        settings.setLoadWithOverviewMode(true);
//        // 布局算法
//        settings.setLayoutAlgorithm(WebSettings.LayoutAlgorithm.NORMAL);
//        // 是否支持Javascript，默认值false
//        settings.setJavaScriptEnabled(true);
//        // 是否支持多窗口，默认值false
//        settings.setSupportMultipleWindows(false);
//        // 是否可用Javascript(window.open)打开窗口，默认值 false
//        settings.setJavaScriptCanOpenWindowsAutomatically(false);
//        // 资源访问
//        settings.setAllowContentAccess(true); // 是否可访问Content Provider的资源，默认值 true
//        settings.setAllowFileAccess(true);    // 是否可访问本地文件，默认值 true
//        // 是否允许通过file url加载的Javascript读取本地文件，默认值 false
//        // settings.setAllowFileAccessFromFileURLs(false);
//        // 是否允许通过file url加载的Javascript读取全部资源(包括文件,http,https)，默认值 false
//        // settings.setAllowUniversalAccessFromFileURLs(false);
//        // 资源加载
//        settings.setLoadsImagesAutomatically(true); // 是否自动加载图片
//        settings.setBlockNetworkImage(false);       // 禁止加载网络图片
//        settings.setBlockNetworkLoads(false);       // 禁止加载所有网络资源
//        // 缩放(zoom)
//        settings.setSupportZoom(true);          // 是否支持缩放
//        settings.setBuiltInZoomControls(false); // 是否使用内置缩放机制
//        settings.setDisplayZoomControls(true);  // 是否显示内置缩放控件
//        // 默认文本编码，默认值 "UTF-8"
//        settings.setDefaultTextEncodingName("UTF-8");
//        settings.setDefaultFontSize(16);        // 默认文字尺寸，默认值16，取值范围1-72
//        settings.setDefaultFixedFontSize(16);   // 默认等宽字体尺寸，默认值16
//        settings.setMinimumFontSize(8);         // 最小文字尺寸，默认值 8
//        settings.setMinimumLogicalFontSize(8);  // 最小文字逻辑尺寸，默认值 8
//        settings.setTextZoom(100);              // 文字缩放百分比，默认值 100
//        // 字体
//        settings.setStandardFontFamily("sans-serif");   // 标准字体，默认值 "sans-serif"
//        settings.setSerifFontFamily("serif");           // 衬线字体，默认值 "serif"
//        settings.setSansSerifFontFamily("sans-serif");  // 无衬线字体，默认值 "sans-serif"
//        settings.setFixedFontFamily("monospace");       // 等宽字体，默认值 "monospace"
//        settings.setCursiveFontFamily("cursive");       // 手写体(草书)，默认值 "cursive"
//        settings.setFantasyFontFamily("fantasy");       // 幻想体，默认值 "fantasy"

    webView.getSettings().setJavaScriptEnabled(true);
    webView.getSettings().setDomStorageEnabled(true);
    webView.setWebChromeClient(webChromeClient);
    // webView.setWebViewClient(new WebViewClient());
    webView.loadUrl("https://www.baidu.com/");
```