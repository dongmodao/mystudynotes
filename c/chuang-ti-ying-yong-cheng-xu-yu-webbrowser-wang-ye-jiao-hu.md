# 网页脚本执行程序函数

在程序中定义一个方法如下：

``` csharp
 public void GetLogLat(string log, string lat)
        {
            tbxLog.Text = log;
            tbxLat.Text = lat;
        }
```

同时在窗体定义可见性如下：

``` csharp
 [System.Runtime.InteropServices.ComVisible(true)]
    public partial class Mainfrm : Form
    {...}
```

将脚本对象设置为窗体：

``` csharp
webBrowser.ObjectForScripting = this;
```



在网页文件中定义脚本：

``` javascript
	function showInfo(e){
		external.GetLogLat(e.point.lng, e.point.lat);
	}
```

使用了 external 关键字，调用外部的 GetLogLat() 方法，则当脚本得到运行时，则相当于调用了程序的 GetLogLat() 函数。