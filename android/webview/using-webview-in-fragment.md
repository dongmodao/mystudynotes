## Using WebView in Fragment

在新建的 NewFragment 类型（继承自 Fragment）中添加如下代码：
``` java
 @Override
public View onCreateView(LayoutInflater inflater, ViewGroup container,
                         Bundle savedInstanceState) {

    View v=inflater.inflate(R.layout.fragment_bugtracker, container, false);
    mWebView = (WebView) v.findViewById(R.id.webview);
    mWebView.loadUrl("https://google.com");

    // Enable Javascript
    WebSettings webSettings = mWebView.getSettings();
    webSettings.setJavaScriptEnabled(true);

    // Force links and redirects to open in the WebView instead of in a browser
    mWebView.setWebViewClient(new WebViewClient());

    return v;
}
```