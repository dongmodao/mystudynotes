### 点击事件

OnClick
对于 View 使用该事件，不能正确获得该 View 被点击的坐标
OnTouch
接受两个参数，View, MotionEvent。通过 Event.getX() 可以获得该坐标。进行相应操作即可。
``` java
    @Override
    public boolean onTouch(View v, MotionEvent event) {
        switch (event.getAction()){
            case MotionEvent.ACTION_DOWN:
                firstX = event.getX();
                return true;
            case MotionEvent.ACTION_UP:
                float secondX = event.getX();
                if(secondX - firstX <= 10)
                    index++;
                if(secondX - firstX >= 10)
                    index--;
                if(index < 0)
                    index = 0;
                loadContent(url);
                break;
            default:
                break;
        }
        return true;
    }
```