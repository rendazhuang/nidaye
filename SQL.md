

看标的结构

```
desc from 表名
```

查询表的内容

```
select * from 表名
```

修改表名

```
alter table 旧表名 rename新表名
```

修改字段名

```
alter table 表名 change 旧属性名 新名 新属性
```

修改字段的数据类型

```
alter table 表名 modiFY旧属性名 数据类型
```

增加字段

```
alter table 表名 ADD属性名1 数据类型 after 属性名2
```

删除字段

```
alter table 表名 drop 属性名
```

修改字段的排列位置

```
alter table 表名modify属性名1 数据类型First/after 属性名2
```

更改表的储存引擎

```
alter table 表名engine=储存引擎名
```

删除表的外键约束

```
alter table 表名drop foreign key 外键别名
```

删除没有被关联的普通表

```
drop table 表名
```

表中插入内容

```
insert into 表名(属性，，，)values（每一列的数据）
```

重复的一列中所有的东西：distinck depart

```
select distinck depart from 表格
```

在一个属性的什么到什么之间的betueen   and

```
1.select*from表格 where 属性 between 最小数据and最大数据
2.select*from表格 where 属性>最小数据and属性<最大数据
```

降序： order by desc（降序）升序asc

```
select *表格order by 表属性 desc
select*表格oeder by 表属性 asc
```

查询人数count()

```
select count(1)from表格where 条件
```

 ```
select b.属性,count(1)from表名b where b.属性名 like'以什么开头%' group by b.属性名   having count(1)>=5
 ```

union all

```
合并俩表，union 过滤掉重复的资料
```

如果存在

```
exists,在条件后使用
```

'年'函数的使用

```
year(now())-year(属性)  age
```

自增

```
auto_increment,一般用在主键里面
```

总和函数

```
select sum() from 表格名
```

平均值函数

```
select avg(属性) from 表格名
```

最大值函数

```
select max(属性) from 表格名
```

最小值函数

```
select min(属性) from 表格名
```

like

```
like 后面跟' ',表示数字，像，，，，，一样
```

as

```
creat table 新表格 as select 属性或者* from 有内容的表格：    表示把一个表格的内容及格式弄到另一个新建的表格
```

case

```
在表原来的基础上另添加一列，用来描述其中一列，常用的的格式有：
case
when 表属性（分类之类的）
between 一个条件and另一个条件
then 后面跟在上面那些条件符合的情况下要出来的结果
else 后面跟如果不符合上面那些条件的要出的结果
end 后面跟这一列的属性名
```

内连接

```
select 查询列 from 表1 jion 表2 on 连接条件 where 查询条件
```

左外连接

```
select 查询列 from 表1 left join 表2 on 连接条件 where
```

右外连接

```
select 查询列 from 表1 right outer join 表2 on 连接条件 where 查询条件
```

索引:索引分为普通索引，主键索引和复合索引

```
create index 索引名字 on 表格名字//普通索引的创建
crente unique index 索引名字 on表格名字//唯一索引
create index 索引名字 on 表格名字（这里面可以写多个属性名）//复合索引
```

修改索引

```
alter table 表格名字ADD index（索引名字什么的）
```

查看索引

```
show index from 表名
show keys from t1
删除索引：drop index 索引名 on 表名
```

查询一个表的大致结构

```
select 属性
from 表名 left join 另一个表on 连接条件
where 筛选条件
groupby 分组条件
having 筛选分组条件结果
ordeyby desc/asc(降序或者升序)
```

