jQuery与DOM对象转换

```
//将DOM对象转换成jQuery对象
 var q=document.getElmentById("username");
 var $q1=$(q);
 //将//将jQuery对象转换成DOM对象
 var $s1=$("#username");
 var q=$s1[0]
```

加载完毕事件

```
//js
window.onload=function(){
  
}
//jQ
$(document).ready(fuction(){
  
})
```

jQ选择器

```
//选择id为container的元素
$("#container").css("outline","2px solid red")
//选择所有的sapan元素
$("span")
//现在class为s的元素
$(".s")
//选择class为s的span元素
$(".s,span")
//选择所有元素
$("*")
//选择a内所有后代为b的元素
$("a b")//所有的
$("a>b")//子元素
//选择a后面的同层元素
$("a+b")//a后面同辈的第一个$("#tex+span")
$("a~b")//a后面的所有同辈元素
```

属性选择器

```
$("div[text]")
$("div[text='abc']")
```

过滤器

```
索引过滤
  :first和:last   第一项和最后一项
  :eq(index),:gt(index),:lt(index)  等于，大于，小于
  :even,:odd     偶数项和气数项
  :not()   去除所有与给定选择器匹配的元素
 内容过滤   （返回ture或）
 	:empty   当前元素为空（不含有子元素或文本节点）
 	:parent   当前元素为父元素
 	:has      当前元素含有指定的子元素
 	:contains   当前元素含有指定的文本
 可见性过滤
 	:hidden  选择隐藏的元素，俩种情况1.display:none  2.表单隐藏：<input type="hidden"/>
 	:visible   选择可见的元素
 	隐藏元素可以show()函数来显示
```

字元素和表单

```
子元素过滤
	:nth-child(num)   匹配第几个子元素，从1开始
	:first-child   匹配第一个子元素
	:last-child    匹配最后一个子元素
	:only-child   匹配唯一的子元素
  子元素例子
      $("ul li:first-child")//所有ul中的第一个li
表单过滤
	:input  匹配所有表单元素，包括下列列表等等
	//匹配input的type属性
	（表框和密码框）
		:text 和:password   $(":input:text")
		（单选和多选）
		:radio和:checkbox
		（提交按钮，重置按钮，）
		:submit  :reset  :image   :button
		(上传文件)
		:file   :hidden
过滤表单元素
	可用性（多用于type="text"）
	:enabled   选择可用的元素
	:disabled   选择不可用的元素
	是否选中
		:checked  选中（单选框 radio  复选框  checkbox）
		:selected   选中（下拉列表）
```

属性

```
操作元素的属性
var q=$("#u").sttr("disabled")//查找id为u的是否有disabled这个属性
attr("属性名")      返回值是undefined
$("#u").attr("属性名","属性") //往id为u的里面添加 
$("#u").removeAtte("disabled")//移除id为u的disabled属性


prop()和removeProp()    返回true和false

属性的切换
$("#o").toggleClass(特殊的属性，颜色之类的)//与id为o的class属性相换
addClass("")增加某些属性  removeClass()
```

```
html操作
	html()获得元素内的html代码，含有标签
	html(..)设置html代码，如果有标签进行解析
文本操作
	text()获得文本值，标签被过滤
	text(...)设置文本值
value:val()函数获取和设置value
```

css

```
$("span").mouseover(function(){
  $("span").css({
    "font-size":"50px",
    color:"red"
  }).mouseout(function(){
    $("span").css({
      "font-size":"20px",
      color:"black"
    })
  })
})
实现了鼠标悬浮其上时，文本变成50px，红色
离开时，文本变成20px，黑色
```

文档处理

```
内部插入
a.append(b)  将b插入到a内部标签的后面
a.prepend(b)  将b插入到a内部标签的前面
外部插入
	a.after(b)  将b插入到a标签后面
	a.before(b)  将b插入到a标签前面
删除
	empty()   删除元素的内容，即元素所有子节点
	remove()
	detach()
复制和替换
	复制：clone()     clone(true) 参数代表事件处理函数也要复制
	替换：a.replaceWith(b)  使用b替换a
			$("p").replaceWith("<b>abc</b>")
					用<b>abc</b>替换掉所有的p标签
```

