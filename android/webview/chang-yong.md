## 常用

#### 监听案件点击次数不同实现（含后退的实现）

区别按键的单双击，同时照顾，但在一个时间间隔内，可执行另一种方案。
参考[Android 监听返回键退出程序的两种实现](http://www.cnblogs.com/recock/p/4284429.html)，摘取我今天使用部分的代码，防止原帖删除。

``` java
    /**
     * 菜单、返回键响应
     */
    @Override
    public boolean onKeyDown(int keyCode, KeyEvent event) {
        // TODO Auto-generated method stub
        if(keyCode == KeyEvent.KEYCODE_BACK)
        {  
            exitBy2Click();        // 调用双击退出函数
        }
        return false;
    }
    /**
     * 双击退出函数
     */
    private static Boolean isExit = false;

    private void exitBy2Click() {
        Timer tExit = null;
        if (isExit == false) {
            isExit = true; // 准备退出
            Toast.makeText(this, "再按一次退出程序", Toast.LENGTH_SHORT).show();
            tExit = new Timer();
            tExit.schedule(new TimerTask() {
                @Override
                public void run() {
                    isExit = false; // 取消退出
                }
            }, 2000); // 如果2秒钟内没有按下返回键，则启动定时器取消掉刚才执行的任务

        } else {
            finish();
            System.exit(0);
        }
    }

```
#### WebView 支持缩放

``` java
     webView.getSettings().setSupportZoom(true);
     webView.getSettings().setBuiltInZoomControls(true);// 实现触摸 WebView 放大缩小
     webView.getSettings().setUseWideViewPort(true);// 双击实现放大缩小
```

