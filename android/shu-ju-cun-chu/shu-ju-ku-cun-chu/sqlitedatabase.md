## SQLiteDatabase

Android 系统内置了轻量级 SQLite 关系型数据库，可以使用标准的 SQL 语法，遵循数据库的 ACID 事务。（A：原子性「Aotomicaly」 C：一致性性「Consistency」 I：隔离性「Isolation」 D：持久性「Durability」）。

1. 创建数据库

 Android 提供了一个管理数据库的抽象 SQLiteOpenHelper 帮助类，使用时需要自己创建一个帮助类去继承它，要实现 onCreate() 和 onUpgrade() 两个抽象方法，在这两个方法中实现创建和升级数据库的逻辑。 
 SQLiteOpenHelper 中还有两个重要的实例方法：getReadableDatabase() 和 getWritableDatabase()。这两个方法是用于创建或打开一个现有的数据库（不存在则新建），返回一个可对数据库进行读写操作的对象。注意当不可以写入是前者只读打开，后者出现异常。
 SQLiteOpenHelper 有连个两个构造函数，一般使用参数少的那一个。传入 4 个参数，Context、数据库名、查询数据库的时候返回的自定义 Cursor（一般传 null）、数据库的版本号。数据保存在应用的/databases/目录下。
 