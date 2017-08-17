# **Oracle函数分类总结******

F.1字符函数——返回字符值

这些函数全都接收的是字符族类型的参数(CHR除外)并且返回字符值.除了特别说明的之外,这些函数大部分返回VARCHAR2类型的数值.字符函数的返回类型所受的限制和基本数据库类型所受的限制是相同的,比如: VARCHAR2数值被限制为2000字符(ORACLE 8中为4000字符),而CHAR数值被限制为255字符(在ORACLE8中是2000).当在过程性语句中使用时,它们可以被赋值给VARCHAR2或者CHAR类型的PL/SQL变量.

 

l **CHR******

**语法**:  chr(x)

**功能：**返回在数据库字符集中与X拥有等价数值的字符。CHR和ASCII是一对反函数。经过CHR转换后的字符再经过ASCII转换又得到了原来的字符。

使用位置：过程性语句和SQL语句。

 

l **CONCAT******

**语法：** CONCAT（string1,string2）

**功能：**返回string1，并且在后面连接string2。

**使用位置：**过程性语句和SQL语句。

 

l **INITCAP******

**语法：**INITCAP（string）

**功能：**返回字符串的每个单词的第一个字母大写而单词中的其他字母小写的string。单词是用.空格或给字母数字字符进行分隔。不是字母的字符不变动。

 

**使用位置：**过程性语句和SQL语句。

 

l **LTRIM******

**语法：**LTRIM（string1,string2）

**功能：**返回删除从左边算起出现在string2中的字符的string1。String2被缺省设置为单个的空格。数据库将扫描string1，从最左边开始。当遇到不在string2中的第一个字符，结果就被返回了。LTRIM的行为方式与RTRIM很相似。

**使用位置：**过程性语句和SQL语句。

 

l **NLS_INITCAP**

**语法：NLS_INITCAP（string[,nlsparams]）******

**功能：**返回字符串每个单词第一个字母大写而单词中的其他字母小写的string，nlsparams

指定了不同于该会话缺省值的不同排序序列。如果不指定参数，则功能和INITCAP相同。Nlsparams可以使用的形式是：

**‘NLS_SORT=sort****’******

这里**sort**制订了一个语言排序序列。

**使用位置：**过程性语句和SQL语句。

 

l **NLS_LOWER******

**语法：NLS_LOWER（string[,nlsparams]）******

**功能：**返回字符串中的所有字母都是小写形式的string。不是字母的字符不变。

      Nlsparams参数的形式与用途和**NLS_INITCAP**中的**nlsparams**参数是相同的。如果**nlsparams**没有被包含，那么**NLS_LOWER**所作的处理和**LOWER**相同。

**使用位置；**过程性语句和SQL语句。

 

l **NLS_UPPER******

**语法：nls_upper（string[,nlsparams]）******

**功能：**返回字符串中的所有字母都是大写的形式的string。不是字母的字符不变。nlsparams参数的形式与用途和**NLS_INITCAP**中的相同。如果没有设定参数，则NLS_UPPER功能和UPPER相同。

**使用位置：**过程性语句和SQL语句。

 

l **REPLACE******

**语法：REPLACE（**string，search_str[,replace_str]**）**

**功能：**把string中的所有的子字符串search_str用可选的replace_str替换，如果没有指定replace_str，所有的string中的子字符串search_str都将被删除。**REPLACE**是**TRANSLATE**所提供的功能的一个子集。

**使用位置：**过程性语句和SQL语句。

 

l **RPAD******

**语法：RPAD（string1,x[,string2]）******

**功能：**返回在X字符长度的位置上插入一个string2中的字符的string1。如果string2的长度要比X字符少，就按照需要进行复制。如果string2多于X字符，则仅string1前面的X各字符被使用。如果没有指定string2，那么使用空格进行填充。X是使用显示长度可以比字符串的实际长度要长。RPAD的行为方式与LPAD很相似，除了它是在右边而不是在左边进行填充。

**使用位置：**过程性语句和SQL语句。

 

l **RTRIM******

**语法:  RTRIM（string1,[,string2]）******

