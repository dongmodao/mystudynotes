# 窗体与顺序

## 关于窗体查找

为了避免打开重复的窗体，可以对窗体进行存在检验，如果存在则使用已经存在的窗体，不存在则是返回 ``null``，让用户根据结果来使用。

``` csharp
        private POIDetailForm GetPOIDetailForm()
        {
            POIDetailForm tempPOIDetailForm = null;
            foreach (Form sForm in this.OwnedForms)
            {
                if (sForm.GetType() == typeof(POIDetailForm))
                {
                    tempPOIDetailForm = (POIDetailForm)sForm;
                    return tempPOIDetailForm;
                }
            }
            return tempPOIDetailForm;
        }
```

上述方法是用于检验子窗体中是否存在，即显示时使用 ``.Show(this)`` 的情况。此时，子窗体总是会遮盖父窗体，只能移动位置使其不被遮盖。如果不用父子窗体打开，而是用 ``.Show()`` 打开，则当其可以主窗体可以移动到打开的窗体的前面。上述在进行检验时就需要使用如下语句判断：

``` csharp
foreach (Form sForm in Application.OpenForms)
```

即从程序打开的窗体中进行寻找，使用 ``this.OwnedForms`` 即使是存在该窗体也找不到，因为打开的时候用的不是 ``.Show(this)``。

## 顺序

一般使用比较多的有 ``.BringToFront()`` 以及 ``.SendToBack()``，但是，这个好像只对 ``.Show()`` 有用，以为 ``.Show(this)`` 没有解决父子窗体的问题。所以根据需要再判断使用哪一种 ``Show()`` 方法。

