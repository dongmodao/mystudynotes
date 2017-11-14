## 小技巧

1. 获取和设置控件宽高、屏幕的宽高
``` java
        //获取屏幕的宽高
        DisplayMetrics dm = getResources().getDisplayMetrics();
        int width = dm.widthPixels;
        int height = dm.heightPixels;
        
        //设置控件的宽高        mainWeatherContainer 是一个控件名字
        LinearLayout.LayoutParams params= (LinearLayout.LayoutParams)mainWeatherContainer.getLayoutParams();
        //获取当前控件的布局对象
        params.height=height;//设置当前控件布局的高度
        mainWeatherContainer.setLayoutParams(params);//将设置好的布局参数应用到控件中
        //LinearLayout.LayoutParams 不一定是 LinearLayout，可视为控件的父布局，并不一定是实际上的布局，反正测试不对的时候看一下 Logcat 中的提示就行了。
```