元素筛选   函数

```
first()   先选出所有的，然后在选第一个
$("div:first")和$("div").first()
eq(index)   筛选出指定索引的元素
last()     筛选出最后一个元素

is()  如果符合指定选择器，返回true,否则返回false
filter()  筛选出符合指定选择器的元素集合
no()  删除符合指定选择器的元素
```

查找    函数

```
a.find(b)  找出a里面包含b的，所有的  包括儿子，孙子
a.children(b)   找出a里面是b的儿子
a.next(b)   找出a同级的下一个
a.nextAll(b)  下面全部

a.prev(b)  a的上一个   a.prevAll(b)  前面的全部
a.siblings() 所有同辈


a.parent()  找到a的父元素
```

事件方法

```
blur()  失去焦点
focus()  获得焦点
mouseout()  鼠标移出
mouseover()   鼠标移入
change()     值发生变化
select()     文本被选中
click()   鼠标单击
dbclick()  鼠标双击
submit()  提交
error()  页面异常

 获得焦点  focusin（针对自己时在自己或者孩子处都能触发）和focusout（）
mouseover(移入)   mouseenter
mouseout（移出）和mouseleave
```

事件操作和处理

```
事件绑定
	.bind("绑定事件（上面）","具体方法")  解绑： .unbind("事件")    可以写进方法
	.on("事件 事件""方法")：绑定多个事件         .off("事件" "事件")  
	
	.one("事件","方法") ：单次，就获取一次
	
	$(".q").trigger("click事件")   触发class为q所有click事件
	$(".q").triggerHandler("click事件")   只触发第一个click事件
	繁衍：
        $(".q").live("click","function(){
                $("body").append("<input type='butten'class='q'/>")
                }")   给class为q的添加一个事件 
        $(".q").die("click")   不让他繁衍
 显示，隐藏
 .show(速度,方法)  显示出来之后做些什么，方法实现
 .hide(速度,方法)  隐藏
 .toggle(速度,方法)   切换，显示的时候隐藏，隐藏的时候显示
 
 滑动
 .slideToggle(时间)  切换，显示的时候隐藏，隐藏的时候显示，显示方式是下滑
 显示：slideDown()
 隐藏：slideUp()
 淡入淡出
 	fadeToggle(时间，方法)   切换，显示的时候淡入，隐藏的时候淡出
 	隐藏：fadeOut()
 	显示：fadeln()
 fadeTo(时间,0.5,方法)  指定透明度
```

文字提示

```
<a herf="#"title="要提示的东西">：开始默认在下方
$（fuction()){
//鼠标移动事件
  $(".m").mouseover(function(event){
  		//获取title属性
    	var q=$(this).attr("title")
    //把title数据存入缓存
    if(q!=""){
      	$(this).date("title","title")//缓存
      	$(this).sttr("title","")
    }else{
      q=$(this).date("title")
    }
    var d=$("<div id='t'></div>")//创建div并获取
    	d.html(q);//动态的把title内容给div
    //根据鼠标移动设置div的位置
    d.offset({"left":event.pageX+20,"top":event.pageY-10});
    b.appendTo("body").show();//添加到body标签并显示
  }).mouseover(function(event){
    	 $("#t").offset({"left":event.pageX+20,"top":event.pageY-10});
  }.mouseout(function(){
    //鼠标移开事件
    $("#t").remove()
  })
}
```

遍历

```
1.$("div").each(function(i){
  i就是索引值
  this表示获取遍历每一个对象
})
2.$("div").each(function(index,ele){
  index就是索引值
  ele表示获取遍历每一个对象
})
3.var s=$("div");
$.each(s,function(index,ele){
  s是要遍历的集合
  index就是索引值
  ele表示获取遍历的每一个对象
})
```

