## SharedPreferences 存储

使用键值对的方式来存储数据，保存时需要提供一个键，读取是根据键获取数据。可以保存不同数据类型，什么类型保存的，都出来就是什么类型的数据。

### 存储方法

首先需要获取 SharedPreferences 对象。三种方法：

 1. Context 类中的 getSharedPreferences() 方法。
  接受两个参数，文件名称（在应用的 shared_prefs/ 目录下），操作模式（目前只有 MODE_PRIVATE 方式可选（Android 6.0 以上版本），可直接传入 0，表示只有当前应用能够对这个文件进行读写）。
  
 2. Activity 类中的 getPreferences() 方法。
  同上，但只接受一个参数，即操作模式。文件名默认就是当前活动的类名。 
   
 3. PreferenceManager 类中的 getDefaultSharedPreferences() 方法。
 静态方法，接收一个 Context 参数，自动使用当前应用程序的报名作为前缀命名 SharedPreferences 文件。
 
得到 SharedPreferences 对象之后，分 3 步向其中存储数据。
 
 1. 调用 ShardPreferences 对象的 edit() 方法获取一个 SharedPreferences.Editor 对象。
 2. 使用对象的方法向这个 SharedPreferences.Editor 对象中添加数据，putBoole(), putString(), etc.
 3. 调用 apply() 方法提交数据，完成存储操作。
 
 在 Activity 中调用：
 ``` java
                 SharedPreferences.Editor editor = getSharedPreferences("data", MODE_PRIVATE).edit();
                editor.putString("name", "dongmodao");
                editor.putInt("age", 21);
                editor.putBoolean("married", false);
                editor.apply();
```

### 读取数据

获取 SharedPreferences 对象（方法同上），调用 get*() 方法，getInt(String key, 0) 之类的方法即可。方法接受两个参数，键以及默认值（找不到对应值时使用）。

在 Activity 中调用：
``` java
                SharedPreferences pref = getSharedPreferences("data", MODE_PRIVATE);
                String name = pref.getString("name", "");
                int age = pref.getInt("age", 0);
                boolean married = pref.getBoolean("married", false);
```

#### 本质

存储过程：获取一个 SharedPreferences.Editor 对象（获取方式如上），使用该对象的``.putXxx``方法可加入不同类型的数据，使用``.apply()``方法提交即可。

读取过程：获取一个 SharedPreferences 对象，使用``.getXxx``方法获取对应类型的数据即可。