**功能:  **返回删除从右边算起出现在string1中出现的字符string2. string2被缺省设置为单个的空格.数据库将扫描string1,从右边开始.当遇到不在string2中的第一个字符,结果就被返回了**RTRIM**的行为方式与**LTRIM**很相似.

**使用位置：**过程性语句和SQL语句。

 

l **SOUNDEX******

**语法:  SOUNDEX（string）******

**功能:  **返回string的声音表示形式.这对于比较两个拼写不同但是发音类似的单词而言很有帮助.

**使用位置：**过程性语句和SQL语句。

 

l **SUBSTR******

**语法:  SUBSTR（string,a[,b]）******

**功能:**  返回从字母为值a开始b个字符长的string的一个子字符串.如果a是0,那么它就被认为从第一个字符开始.如果是正数,返回字符是从左边向右边进行计算的.如果b是负数,那么返回的字符是从string的末尾开始从右向左进行计算的.如果b不存在,那么它将缺省的设置为整个字符串.如果b小于1,那么将返回NULL.如果a或b使用了浮点数,那么该数值将在处理进行以前首先被却为一个整数.

**使用位置：**过程性语句和SQL语句。

 

l TRANSLATE

**   语法:  TRANSLATE(string,from_str,to_str)******

**   功能:  **返回将所出现的from_str中的每个字符替换为to_str中的相应字符以后的string. TRANSLATE是REPLACE所提供的功能的一个超集.如果from_str比to_str长,那么在from_str中而不在to_str中而外的字符将从string中被删除,因为它们没有相应的替换字符. to_str不能为空.Oracle把空字符串认为是NULL,并且如果TRANSLATE中的任何参数为NULL,那么结果也是NULL.

**使用位置：**过程性语句和SQL语句。

 

l **UPPER******

**语法: UPPER（string）******

**功能: **返回大写的string.不是字母的字符不变.如果string是CHAR数据类型的,那么结果也是CHAR类型的.如果string是VARCHAR2类型的,那么结果也是VARCHAR2类型的.

**使用位置:** 过程性语句和SQL语句。

**F.2    字符函数——返回数字******

这些函数接受字符参数回数字结果.参数可以是CHAR或者是VARCHAR2类型的.尽管实际下许多结果都是整数值,但是返回结果都是简单的NUMBER类型的,没有定义任何的精度或刻度范围.

 

l **ASCII******

**语法:  ASCII（string）******

**功能: **数据库字符集返回string的第一个字节的十进制表示.请注意该函数仍然称作为ASCII.尽管许多字符集不是7位ASCII.CHR和ASCII是互为相反的函数.CHR得到给定字符编码的响应字符. ASCII得到给定字符的字符编码.

**使用位置:** 过程性语句和SQL语句。

 

l **INSTR******

**语法:  INSTR（string1, string2[a,b]）******

**功能: ** 得到在**string1**中包含string2的位置. string1时从左边开始检查的,开始的位置为a,如果a是一个负数,那么string1是从右边开始进行扫描的.第b次出现的位置将被返回. a和b都缺省设置为1,这将会返回在string1中第一次出现string2的位置.如果string2在a和b的规定下没有找到,那么返回0.位置的计算是相对于string1的开始位置的,不管a和b的取值是多少.

**使用位置:** 过程性语句和SQL语句。

 

l **INSTRB******

**语法:**  **INSTRB（string1, string2[a,[b]]）******

**功能: ** 和INSTR相同,只是操作的对参数字符使用的位置的是字节.

**使用位置:** 过程性语句和SQL语句。

 

l **LENGTH******

**语法:  LENGTH（string）******

**功能:**  返回string的字节单位的长度.CHAR数值是填充空格类型的,如果string由数据类型CHAR,它的结尾的空格都被计算到字符串长度中间.如果string是NULL,返回结果是NULL,而不是0.

**使用位置:** 过程性语句和SQL语句。

 

l **LENGTHB******

**语法:  LENGTHB（string）******

**功能:  **返回以字节为单位的string的长度.对于单字节字符集LENGTHB和LENGTH是一样的.

**使用位置:** 过程性语句和SQL语句。

 

