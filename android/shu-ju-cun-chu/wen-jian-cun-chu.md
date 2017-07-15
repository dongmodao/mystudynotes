## 文件存储

Android 中最基本的数据存储方案。不对存储的内容进行任何多余的格式化处理，存的什么样子就是什么样子。一般存储简单的文本数据或二进制数据。当然，可以定义自己的格式规范来读写。

### 保存方法

Context 类中提供一个 openFileOutput() 方法，可将数据保存到指定文件之中。保存路径为 /data/data/< packagename >/files/ 目录中。接收两个参数，第一个是文件名，第二个是操作模式，MODE_PRIVATE 和 MODE_APPEND 两种。前者遇到同名文件时覆盖，后者则在后面加入。

openFileOutput() 方法返回一个 FileOutputStream 对象。接着就可以按照 Java 流的方式把数据写到文件中。

``` java
    private void Save(String inputText) {
        FileOutputStream out = null;
        BufferedWriter writer = null;
        try{
            out = openFileOutput("data", Context.MODE_PRIVATE);
            writer = new BufferedWriter(new OutputStreamWriter(out));
            writer.write(inputText);
        }catch (IOException e){
            e.printStackTrace();
        }finally {
            try{
                if(writer != null){
                    writer.close();
                }
            }catch (IOException e){
                e.printStackTrace();
            }
        }
    }
```

学习使用的是郭神的《第一行代码》第六章。在这个过程中可能会遇到很多问题，一些问题可以参照[Android Device Monitor 文件管理的常见问题](http://www.jianshu.com/p/d8a9a2918c61)解决（在我自己遇到的问题里，亲测可用）。
![](/assets/adbshellcmd.png)

### 读取方法

使用 Context 提供的方法 openFileInput() 从文件中读取数据。接受文件名作为唯一参数。从该应用的目录下加载文件，返回一个 FileInputStream 对象，随后用 Java 方式读取。

``` java
    private String load() {
        FileInputStream in = null;
        BufferedReader reader = null;
        StringBuilder content = new StringBuilder();
        try{
            in = openFileInput("data");
            reader = new BufferedReader(new InputStreamReader(in));
            String line = "";
            while ((line = reader.readLine()) != null){
                content.append(line);
            }
        }catch (IOException e){
            e.printStackTrace();
        }finally {
            if(reader != null){
                try{
                    reader.close();
                }catch (IOException e){
                    e.printStackTrace();
                }
            }
        }
        return content.toString();
    }
```
