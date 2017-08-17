
Object
==============

getClass():返回 类  类名

```
//Lianxi是方法名
1.getClass.getName()//表示的是支出类名
Lianxi lia=new Lianxi("小明");
		System.out.println(lia.getClass());
String类型  toString():返回该对象的字符串表示
boolean类型  equals(s)：只是其让某个对象是否与此对象相等
ing类型     hashCode()：返回该对象的哈希码值
```

hashCode():对同一对象的hashCode()值肯定相同

```
Lianxi lai=new Lianxi("小明");
System.out.println(lia.hashCode());
```


System
================

1.System 类提供了系统级 的很多属性和控制方法，位于java.lang包

2.System类是final类不能被实例化，所有方法和属性都是静态的，可以直接调用

arraycopy方法：arraycopy(要复制的数组,要从复制的数组的第几个开始,复制到哪,复制到的数组第几个开始,复制长度)其他的是0代替

```
int []arr1={1,2,3};
int []arr2=new int[5];
System.arraycopy(arr1,0,arr2,1,2);
//打印
for(int i=0;i<arr2.length;i++){
  System.out.print(arr2[i]);
}
这个结果是01200
```

gc方法：用于垃圾回收


Random
===================

1.Random类用于生成伪随机数，位于java.util包

2.Random对象的生成

```
Random ran =new Random();//普通的
Random ran =new Random(100);//使用指定的种子数构建Random对象，相同的种子产生的随机数序列完全相同
```

常用方法

```
1.int返回值;
Random ran=new Random();
int a=ran.nextInt(10);//表示随机取出一个不大于10的数
double b=ran.nextDouble();//表示随机生成一个double介于0-1之间
```


Math
==============

1.Math类提供了执行基本数学的运算的方法，位于java.lang包。

2.Math类是final类不能被实例化，所有方法和属性都是静态的，可以直接调用

3.返回值都是double类型。

方法有

``` 
pow (double a,double b) a的b次幂  double o=Math.pow(a,b);
sqrt(double a)			a的平方根 double o=Math.sqrt(a);
ceil(double a)			a向上取整 double o=Math.ceil(a);//不管a有多少小数都不要,整数加1
floor(double a)			a向下取整 double o=Math.floor(a);//不管a有多少小数都不要,整数不变
round(double a)			a四舍五入 double o=Math.round(a);//四舍五入，最后为整数
abs(double a)			a的绝对值 double o=Math.abs(a);
random()				0-1之间的随机double值 double o=Math.random();
max(double a,double b)	a,b中的最大值	double o=Math.max(a,b);//如果a比b大打印a
min(double a,double b)	a,b中的最小值   double o=Math.min(a,b);//如果a比b小打印a
```


Arrays
===============

1.Arrays类提供了一系列操作数组的方法，位于java.util包中

```
1.void返回值  sort(int[ a]):升序Arrays.sort();
int[] arr=new int[]{10,12,45,12,25,14};
	//只排序前俩个
		Arrays.sort(arr,0,2);
	//排序全部
	Arrays.sort(arr);
	遍历：
		for(int i:arr){
			System.out.println(i);
		}
2.int返回值  binarySearch(int[] a,int key)二分搜索,搜索指定数字或汉字的位置
Arrays.binarySearch(arr,45);//搜索的是arr中45的位置
3.String类型  toString(int[]array) 返回数组的字符串形式
System.out.println(Arrays.toString(arr));
```


包装类
==================

Integer和八种数据类型之间的转换

```
与int之间的转换，其余类似
		int a=10;
		Integer in=new Integer(100);
		//将int类型转换为Integer类型
		Integer in1=new Integer(a);
		//将Integer类型转换为int 类型
		int a1=in.intValue();
```

Integer类内部的常用方法

1.将数字字符转换为int数值        parseInt

```
		String str="123456";
		int a= Integer.parseInt(str);
		
		  //将字符串”120”按照十进制转换为int，则结果为120

         int n = Integer.parseInt(“120”,10);

         //将字符串”12”按照十六进制转换为int，则结果为18

         int n = Integer.parseInt(“12”,16);

         //将字符串”ff”按照十六进制转换为int，则结果为255

         int n = Integer.parseInt(“ff”,16)
```

2.将int类型转换为对应的String类型         toString