l **NLSSORT******

**语法: NLSSORT（string[,nlsparams]）******

**功能: **得到用于排序string的字符串字节.所有的数值都被转换为字节字符串,这样在不同数据库之间就保持了一致性. Nlsparams的作用和NLS_INITCAP中的相同.如果忽略参数,会话使用缺省排序.

**使用位置:** 过程性语句和SQL语句。

 

**F.3    数字函数******

函数接受NUMBER类型的参数并返回NUMBER类型的数值.超越函数和三角函数的返回值精确到36位.ACOS、ASIN、ATAN、ATAN2的结果精确到36位.

l **ABS******

**语法:   **ABS(x)

**功能:   **得到x的绝对值.

**使用位置:** 过程性语言和SQL语句。

 

l **ACOS******

**语法:  **ACOS(x)

**功能:**  返回x的反余弦值. x应该从0到1之间的数,结果在0到pi之间,以弧度为单位.

**使用位置:** 过程性语言和SQL语句。

 

l **ASIN******

**语法:  **ASIN(x)****

**功能:  **计算x的反正弦值. X的范围应该是－1到1之间,返回的结果在－pi/2到pi/2之间,以弧度为单位.

**使用位置:** 过程性语言和SQL语句。

 

l **ATAN******

**语法:  **ATAN(x)

**功能:  **计算x的反正切值.返回值在－pi/2到pi/2之间,单位是弧度.

**使用位置:** 过程性语言和SQL语句。

 

l **ATAN2******

**语法: ** ATAN2(x,y)

**功能:  **计算x和y的反正切值.结果在负的pi/2到正的pi/2之间,单位是弧度.

**使用位置:** 过程性语言和SQL语句。

 

l **CEIL******

**语法:  **CEIL(x)

**功能:  **计算大于或等于x的最小整数值.

**使用位置:** 过程性语言和SQL语句。

 

l **COS******

**语法:  **COS(x)

**功能:  **返回x的余弦值. X的单位是弧度.

**使用位置:** 过程性语言和SQL语句。

 

l **COSH******

**语法:  **COSH(x)

**功能:  **计算x的双曲余弦值.

 

l **EXP******

**语法:  **EXP(x)

**功能:  **计算e的x次幂. e为自然对数,约等于2.71828.

**使用位置:** 过程性语言和SQL语句。

 

l **FLOOR******

**语法:  **FLOOR(x)

**功能:  **返回小于等于x的最大整数值.

**使用位置:** 过程性语言和SQL语句。

 

l **LN******

**语法: ** LN(x)

**功能:**  返回x的自然对数. x必须是正数,并且大于0

**使用位置:** 过程性语言和SQL语句。

 

l **LOG******

**语法:  **LOG(x)

 

**功能:  **计算以x为底的y的对数.底必须大于0而且不等于1, y为任意正数.

**使用位置:** 过程性语言和SQL语句。

 

l **MOD******

**语法:  **MOD(x,y)

**功能:  **返回x除以y的余数.如果y是0,则返回x

**使用位置:** 过程性语言和SQL语句。

 

l **POWER******

**语法:  **POWER(x,y)

**功能:**  计算x的y次幂.

**使用位置:** 过程性语言和SQL语句。

 

l **ROUND******

**语**法**:  **ROUND(x[,y])

**功能:  **计算保留到小数点右边y位的x值. y缺省设置为0,这会将x保留为最接近的整数.如果y小于0,保留到小数点左边相应的位. Y必须是整数.

**使用位置:** 过程性语言和SQL语句。

 

l **SIGN******

**语法:**  SIGN(x)

**功能:**  获得x的符号位标志.如果x<0返回－1.如果x=0返回0.如果x>0返回1.

**使用位置:** 过程性语言和SQL语句。

 

l **SIN******

语法:SIN(x)

功能:计算x的正弦值. X是一个以弧度表示的角度.

**使用位置:** 过程性语言和SQL语句。

 

l **SINH******

语法:SINH(x)

功能:返回x的双曲正弦值.

**使用位置:** 过程性语言和SQL语句。

 

l **SQRT******

