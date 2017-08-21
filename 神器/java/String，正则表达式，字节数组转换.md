

equals

```
a.equals(b)：比较a和b俩字符串是否相等。

a.qwualsIgnorCase(b):比较a和b俩字符串不区分的大小写是否相等。

startWith(String类型):判断是否一指定字符串开头

endWith():判断水否以指定字符串结束

isEmpty():判断字符串长度是否为0
```

```
String str="HellWotd";

length:(str长度)：System.out.println(str.length);

charAt():(获取str的第二个字符)System.out.println(str.charAt(1));

indexOf():(str中第一个o出现的位置)System.out.println(str.indexOf("o"));

lastIndexOf():(str中最后一个o出现的位置)System.out.println(str.lastIndexOf("o"));

substring(a,b):(截取str[5-9的字符串])System.out.println(str.substring(5,9));
```

增强遍历

```
Person []pers={1,2};
1.for(要接收的类型及名字:传递){
  
}
2.实例:for(Person p:pers){
  System.out.println(p);
}
```

正则表达式

```
split:分离
String str="abcdasajHFJKJB";


String []s=str.split("a");遇到a之后就成拆分，并把a给去掉

for(String st:s){
  System.out.println(st);
}结果：bcd
	   s
	   jHFJKJB
	   
	   
1.replace:替换，只能去替换某一个字符
2.replaceAll:
3.System.out.println(str.replace("把什么,替换成什么"));后面的替换掉前面的
```

StringBuffer:追加

```
StringBuffer sb=new StringBuffer(10);10是容量，也可以在括号里直接写入值，不写容量，默认16个
sb.append("aaa");追加的aaa;append关键字
sb.append("bbb");追加的bbb
System.out.println(sb.toString());打印
```


```
String[] split(String str) 将字符串拆分为给定正则表达式的匹配项

String replace(String1 old, String new) 用新字符串替换旧字符串

String replaceAll(String old, String new) 用新字符串替换所有旧字符串

String trim() 去掉两端空格

int compareTo(String str) 按字典顺序比较两个字符串

int compareToIgnoreCase(String str) 忽略大小写按字典顺序比较两个字符串
```

```
删除功能
StringBuffer deleteCharAt(int index) 删除指定位置的字符

StringBuffer delete(int start,int end) 删除指定区间的字符

其他功能
StringBuffer replace(int start,int end,String str) 替换指定区间为新字符串

String substring(int start) 截取从指定位置到末尾的字符串

String subString(int start,int end) 截取指定区间的字符串

StringBuffer append(String str) 末尾追加字符串

StringBuffer insert(int offset,String str) 指定位置插入字符
```


正则表达式
======================

```
一.正则元字符：
1.用于匹配特定字符的元字符    []
[]:[abc]匹配a，b，c，中的任意一个；[^abc]匹配任意一个不是a,b,c的字符
[a-zA-Z]匹配a到z，或者A到Z的任意一个字符

2.常见的字符集  .;\d;\w
.   :匹配任意字符
\d  :匹配数字，相当于[0-9];\D匹配非数字，[^0-9]
\w匹配单词字符，相当于[a-zA-Z_0-9];\W匹配非单词字符；相当于[^\w]

3.用于限定字符数量的元字符   {}
{n}	恰好出现n次
{n,m}至少n次，至多m次;
{n,}至少n次，无上限
?:表示0次或1次;
*:表示0次或多次;
+:表示一次或多次;

4.用于约束字符边界的元字符
^:^abc;表示以abc开头的
$:abc$;表示以abc结尾的
\b:\babc;表示离边界最近的abc

5.逻辑运算   |
A|B:表示A或者B;
(ab){2}:表示连续出现2个ab的

二.String类中的正则方法
1.publuic boolean matches(String regex);//传入String类型的正则表达式
2.public String replaceAll(String regex,String replacement（用什么替换前面的）);//替换
3.public String[] split(String regex);//分割
String str="abc12wed333ki";
String[]str1=str.split("\\d+");//分割[1-9]至少有一个
//遍历
for(String str2:str1){
  System.out.println(str2);
}
三.Pattern和Matcher
1.Pattern用来编译一个正则表达式
2.Matcher用来执行正则表达式的匹配操作

```

字节数组转换

```
String(String original) 字符串常量转换成字符串

String(byte[] bytes) 字节数组转成字符串

String(byte[] bytes,int offset,int length) 字节数组的一部分转成字符串

String(char[] value) 字符数组转成字符串

String(char[] value,int offset,int count) 字符数组的一部分转成字符串
```

String 转换

```
public static void main(String[]args){
  String str="sdfhjbnajshd";
  byte[]bytes=str.getBytes();(str转换成byte类型)****getBytes****
  
  char[]chars=str.toCharArray();(str转换成char类型)****toCharArray***(一个整得单词（Holle分开H,o,l,l,e)
  
  String str1=str.valueOf('中');(把char（中）类型转换为String类型);****valueOf()可以转任何类型***
  
  String str2=str.toLowerCase();(把str转为小写)******toLowerCase()********
  
  String str3=str.toUpperCase();(把str转为大写)*********toUpperCase()******
  
  String str4=str.concat("123456");(把str和123456连接)**********concat(String str)****
  }
```


异常
================

关键字：try;  catch;  finally;   throws;  throw

System.out.println(e.getMessage());