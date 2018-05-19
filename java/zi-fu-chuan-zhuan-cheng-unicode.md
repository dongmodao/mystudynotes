#### 字符串转 Unicode

``` java
    public static String string2Unicode(String string) {
        StringBuffer unicode = new StringBuffer();
        for (int i = 0; i < string.length(); i++) {
            // 取出每一个字符
            char c = string.charAt(i);
            // 转换为unicode
            if(c<127){
                unicode.append(c);    // 不转换字符，如需转则删除
            }else{
                unicode.append("\\u" + Integer.toHexString(c));
            }

        }
        return unicode.toString();
    }
```