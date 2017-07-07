## Fragment

**需要准备的东西**
 + Fragment 对应的布局文件
 + 继承自 Fragment 的新的碎片类。NewFragment。
 + 在类中的 onCreateView 使用 inflater.inflate() 方法使布局与碎片类联系起来。
 + 在使用 fragment 的布局文件中使用 name 属性指明使用的碎片类型。引入新建的 Fragment。
 
## 动态添加 Fragment

1. 创建待添加的碎片实例。
2. 获取 FragmentManager，在活动中可以直接调用 getSupportFragmentManager() 方法得到。
3. 开启一个事务，通过调用 beginTransaction() 方法开启。
4. 向容器内添加或者替换碎片，replace() 方法，传入容器的 id 和待添加的碎片实例。
5. 提交事务，使用 commit() 方法来完成。

``` java
FragmentManager fragmentManager = getSupportFragmentManager();
FragmentTransaction transaction = fragmentManager.beginTran();
transaction.replace(R.id.myfragment, newfragmentinstance);
transaction.commit();

```

