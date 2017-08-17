css :  style    放在html的颈部

```
<head>

  <style type="text/css">

  //各种标签的设置

   </style>

</head>

```

规范

```
1.全部推荐小写
2.每条样式规则用(;)隔开
3./*..*/注释
```

标签选择器

```

```

id选择器

```

```

文本属性

``` 
  width:宽度
  line-height:设置行高(25px,28px) 
    text-align:设置对齐方式(left,right,center)
 letter-spacing:设置字符间距(3px.8px)
text-decoration:设置文本修饰,加中划线()下划线(underline),取消(none)
    white-space:处理空白，是否换行，nowrap（不换行）
```

字体属性     font.0

```
font-family:设置字体样式
  font-size：定义字体大小
 font-weight：定义字体粗细
```

背景属性   background

```
background-color:设置背景颜色
background-image：url(图片地址)  ：设置背景图片
background-repeat:设置背景平铺方式(x，y)
background-position:设置背景出现的初始位置；1.background-position:20px-100px
										  2.30%50%
										  3.right top:右上角
										  	left bottom:左下角
										  	top:上方水平居中位置
```

在不用ol和ul也可以实现列表的的各类风格   list-style

```
none	去掉修饰符号	list-style:none

disc	实心圆（<ul>默认类型）	list-style:disc	•刷牙 •洗脸

circle	空心圆	list-style:circle	〇刷牙 〇洗脸

square	实心正方形	list-style:square	■刷牙 ■洗脸

decimal	数字（<01>默认类型）	list-style:decimal	1. 刷牙
2. 洗脸
```


div
==========

外边距设置   margin

```
margin-top:上外边距  margin-top:1px
margin-right:右外边距   margin-right：2px
margin-bottom:下外边距  margin-bottom：2px
margin-left：  左外边距  margin-left:1px
margin:1px 2px 3px 4px 上右下左
```

边框(颜色，宽度，样式（实线，虚线）)   border

```
border-color:边框颜色
border-width:边框宽度
border-style:边框样式(none(默认，无边框)，solid(实线)，dashed(虚线))

border-top:上边框
border-right:右边框
border-bottom:下边框
border-left:左边框

border-left:1px solid red :设置边框左边1像素，红色，实线
```

内边距   padding

```
padding-top	内容与上边框之间的距离	padding-top： 5px

padding-right	内容与右边框之间的距离	padding-right： 5px

padding-bottom	内容与下边框之间的距离	padding-bottom ： 5px

padding-left	内容与左边框之间的距离	padding-left： 5px

padding： 5px l0px 20px 40px
(按顺时针方向，上填充5px，右填充
10px，下填充20px，左填充40px)
```


浮动
=========

float:left   左浮动

float:right  右浮动

float:none  默认不浮动

浮动清除    clear

clear left       左侧不允许有浮动

clear rigth    右侧不允许有浮动

clear both   俩侧都不允许有浮动

clear  none  默认，允许俩侧都有浮动

```
a:link	a:link{color:#999;} 	未单击访问时的超链接样式 	常用，超链接主样式 
a:visited	a:visited{color:#333;} 	单击访问后的超链接样式 	需区分是否已被访问 
a:hover	a:hover{color:#ff7300;} 	鼠标悬浮其上的超链接样式	常用，实现动态效果 
a:active	a:active {color:#999;}	鼠标单击未释放的超链接样式	少用，一般与link —致
```

