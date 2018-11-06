### Mysql-Python

### 安装

```
pip install MySQL-python
```

### 实例

```
import mysql.connector as mariadb

connector = mariadb.connect(user="",password="",database="")

cursor = connector.cursor()

cursor.execute(sql)

connector.close()
```


### 异常处理

mariadb.Error

```
try :
	pass
mariadb.Error as error :
	# handle error code
	pass
```
##### 注：在python中操作mysql数据库是通过游标去操作的跟java中一样。

### 文档

[https://www.python.org/dev/peps/pep-0249/#introduction](https://www.python.org/dev/peps/pep-0249/#introduction 'https://www.python.org/dev/peps/pep-0249/#introduction')

[https://mariadb.com/resources/blog/how-connect-python-programs-mariadb](https://mariadb.com/resources/blog/how-connect-python-programs-mariadb 'https://mariadb.com/resources/blog/how-connect-python-programs-mariadb')