**语法:  **SQRT(x)

**功能:  **返回x的平方根. x必须是正数.

**使用位置:** 过程性语言和SQL语句。

 

l **TAN******

**语法:  **TAN(x)

**功能:  **计算x的正切值, x是一个以弧度位单位的角度.

**使用位置:** 过程性语言和SQL语句。

 

l **TANH******

**语法:  **TANH(x)

**功能:  **计算x的双曲正切值.

**使用位置:** 过程性语言和SQL语句。

 

l **TRUNC******

**语法:  **TRUNC(x[,y])

**功能:  **计算截尾到y位小数的x值. y缺省为0,结果变为一个整数值.如果y是一个负数,那么就截尾到小数点左边对应的位上.

**使用位置:** 过程性语言和SQL语句。

 

**F.4    日期函数******

日期函数接受DATE类型的参数.除了MONTHS_BETWEEN函数返回的是NUMBER类型的结果,所有其他的日期函数返回的都是DATE类型的数值.

l **ADD_MONTHS******

**语法: ** ADD_MONTHS(d,x)

**功能:**  返回日期d加上x个月后的月份。x可以是任意整数。如果结果日期中的月份所包含的天数比d日期中的“日”分量要少。（即相加后的结果日期中的日分量信息已经超过该月的最后一天，例如，8月31日加上一个月之后得到9月31日，而9月只能有30天）返回结果月份的最后一天。

**使用位置:** 过程性语言和SQL语句。

 

l **LAST_DAY******

**语法:LAST_DAY(d)******

**功能:**计算包含日期的d的月份最后一天的日期.这个函数可以用来计算当月中剩余天数.

**使用位置:** 过程性语言和SQL语句。

 

l **MONTHS_BETWEEN******

**语法:  MONTHS_BETWEEN(date 1,date2)******

**功能:  **计算date 1和date2之间月数.如果date 1,date2这两个日期中日分量信息是相同的,或者这两个日期都分别是所在月的最后一天,那么返回的结果是一个整数,否则包括一个小数,小数为富余天数除以31.

**使用位置:** 过程性语言和SQL语句。

 

l **NEW_TIME******

**语法:  NEW_TIME(d,zone1,zone2)******

**功能:** 计算当时区zone1中的日期和时间是s时候,返回时区zone2中的日期和时间. zone1和zone2是字符串.

**使用位置:** 过程性语言和SQL语句。

 

l **NEXT_DAY******

**语法:  NEXT_DAY(d,string)******

**功能:  **计算在日期d后满足由string给出的条件的第一天. String使用位置;当前会话的语言指定了一周中的某一天.返回值的时间分量与d的时间分量是相同的. String的内容可以忽略大小写.

**使用位置:** 过程性语言和SQL语句。

 

l **ROUND******

语法:  ROUND(d[,format])

**功能:  **将日期d按照由format指定的格式进行处理.如果没有给format则使用缺省设置`DD`.

**使用位置:** 过程性语言和SQL语句。

 

l **SYSDATE******

**语法: SYSDATE******

**功能:** 取得当前的日期和时间,类型是DATE.它没有参数.但在分布式SQL语句中使用时,SYSDATE返回本地数据库的日期和时间.

**使用位置:** 过程性语言和SQL语句。

 

l **TRUNC******

**语法:  TRUNC(d,format)******

**功能:**  计算截尾到由format指定单位的日期d.可以使用位置:格式和效果.缺省参数同ROUNG.

**使用位置:** 过程性语言和SQL语句。

 

 

**F.5     转 换 函 数******

** **

转换函数用于在PL/SQL数据类型之间进行转换.PL/SQL尽可能地自动进行转换,也就是采用隐含方式转换.隐含转换无法转换格式信息,并且有些类型的数据之间不支持隐含转换,所以对这些可以采用显示转换.使用显示转换也是一种好的编程习惯

.

l **CHARTOROWID******

**语法:  CHARTOROWID(string)******

**功能:**  把包含外部格式的ROWID的CHAR或VARCHAR2数值转换为内部的二进制格式.参数string必须是包含外部格式的ROWID的18字符的字符串.oracle7和 oracle8中的外部格式是不同的.CHARTOROWID是ROWIDTOCHAR的反函数.

