
JDBC
=========

连接数据库

```
1.注册驱动，创建连接
	
2.获得执行SQL语句的statement对象（写SQL语句）
3.执行SQL语句，返回结束
4.处理结果，关闭资源
```

1.注册驱动

```
1.注册 驱动
Class.forName("Driver类的全名")//反射的动态方式
Connection q=null;
PrepardStatement statement=null;
Resultset resultset=null;
	创建连接   并接收
 q=DriverManager.getConnection(String url(jdbc:mysql://要连的数据库地址:3306/数据库名),"用户名","密码")
          二. 把用户名和密码封装成一个对象
     /*Properties pro=new Properties();
     pro.setProperty("user","用户名");
     pro.setProperty("password","密码");
     Connection q=DriverManager.getConnection(String url(jdbc:mysql://要连的数据库地址:3306/数据库名),"pro")*/
 2.获得执行SQL语句的statement对象（写SQL语句）
 		String s=sql语句
 		statement=p.prepareStatement(s);
 		statement.setString(1,name)
 		statement.setString(2,pws)
 3.返回结果
 	 resultset=statement.executeQuery();
 	创建集合
 4.处理结果
 	while(resultSet.next()){
      int i=resultSet.getInt(1);
      什么类型用什么类型接收
      创建对象
      存入集合
 	}
 		关闭资源
 			finally{
              if(p!=null){
                p.close();
              }
              if(statement!=null){
                statement.close();
              }
 			}
```


JDBC万金油 
=========

1.把ip地址，密码等写进文档，如果变化更改即可

```
Connection=com.mysql.jdbc.Driver
user=jdbc:mysql://localhost:3306/xinjian
uname=root
paswd=123456
```

2.读取文档中键值对相对应的值

```
public String getValueByKey(String key) {

		Properties prop = new Properties();
		//读取流
		File file = new File("Daydome");
			FileInputStream is = new FileInputStream(file);
			//把读取出来的放进去
			prop.load(is);
			//返回根据传入的键值对相对应的值
		return prop.getProperty(key);
	}
```

3.调用2中的方法 ，把相对应的值赋给相对应的

```
public Jdbcutil() {
		Confiog config = new Confiog();
		//获得自带的代码地址
		drvierClass = config.getValueByKey("Connection");
		//获得地址
		url = config.getValueByKey("user");
		//获得用户名
		userName = config.getValueByKey("uname");
		//获得密码
		passwd = config.getValueByKey("paswd"); 
	}
```

4.获得数据库连接,返回地址

```
	/**
	 * 获取数据库连接
	 * 
	 * @param dirverClass
	 *            驱动类
	 * @param url
	 *            连接字串
	 * @param userName
	 *            用户名
	 * @param passwd
	 *            密码
	 * @return 数据库连接
	 */
	public  Connection getConection(){
		Class.forName(drvierClass);
			con = DriverManager.getConnection(url, userName, passwd);
			return con;
		}
```

5.查询通用的方法，并返回，想要遍历用数组接收

```
/**
	 * 查詢通用的方法
	 * @param sql  sql語句
	 * @param paramList  sql語句的參數
	 * @return 返回查询的结果
	 */
	public List<Object[]> queryMethod(String sql,List<String> paramList) {
		
		con = getConection();
		
		PreparedStatement ps = null;
		
		List<Object[]> result = new ArrayList<Object[]>();
		try {
			ps = con.prepareStatement(sql);
			
			if (paramList != null && !paramList.isEmpty()) {
				
				for (int i = 0; i < paramList.size(); i++) {
					ps.setString(i+1, paramList.get(i));
				}
			}
			
			ResultSetMetaData rsmd = ps.getMetaData();
			
			// 获取每行列的总个数
			int columnCount = rsmd.getColumnCount();
			
			ResultSet rs = ps.executeQuery();
			
			while(rs.next()) {
				
				Object[] objects = new Object[columnCount];
				for (int i = 0; i < columnCount; i++) {
					
					// 获取每行的列名
					String columnName = rsmd.getColumnName(i+1);
					
					// 获取每行的列的值
					String columnValue = rs.getString(columnName);
					objects[i] = columnValue;
				}
				result.add(objects);	
			}
			rs.close();
			ps.close();
			con.close();
		} catch (SQLException e) {
			// TODO Auto-generated catch block
			e.printStackTrace();
		}
		return result;
	}
```

6.增，删，改通用方法，无需返回值

```
/**
	 * 新增修改删除通用方法
	 * @param sql 新增修改删除sql语句
	 * @param paramList 参数列表
	 */
	public void modifyMethod(String sql,List<String> paramList) {
		
		con = getConection();
		
		PreparedStatement ps = null;
		
		try {
			ps = con.prepareStatement(sql);
			
			if (paramList != null && !paramList.isEmpty()) {
				
				for (int i = 0; i < paramList.size(); i++) {
					ps.setString(i+1, paramList.get(i));
				}
			}
			//增，删，改用executeUpdate();
			ps.executeUpdate();
			
			ps.close();
			con.close();
		} catch (SQLException e) {
			// TODO Auto-generated catch block
			e.printStackTrace();
		}
		
	}
```

7.

```
					//new上俩个方法中的类，以便调用增加或准备查询方法
					Jdbcutil jdbc=new Jdbcutil();
					List<String> paramList = new ArrayList<String>();
					paramList.add(str);
					paramList.add(str1);
					paramList.add(str2);
					paramList.add(str3);
					//往tue插入数据
					如果是查询可以用数组接收
		//查询到的返回一个数组，然后遍历
List<Object[]> q=jdbc.zscg("insert into tue (sname,spswd,sspswd,email,ssname,ssex,sdate) values (?,?,?,?,?,?,?)", paramList);
		for(Object q1[]:q){
			for(Object q2:q1){
				System.out.println((String)q2+",   ");
			}
			System.out.println();
		}
```

返回

request

```
request.setAttribute("name",返回的值);
网页接收：${name}
```

response

```
response.getWriter().write(返回的值);

function kdown() {
		var xmlhttp;
		//1.判断浏览器类型
		if(window.XMLHttpRequest){
			xmlhttp=new XMLHttpRequest();
			
		}else{
			xmlhttp=new ActiveXObject("Microsoft.XMLHTTP");
		}
		//判断是否正常
		xmlhttp.onresdystatechange=function(){
			if(xmlhttp.readtState==4&&xmlhttp.status==200){
			//网页接收
				var q=xmlhttp.responseText;
				//处理
			}
		}
		//发送方式，地址，记忆是否异面
		xmlhttp.open("GET","${pageContext.request.contextPath }/ajsx_servlte",true);
		//发送
		xmlhttp.send();
		
		
	}
```

