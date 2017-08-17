page

```
作用：用于定义JSP页面的各种属性
属性值：
1.1.<%@page import ="java.util.Date.java.util.List"%>//
2.<%@page import ="java.util.Date"%>
3.<%@page import ="java.util.List"%>
JSP会自动导入以下的包：
import java.lang.*;
import javax.servlet.*;
import java.servlet.http.*;
import javax.servlet.jsp.*;
1.2. session :
是否会自动创建session对象，默认值为true   <%@page session="true"%>
1.3.  buffer: 输出缓存数据的缓存大小，默认为8kb
1.4    errorPage  :如果页面出现错误，则跳转到指定的资源    <%@page errorPage="指定的资源"%>
1.5  isErrorPage:是否创建throwable对象，默认值为false
1.6   pageEncoding: 告诉JSP引擎要翻译的文件使用的编码。 <%@page session="true" pageEncoding=UTF-8%>
1.7   isELIgnored: 是否支持EL表达式。 默认是false
```

2.  include    把其他资源放到当前页面

   ```
   静态包含
   <%@include file="要引入的资源"%>
   动态包含
   <jsp:include page="要引入的资源"></jsp:include>

   区别：翻译的时间段不同
   静态在翻译是就把俩个文件合并，动态翻译时不会合并文件，当代码执行include时，才包含另一个文件的内容


   推荐使用静态
   ```

   3.  taglib    在JSP页面中导入JSTL标签库，替换JSP中的java代码段

      ```
      <%@taglib uri="http://java.sun.com/jsp/jstl/core" prefix="c"%>
      ```


jsp的6个动作
==============

```
<jsp:include> 动态包含   <jsp:include page="2.jsp"></jsp:include>  当前页面包含2.jsp页面
<jsp:forward>请求转发
<jsp:param>  设置请求转发的请求参数
	<jsp:forward page="error.jsp">
		<jsp:param value="" name=""/>
		</jsp:forward>
	转发到error.jsp页面，参数是value的值  name获取的时候用
	
<jsp:useBean>  创建一个对象
<jsp:useBean id="stu" scope="session" class="模板类地址"></jsp:useBean>   创建一个对象为stu，只在一次会话请求中有效，创建的地址为模板类地址
scope 一次会话，class  地址

<jsp:setPriperty>  给指定的对象属性赋值
<jsp:setPriperty property="name" name="stu" value="zhangsan"/> 给对象为stu的name属性赋值，值为zhangsan
property属性  name 对象简称   value 属性值  

<jsp:getPriperty>   取出指定对象的属性值
<jsp:getProperty property="name" name="stu"/>
${stu}  取出name值
```


jsp中的9个内置对象 :指在JSP的<%=%>和<%%>中可以直接使用的对象
================

```
1.request
2.response
3.session
4.application
5.exception
6.page
7.config
8.out
9.pageContext
```

```
pageContext()
1、本身也是一个域对象：它可以操作其它三个域对象（request session application）的数据
void setAttribute(String name,Object o);
Object getAttribute(String name);
void removeAttribute(String name);
操作其它域对象的方法
void setAttribute(String name,Object o，int Scope);
Object getAttribute(String name,int Scope);
void removeAttribute(String name,int Scope);
scpoe的值：
PageContext.PAGE_SCOPE 
PageContext.REQUEST_SCOPE 
PageContext.SESSION_SCOPE 
PageContext.APPLICATION_SCOPE

findAttribute(String name); 自动从page request session application依次查找，找到了就取值，结束查找。


2、它可以创建其它的8个隐式对象
在普通类中可以通过PageContext获取其他JSP隐式对象。自定义标签时就使用。

3、提供了的简易方法
pageContext.forward("2.jsp");
    	pageContext.include("2.jsp");
```


四大域对象
=============

```
 PageContext:pageConext 存放的数据在当前页面有效
 ServletRequest: request  存放的数据在一次请求内有效
 HttpSession:session  存放的数据在一次会话中有效，列如存放用户的登录信息
 ServletContexy:application  存放的数据在整个应用范围内都有效，不过范围太大
```


EL表达式
============

1.作用：简化jsp中的java代码开发  ${ }

2.具体功能

​	EL表达式只能获取存在4个作用域中的数据

​		${u} ==pageContext.findAttribute("u");

​	EL获取null这样的数据，在页面中表现为空字符串、

${u.name}====u.getName();

属性导航

 ${u.address.city}  到u下面的address文件

[]能用于去数组而点不能

${u.nam}

${u[name]}

2.运算  empty    判断null ,空字符串和没有元素的集合都返回true

​	什么都没有是true   有东西是 false

```
<%
 	String str=null;
 	pageContext.setAttribute("str",str);
 	String str1="";
 	pageContext.setAttribute("str1",str1);
 	String str2="abc";
 	pageContext.setAttribute("str2",str2);
 	 List list1=new ArrayList();
 	 pageContext.setAttribute("list1",list1);
 	 List list2=new ArrayList();
 	 list2.add("abc")
 	 pageContext.setAttribute("list2",list2);
%>
	 ${empty str}
 	 ${empty str1}
 	 ${empty str2}
 	 ${empty list1}
 	 ${empty list2}
 	true true false true false
```

三元运算符

```
<%
pageContext.setAttribute("gender","1");
%>
<input type="radio" name=sex checked="checked"/>${gender==1?"男":"女"}
```

隐式对象   11个

```
1.pageContext     javax.servlet.jsp.PageContext
2.pageScope       java.util.Map<String,Object>
3.requestScope       java.util.Map<String,Object>
4.sessionScope      java.util.Map<String,Object>
5.applicationScope     java.util.Map<String,Object>
6.param                    java.util.Map<String,String>
7.paramValues             java.util.Map<String,String[]>
8.header                java.util.Map<String,String>
9.headerValues            java.util.Map<String,String[]>
10.initParam                java.util.Map<String,String>
11.cookie                 java.util.Map<String,Cookie>
```

