外部引入

```
<script src="引入地址" type="text/javascript"></script>
```

JavaScript三种消息框

```
alwet(); ：通知<inpu type="button" value="点击" onclick="alert('点击按钮弹出的东西')">
confirm();：带确定和取消
prompt();：出来框
```

与Java的差别

```
1.js使用var运算符声明变量，变量可以存放不同类型的值
2.变量不一定要初始化，未初始化的变量值是undefined
3.变量声明不是必须的，未声明的变量会自动变为全局变量
4.逻辑运算符||和&&遵循短路原则，会返回结束判断的最后一个分项的值
5.等性运算符：==和===，后者是全等，类型和值都要相等
6.类型运算符，typeof返回我的数据类型，instanceof判断是否是某种类型
```

数据类型的转换：number,string,boolean,null,undefined

​	引用类型：var obj=newObject();

```
number,boolean可以通过toString转换为String类型
boolean类型转换为String类型
boolean a="true"
string s=a.toString();
String可以通过 parseInr()和parseFloat()转换为number
```

遍历

```
 var date=["1","2","3",]
 for循环
 for(var i=0;i<date.;length;i++){
   document.write()//打印
 }
 增强型遍历
 for(index a in data){
   document.write()//打印
 }
```

函数事件处理

```
<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN"
        "http://www.w3.org/TR/html4/loose.dtd">
<html>
    <head>
        <meta charset="UTF-8">
        <title>注册表</title>
        <style type="text/css">
            .q{
                text-align: right;
            }
        </style>
    </head>
    <body>
    <form action="#" method="get">
    <table border="1">
        <tr>
            <td colspan="2">
                会员注册USER  REGISTER
            </td>
        </tr>
        <tr>
            <td class="q">
                用户名
            </td>
            <td>
                <input type="text" value="" id="1"/><span id="a"></span>
            </td>
        </tr>
        <tr>
            <td class="q">
                密码
            </td>
            <td>
                <input type="password" value="" id="2"/><span id="b"></span>
            </td>
        </tr>
        <tr>
            <td class="q">
                确认密码
            </td>
            <td>
                <input type="password" value=""id="3"/><span id="c"></span>
            </td>
        </tr>
        <tr>
            <td class="q">
                Email
            </td>
            <td>
                <input type="text" value=""id="4"/><span id="d"></span>
            </td>
        </tr>
        <tr>
            <td class="q">
                姓名
            </td>
            <td>
                <input type="text"/>
            </td>
        </tr>
        <tr>
            <td class="q">籍贯</td>
            <td>
                <select id="guojia">
                    <option>小日本</option>
                    <option>美国</option>
                    <option>英国</option>
                </select>
                <select id="cens">

                </select>
            </td>
        </tr>
        <tr>
            <td class="q">
                性别
            </td>
            <td>
                <input type="radio" name="q" checked="checked"/>男
                <input type="radio" name="q" />女
            </td>
        </tr>
        <tr>
            <td class="q">
                出生日期
            </td>
            <td>
                <input type="text"/>
            </td>
        </tr>
        <tr>
            <td class="q">
                验证码
            </td>
            <td>
                <input type="text"/>
            </td>
        </tr>
        <tr>
            <td colspan="2">
                <input type="submit" value="注册"/>
            </td>
        </tr>
    </table>
    </form>
    </body>
        <script type="text/javascript">
			//失去焦点
           var zhuce= document.getElementById("1");
           var zhuce1=document.getElementById("a");
            zhuce.onblur=function () {
			
                if (zhuce.value ===""){
                    zhuce1.innerHTML = "用户名不能为空";
            }else{
                    zhuce1.innerHTML = "";
                }
            };
            //获取焦点
            var mima=document.getElementById("2");
            var mima1=document.getElementById("b");
            mima.onfocus=function () {
                mima1.innerHTML="请输入六位数密码";
            }
           var mima2=document.getElementById("3");
           var mima3=document.getElementById("c");
           mima2.onblur=function () {
               if(mima.value!=mima2.value){
                   mima3.innerHTML="俩次密码输入不一致";
               }else {
                   mima3.innerHTML="";
               }
           }
           var youxiang=document.getElementById("4");
           var youxiang1=document.getElementById("d");

           youxiang.onblur=function () {
               var q=new RegExp("\^([a-zA-Z0-9_-])+@([a-zA-Z0-9_-])+(.[a-zA-Z0-9_-])+\$");
               if(q.test(youxiang.value)){
                   youxiang1.innerHTML="";
               }else{
                   youxiang1.innerHTML="邮箱不符合规范";
               }
           }
           var a1=document.getElementById("1");
           var a2=document.getElementById("a");

           a1.onblur=function () {
               var q=new RegExp("\^[a-zA-Z]{1}[0-9a-zA-Z_]{1,}\$");
               if(q.test(a1.value)){
                   a2.innerHTML="";
               }else{
                   a2.innerHTML="用户名不符合规范";
               }
           }
           var a3=document.getElementById("2");
           var a4=document.getElementById("b");

           a3.onblur=function () {
               var q = new RegExp("\^[0-9]{6,8}\$");
               if (q.test(a3.value)) {
                   a4.innerHTML = "";
               } else {
                   a4.innerHTML = "密码不符合规范";
               }
           }
           	//下拉选项二级联动
               var guojia= document.getElementById("guojia");
               var cs=document.getElementById("cens");
               guojia.onchange=function () {
                   var q=guojia.value;
                   switch (q){
                       case "小日本":
                           cs.innerHTML="<option>千岛</option>"+"<option>景田</option>";
                           break;
                       case"美国":
                           cs.innerHTML="<option>纽约</option>"+"<option>巴黎</option>";
                           break;
                       case "英国":
                           cs.innerHTML="<option>首都</option>"+"<option>千岛首都</option>";
                           break;
                   }
               }

        </script>
</html>
```


