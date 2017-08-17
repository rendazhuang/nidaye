##    Java 常用类

***

- ArrayList 
  - ArrayList：长度可变的数组，在内存中分配连续的空间，可动态维护长度的集合。
- Arrays
  - 包含用来操作数组的各种方法，如排序和搜索
- Calendar
  - 该类是一个抽象类， 可以使用GregorianCalendar类将其实例化，也可以通过getInstannce()方法来创建对象。用来处理日期和时间
- Class
  - Class类的实例表示正在运行的Java应用程序的类和接口，没有公共构造方法
- Collection
  - 存储一组不唯一，无序的对象
- Date
  - 用一个long类型的值来表示一个指定的时刻。
- DateFormat
  - 将一个日期按照指定的风格进行格式化.
- Error
  - 通常出现重大问题如：运行的类不存在或者内存溢出等；不编写针对代码对其处理。
- Exception
  - 在运行时函数出现的一些情况，可以通过try、catch、finally。
- HashMap
  - 无序存放的，是新的操作类，key不允许重复。
- HashSet
  - HashSet是Set接口的一个子类，主要的特点是：里面不能存放重复元素，而且是采用散列的存储方式，所以是没有顺序的。
- Iterator
  - 用于遍历集合类的标准访问方法

- List
  - 可以进行双向输出，通过索引获取对象，存储一组不唯一，有序（插入顺序）的对象
- Linked List
  - LinkedList采用链表存储方式，在集合任何位置（头部、中间、尾部）添加、获取、删除对象。
- Math
  - 执行基本数学运算的方法。
- Matcher
  - 验证是否符合其规范。
- Number
  -  BigDecimal、BigInteger、Byte、Double、Float、Integer、Long 和 Short 类的超类。 Number的子类必须提供将表示的数值转换为 byte、double、float、int、long 和 short 的方法。 
- Object
  - 类Object是类层次结构的根类
- Pattern
  - Pattern类的主要作用是进行正则规范（如之前的“[0-9]”就属于正则规范）的编写
- Random
  - 产生int、long、float、double等类型的随机数。
- String
  - String类位于java.lang包中，具有丰富的方法  计算字符串的长度、比较字符串、连接字符串、提取  字符串
- Set
  - 不能加入重复的元素，存储一组唯一，无序的对象。
- StringBuffer
  - 线程安全的可变字符序列
- StringBuilder
  - 线程非安全的可变字符序列
- System
  - 系统级的属性和控制方法都放置在该类的内部。该类的构造方法是private的,无法实例化该类，其内部的成员变量和方法都是静态的
- Scanner
  - 用于扫描输入文本

- SimpleDateFormat
  - 是一个以国别敏感的方式格式化和分析数据的具体类.主要功能是完成日期显示格式的转换。
- Thread
  - 专门用来创建线程
- TreeSet
  - 对输入的数据进行有序排列
- Vector
  - List子类，实现可增长的对象数组
- Void
  - Void 类是一个不可实例化的占位符类，它持有对表示 Java 关键字 void 的 Class 对象的引用

---

## 基本数据类型

- Boolean
  - Boolean是基本数据类型的包装类，Boolean类在对象中包装了一个基本类型boolean的值。
- Byte
  - Byte是基本数据类型的包装类，Byte类在对象中包装了一个基本类型byte的值。
- Character
  - Character 类在对象中包装一个基本类型 char 的值，用于对单个字符进行操作
- Double
  - Double是基本数据类型的包装类，Double类在对象中包装了一个基本类型double的值。
- Float
  - Float是基本数据类型的包装类，Float类在对象中包装了一个基本类型float的值。
- Long
  - Long是基本数据类型的包装类，Long类在对象中包装了一个基本类型long的值。
- Integer
  - Integer是基本数据类型的包装类，Integer类在对象中包装了一个基本类型int的值。每个Integer类型的对象包含一个int类型的字段。
- Short
  - Short是基本数据类型的包装类，Short类在对象中包装了一个基本类型short的值。

---

### 数据结构中的映射

- Map
  - 用于存储健值对，根据键得到值，因此不允许键重复，但允许值重复

- HashTable
  - 根据键的hashCode值存储数据，根据键可以直接获取它的值

- LinkedHushMap
  - HashMap的一个子类，保存了记录的插入顺序

- TreeMap
  - 能够把它保存的记录根据键排序,默认是按键值的升序排序，也可以指定排序的比较器





---