```
int q=100;
String str=Integer.toString(q);
    //int类型会自动转换为Integer类型

                   int m = 12;

                   Integer in = m;

                   //Integer类型会自动转换为int类型

                   int n = in
```

```
字符常用操作  Character 

Character(char c) 使用char构造对象
 
boolean类型 isUpperCase(char c) 判断字符是否是大写 Character.isDigit(in) in是否是数字

boolean类型 isLowerCase(char c) 判断字符是否是小写

boolean类型 isDigit(char c) 判断字符是否是数字

char toUpperCase(char c) 字符转大写

char toLowerCase(char c) 字符转小写

```



装箱  valueOf  (int i)

拆箱  int Value()

```
	1.int 装箱的到Integer；
		int str="123456";
		int a=Integer.valueOf(str);
		Integer i=100;//自动装箱
2.自动拆箱(unboxing)，也就是将对象中的基本数据从对象中自动取出。如下可实现自动拆箱：
1 Integer i = 10; //装箱
2  int t = i; //拆箱，实际上执行了 int t = i.intValue()
```

获取一个时间表System.currentTimeMillis();

```
long time=System.currentTimeMillis();接收这个时间
```

dete日期

1.在java.util包中

```
（无参构造）Date date=new Date(0);//构建1970年的当前时间
System.out.println(date);//打印出的结果是当前的年月份及时间
有参构造
Date date=new Date(123456L);//使用指定时间毫秒数构造日期对象
		Date date = new Date(); 
		System.out.println(date.getTime());
		System.out.println(date.getYear());
		System.out.println(date.getMonth());
		System.out.println(date.getDay());
```


Calendar
===============

1.java提供Calendar类能更好的处理日期，Calendar类也在java.until中

2.Calendar是抽象类，不能通过new来创建对象，可以通过getInstance方法创建对象（Calendar cal=Calendar.genInstance();）

3.获取各种时间数据

```
Calendar cal=Calendar.getInstance();//创建对象
		Calendar cal=Calendar.getInstance();
		System.out.println(cal.get(Calendar.YEAR));//获取今年的年份
		System.out.println(cal.get(Calendar.MONTH));//获取月份
		System.out.println(cal.get(Calendar.DAY_OF_MONTH));//获取本月的第几天
		System.out.println(cal.get(Calendar.HOUR));//获取当前的小时
		System.out.println(cal.get(Calendar.MINUTE));//获取当前的分钟
		System.out.println(cal.get(Calendar.SECOND));//获取当前时间的 秒
		System.out.println(cal.get(Calendar.DAY_OF_WEEK));//获取当前周的第几天
```

Calendar日历

```
Calendar cal=Calendar.getInstance();
cal.set(Calendar,YEAR,-1);//当前年份减1
cal.add(Calendar.YEAR,-1);当前年份减1
```

DateFormat类

1.DateFormat类位于java.text包

2.DateFormat是为抽象类，有多种方法创建对象

3.使用format()方法格式化时间

```
		Date date = new Date(); 
		DateFormat df = DateFormat.getDateInstance();
		System.out.println(df.format(date));//打印的是当前的日期（年、月、日）
		DateFormat df1 = DateFormat.getTimeInstance();
		System.out.println(df1.format(date));//打印的是当前的时间（时间，分钟，秒）
		DateFormat df2 = DateFormat.getDateTimeInstance(); 
		 System.out.println(df2.format(date));//打印的是当前的日期和时间
```

SimpleDateFormat

1.SimpleDateFormat是DateFomat的子类

2.可通过字符串格式参数创建SimpleDateFormat对象

```
年:yyyy|yy 
月:MM
年中的 天数:DDD
月份中的 天数: dd
年中的 周数:W(小写)
月份中的 周数:W(大写)
小时 (24制)：HH
小时 (12制):hh 
分 :mm
秒 :ss
毫秒:SS  
```

```
Date date = new Date();
SimpleDateFormat sdf1 = new SimpleDateFormat("yyyy-MM-dd"); //可根据需求自定义
SimpleDateFormat sdf2 = new SimpleDateFormat("hh:mm:ss");
SimpleDateFormat sdf3 = new SimpleDateFormat("yyyy年MM月dd日HH时mm分ss秒SSS毫秒"); String str1 = sdf1.format(date);//字符串样式接收
String str2 = sdf2.format(date); （format类，传入date）
String str3 = sdf3.format(date);
System.out.println(str1);
System.out.println(str2);
System.out.println(str3)
```