**使用位置:** 过程性语言和SQL语句。

 

l **CONVERT******

**语法:  **CONVERT(string,dest_set[,source_set])

**功能:  **将字符串string从source_set所表示的字符集转换为由dest_set所表示的字符集.如果source_set没有被指定,它缺省的被设置为数据库的字符集.

**使用位置:** 过程性语言和SQL语句。

 

l **HEXTORAW******

**语法:** ** HEXTORAW(string)******

**功能:  **将由string表示的二进制数值转换为一个RAW数值. String应该包含一个十六进制的数值. String中的每两个字符表示了结果RAW中的一个字节..HEXTORAW和RAWTOHEX为相反的两个函数.

**使用位置:** 过程性语言和SQL语句。

 

l **RAWTOHEX******

**语法:  RAWTOHEX(rawvalue)******

**功能: ** 将RAW类数值rawvalue转换为一个相应的十六进制表示的字符串. rawvalue中的每个字节都被转换为一个双字节的字符串. RAWTOHEX和HEXTORAW是两个相反的函数.

**使用位置:** 过程性语言和SQL语句。

 

l **ROWIDTOCHAR******

**语法:**  ROWIDTOCHAR(rowid)

**功能:  **将ROWID类型的数值rowid转换为其外部的18字符的字符串表示,在oracle7和oracle8之间有些不一样的地方. ROWIDTOCHAR和CHARTOROWID是两个相反的函数.

**使用位置:** 过程性语言和SQL语句。

 

l **TO_CHAR(dates)******

**语法:**  TO_CHAR(d [,format[,nlsparams]])

**功能:  **将日期d转换为一个VARCHAR2类型的字符串.如果指定了format,那么就使用位置:它控制结果的方式.格式字符串是由格式元素构成的.第一个元素返回日期数值一个部份,例如日子.如果没有给定format,使用的就是该会话的缺省日期格式.如果指定了nlsparams,它就控制着返回字符串的月份和日分量信息所使用的语言. nlsparams的格式是:

“NLS_DATE_LANGUAGE”

**使用位置:** 过程性语言和SQL语句。

 

l **TO_CHAR(labels)******

**语法:  TO_CHAR(labels[,**format**])******

**功能:  **将MISLABEL的LABEL转换为一个VARCHAR2类型的变量.

**使用位置:** 在trusted数据库的过程性语句和SQL语句。

 

l **TO_CHAR(numbers)******

**语法: TO_CHAR(num[,format[,nlsparams]])******

**功能: 将NUMBER类型的参数num转换为一个VARCHAR2类型的变量.如果指定了**format,那么它会控制这个转换处理.表5-5列除了可以使用的数字格式.如果没有指定format,它会控制这个转换过程.下面列出了可以使用的数字格式.如果没有指定format,那么结果字符串将包含和num中有效位的个数相同的字符. nlsparams用来指定小数点和千分位分隔符和货币符号.可以使用的格式:

