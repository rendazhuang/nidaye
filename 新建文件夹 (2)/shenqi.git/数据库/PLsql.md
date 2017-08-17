PLsql

rownum

```
select * from 表格  where rownum=1(取一笔资料)
```

算术运算

```
+    -    *  /
```

关系运算

```
> >=  =<  <  ==   !=   
```

逻辑运算

```
或 与  非
```

if结构

```
1.if  条件（列如：2>1）
```



基本格式：

![1](C:\Users\123\Desktop\PLsql\1.png)

循环

```
declare
var_id varchar(20) :=1;
var_name varchar(20) :=0;
begin
   loop
     var_id :=  var_id+1;(循环的次数)
     var_name :=var_id+var_id;（循环次数所得的值）
   end loop;
   dbms_output.put_line(输出的值var_name)
end;
```



delclare

​       变量名(长度不能超过30个字符)   类型   :=值;

​      v_       表名   列名  %type  :=值；

begin



​     if/dbma_output.put_lne