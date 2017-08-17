注释：<!-内容->

<a href=www.baidu.com>点击</a>:跳转到百度网页（href）

<br/>:换行

<h1>~<h6>:标题，字体越来越小

特殊符号：大于号(>):&nbsp

​		   小于号(<):&gt

​		   引号("):&lt

​	版权符号(©):&copy

基本格式

```
<html>
	<head>
	<meta charset="UTF-8">//设置格式
	</head>
	<body>
	//写代码
	</body>
</html>
```

html块级标签

```
1.标题标签:
<h1>~<h6>字体越来越小
2.段落标签：
<p> </p>
3.水平标尺线:<hr/>

4.有序列表标签：<ol> </ol> 

<ol type="1">按照123这样的顺序，还有a,A,I

5.无序列表标签：<ul> </ul>  <li></li>

<ul type="disc">方块

6.定义列表标签:<dl> </dl>	
<dl>
	<dt>
	//显示图片的
	<dt>
	<dd>
	//对图片进行解释
	<dd>
<dl>
7.表格标签:<table> </table>
	<table borter="1">设置表格边框
	表格合并：rowspan(纵向合并)colspan(横向合并)
<html>
	 <head>
		  <title>合并单元格 </title>
	 </head>

	 <body>
	 <table>
		<tr>
		<!--纵向合并3个单元格-->
		<td rowspan="3">一季度</td>
		<td>一月</td>
		<td>五万元</td>
		</tr>
		<tr>
		<td>二月</td>
		<td>3万元</td>
		</tr>
		<tr>
		<td>三月</td>
		<td>4万元</td>
		</tr>
		<tr>
		<td>总额</td>
		<!--横向合并2个单元格-->
		<td colspan="2">12万元</td>
		</tr>
		</table>
	 </body>
</html>

8.表单标签<form> </form>
	<form name="表单名称" cation="要提交的地址" method="提交方法(get，post)">
	表单中的基本元素：
	
      一.type	指定表单元素的类型，可用的选项有text、password、checkbox、radio、submit、reset、 file、hidden、image 和 button，默认为 text
      二.name	指定表单元素的名称
      三.value	指定表单元素的初始值
      四.size	指定表单元素的初始宽度。如果type为text或password，则表单元素的大小以字符为单位；对于其他输入类型，宽度以像素为单位
      五.maxlength	指定可在text或password元素中输入的最大字符数，默认不做限制
      六.checked	此属性只有一个值，为“checked”，表示选中状态，如果不选中，则不需添加此属性
	<form menthod="post" cation="www.">
		<input type="text(表格)/radio(选的圆点)" value="zhangsan" size="20" name=" ">
	</form>
9.分区标签:<div> </div>
	分区标签<div>常用于页面布局时对区块的划分，它相当于一个大的容器，可以容纳无序列表、有序列表、表格、段落等块级标签。
```

有些块级标签会有自己的行级标签

```
<ul>/<ol>: <li></li>:有序列表和无序列表的行级标签<li>
<table>/<table>:<tr><td><td></tr>:<table>块级标签中行级标签是<tr>,<tr>中还包含<td>

div-ul(ol)-li:常用于分类导航或菜单等场合。

div-dl-dt-dd:常用于图文混编场合。

table-tr-td:常用于规整数据的显示。


form-table-tr-td：常用于表单布局的场合。
```



html行级标签

```
1.图像标签	<img/>
	<img src="图片地址">  常见的图片格式jpg.gif.bmp.png
2.范围标签	<span></span>
	<span style="要设置的具体样式">文字</span>
3.换行标签	<br/>
	一般用于语句结尾，需要换行时
4.超级链接	<a></a>
	<a href="地址" target="目标窗口位置">显示的东西</a>
	这里target="_blank"是打开一个页面，不写默认在本页面打开
	瞄链接
	在要跳转到的地方设置  <a name="marker">A</a>
	要跳转到设置了瞄链接的位置   <a href="#marke">点击跳转到A位置</a>
```


html表单实例
============

```
<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd">
<html>
	 <head>
	  <title> 表单 </title>
	  <meta name="Generator" content="EditPlus">
	  <meta name="Author" content="">
	  <meta name="Keywords" content="">
	  <meta name="Description" content="">
	 </head>

	 <body>
	 <!--action提交到哪,method 以什么方式提交-->
		<form action=" " method="get">
		账号：<input type="text" name="account"><br/>
		密码：<input type="password" name="pwd"><br/>
		<!-单选->
		性别：<input type="radio" name="gerder" value="male" checked="checked" >男
		<input type="radio" name="gerder" value="game" >女<br/>
		<!-多选->
		爱好:<input type="checkbox" name="hobby" volue="game">游戏
		<input type="checkbox" name="hobby" volue="reding">读书
		<input type="checkbox" name="hobby" volue="skiing">滑雪<br/>
		<!-上传文件：file关键字->
		选择文件：<input type="text" name="tupian">
		<input type="file" name="pic" accept="image/gif"><br/>
		喜欢吃什么：<!--设置下拉选项：select 》option-->
		<select name="fruit">
		<option value="apple">苹果</option>
		<option value="xaingjiao">香蕉</option>
		<option value="xigua">西瓜</option>
		<option value="chengzi">橙子</option>
		</select><br/>
		<!--disabled:禁用  readonly:只读 。后面不写代表可以编辑-->
		<textarea row="5" cols="10" disabled="disabled">你是不是傻</textarea>
		<textarea row="5" cols="10" readonly="readonly">你是不是傻啊</textarea>
		<textarea row="5" cols="10" >你自己说吧</textarea><br/>
		邮箱：<input type="mail" name="mail"><br/>
		 <input type="submit" value="提交">
		 <input type="reset" value="重置">
		 
		</form>
	 </body>
</html>
```