**`NLS_NUMERIC_CHARS=****”****dg****”****NLS_CURRENCY=****”****string****”******

d和g分别表示列小数点和千分位分隔符. String表示了货币的符号.例如,在美国小数点分隔符通常是一个句点(.),分组分隔符通常是一个逗号(,),而千分位符号通常是一个$.

**使用位置:** 过程性语言和SQL语句。

 

l **TO_DATE******

**语法:  TO_DATE(String[,format[,nlsparams]])******

**功能:  **把CHAR或者VARCHAR2类型的String转换为一个DATE类型的变量. format是一个日期格式字符串.当不指定format的时候,使用该会话的缺省日期格式.****

**使用位置:** 过程性语言和SQL语句。

 

l **TO****_LABEL******

**语法:**  TO_LABEL(String[,format])

**功能:  **将String转换为一个MLSLABEL类型的变量. String可以是VARCHAR2或者CHAR类型的参数.如果指定了format,那么它就会被用在转换中.如果没有指定format,那么使用缺省的转换格式.

**使用位置:** 过程性语言和SQL语句。

 

l **TO_MULTI_BYTE******

**语法:  **TO_MULTI_BYTE(String)

**功能: **计算所有单字节字符都替位换位等价的多字节字符的String.该函数只有当数据库字符集同时包含多字节和单字节的字符的时候有效.否则, String不会进行任何处理. TO_MULTI_BYTE和TO_SINGLE_BYTE是相反的两个函数.

**使用位置:** 过程性语言和SQL语句。

 

l **TO_NUMBER**

**语法: TO_NUMBER(String[,format[,nlsparams]])******

**功能: **将CHAR或者VARCHAR2类型的String转换为一个NUMBER类型的数值.如果指定了format,那么String应该遵循相应的数字格式. Nlsparams的行为方式和TO_CHAR中的完全相同.TO_NUMBER和TO_CHAR是两个相反的函数.

**使用位置:** 过程性语言和SQL语句。

 

l **TO_SINGLE_BYTE**

**语法: TO_SINGLE_BYTE(String )******

**功能:** 计算String中所有多字节字符都替换为等价的单字节字符.该函数只有当数据库字符集同时包含多字节和单字节的字符的时候有效.否则, String不会进行任何处理.

**TO_MULTI_BYTE和TO_SINGLE_BYTE是相反的两个函数.******

**使用位置:** 过程性语言和SQL语句。

 

 

 

 

 

 

**F.6    分 组 函 数******

** **

分组函数返回基于多个行的单一结果,这和单行函数正好形成对比,后者是对单行返回一个结果.这些函数仅仅对于查询的选择列表和GROUP BY子句有效.

    这些函数大都可以接受对参数的修饰符.可以使用位置:的修饰符有DISTINCT和ALL.如果使用位置:了DISTINCT修饰符,那么在处理中仅仅会考虑由查询返回的不同的取值.ALL修饰符会使得该函数考虑由查询返回的所有数值.如果没有指定任何修饰符,那么缺省使用位置:的是ALL修饰符.

l **AVG******

**语法:  **AVG([DISTINCT| ALL]col)

**功能:  **返回一列数据的平均值.

**使用位置: **查询列表和GROUP BY子句.

 

l **COUNT******

**语法:**  **COUNT(\*****|**** [DISTINCT****|**** ALL] col)******

**功能:  **得到查询中行的数目.如果使用了*获得行的总数.如果在参数中传递的是选择列表,那么计算的是非空数值.

 

l 获得由label界定的最大下界.函数仅用于trusted oracle.**GLB******

**语法:  GLB ([DISTINCT****|**** ALL]label)******

**功能:  **获得由label界定的最大下界.函数仅用于trusted oracle.

**使用位置:**trusted数据库的选择列表和GROUP BY子句.

 

 

l **LUB******

**语法:  LUB ([DISTINCT****|**** ALL]label)******

**功能:** 获得由label界定的最小上界.用于trusted oracle.数据库.

**使用位置:  **trusted数据库的选择列表和GROUP BY子句.

过程性语言和SQL语句。

 

 

l **MAX******

**语法:  MAX([DISTINCT****|**** ALL]col)******

**功能:  **获得选择列表项目的最大值.

**使用位置: **仅用于查询选择和GROUP BY子句.

** **

l **MIN******

**语法:  MIN([DISTINCT****|**** ALL]col)******

**功能: **获得选择列表的最小值.

**使用位置: **仅用于查询选择和GROUP BY子句.

 

 

l **STDDEV******

**语法:  STDDEV([DISTINCT****|**** ALL]col)******

**功能:  **获得选择列表的标准差.标准差为方差的平方根.

**使用位置: **仅用于查询选择和GROUP BY子句.

 

l **SUM******

语法:SUM**([DISTINCT****|**** ALL]col)******

功能:返回选择的数值和总和

**使用位置: **仅用于查询选择和GROUP BY子句.

 

 

l **VARIANCE******

**语法:** **VARIANCE([DISTINCT****|**** ALL]col)******

**功能:**返回选择列表项目的统计方差.

**使用位置: **仅用于查询选择和GROUP BY子句.

 