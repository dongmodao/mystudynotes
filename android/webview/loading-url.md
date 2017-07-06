## Loading Url

using java code as follow:
``` java
    mWebView = (WebView) findViewById(R.id.webview);
    mWebView.loadUrl("https://google.com");

    // Enable Javascript
    WebSettings webSettings = mWebView.getSettings();
    webSettings.setJavaScriptEnabled(true);

    // Force links and redirects to open in the WebView instead of in a browser
    mWebView.setWebViewClient(new WebViewClient());
```