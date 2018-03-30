## 弹出全局窗口
在使用 Android 的过程中，有时候需要在任意一个界面弹出一个提示窗体，实现的方法不少，但是随着 Android 的版本变化，这些方法有的不适用了，我也是在 StackOverflow 上面才知道有些参数是不能使用了的。具体可以看 [Android: Unable to add window. Permission denied for this window type](https://stackoverflow.com/questions/32224452/android-unable-to-add-window-permission-denied-for-this-window-type) 这个地址，看看各位大佬的讨论就知道了。

1. 使用 AlertDialog.Show() 来实现

  在主线程中使用如下代码，不需添加多余权限：
  ``` java
    AlertDialog.Builder dialog = new AlertDialog.Builder(MainActivity.this);
    dialog.setTitle("测试全局弹框");
    dialog.setMessage("正常弹出，你看到我了");
    AlertDialog alertDialog = dialog.create();
    alertDialog.getWindow().setType(LayoutParams.TYPE_TOAST);
    alertDialog.show();
  ```
  就可以正确在任意界面中显示窗口了。权限 ``SYSTEM_ALERT_WINDOW`` 在比较高的版本已经不适用了。选择什么样的参数，和 API 版本有关。
  <center>
  <img src="/assets/shotcut1.png" heigth="480" width="270" align = center/>
  </center>

2. 使用 WindowManager 添加和移除

 使用 WindowManager 管理 View，添加和删除 View，使用 WindowManager.LayoutParams 来管理 View 的显示类型。主要代码如下：
 ``` java
    // Activity 中的代码
    final WindowManager manager = (WindowManager) MainActivity.this.getSystemService(Context.WINDOW_SERVICE);
    WindowManager.LayoutParams para = new WindowManager.LayoutParams();
    para.height = -1;
    para.width = -1;
    para.format = 1;
    para.flags = LayoutParams.FLAG_FULLSCREEN | LayoutParams.FLAG_LAYOUT_IN_SCREEN;
    para.type = LayoutParams.TYPE_TOAST;
    final View mView = LayoutInflater.from(MainActivity.this).inflate(
            R.layout.dialog, null);
    manager.addView(mView, para);
    mView.setOnClickListener(new View.OnClickListener() {
        @Override
        public void onClick(View view) {
            manager.removeView(mView);
        }
    });
 ```
  R.layout.dialog 的布局代码如下：
  
  ``` xml
  <?xml version="1.0" encoding="utf-8"?>
 <android.support.constraint.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    xmlns:app="http://schemas.android.com/apk/res-auto">

    <ImageView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:src="@drawable/ic_test"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintLeft_toLeftOf="parent"
        app:layout_constraintRight_toRightOf="parent"
        app:layout_constraintTop_toTopOf="parent"/>

 </android.support.constraint.ConstraintLayout>
  ```
  
  <center>
  <img src="/assets/shotcut.png" heigth="480" width="270" align = center/>
  </center>
  
  参考[android 全局对话框（不依赖具体activity）](https://blog.csdn.net/lxlmycsdnfree/article/details/73796543)，[Android: Unable to add window. Permission denied for this window type](https://stackoverflow.com/questions/32224452/android-unable-to-add-window-permission-denied-for-this-window-type)。