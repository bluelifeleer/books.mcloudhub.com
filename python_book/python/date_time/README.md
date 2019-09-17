### Python中的时间和日期

###### Python中与时间处理有关的模块包括```time```、```datatime```、```calendar```，通常用时间戳、格式化的时间字符串和元组三种方式时间。


#### 时间戳

> 时间戳（）表示从1970年1月1日00时00分00秒开始按秒计算的偏移量，也就是从1970年1月1日00时00分00秒（北京时间1970年1月1日08时00分00秒）到现在的总毫秒数

时间戳是一个经加字后形成的凭证文档，包括3部分：

* 1：需加时间戳的文件的摘要(digest)。
* 2：DTS收到文件的日期和时间。
* 3：DTS的数字签名。

一般来说时间戳生产的过程为：用户首先将需要加时间戳的文件用Hash编码加字形成摘要，然后将该摘要发送到DTS，DTS加入收到文件摘要的日期和时间信息后再对该文件加字（数字签名），最后发送回客户。
书面签署文件的时间由签署人自己写上的，而数字时间戳是由谁单位DTS添加的，以DTS收到文件的时间为依据。

##### 时间格式化符号

|  格式  |  含意  |  备注  |
|----|----|----|
|  %a  |  本地简化星期名称  |    |
|  %A  |  本地完整星期名称  |    |
|  %b  |  本地简化月份  |    |
|  %B  |  本地完整月份  |    |
|  %c  |  本地相应的时间和日期表示  |    |
|  %d  |  一个月中的第几天（01~31）  |    |
|  %H  |  一天中的第几个小时（24小时制，00~23）  |    |
|  %I  |  第几个小时（12小时制，01~12）  |    |
|  %j  |  一年中的第几天（01~366）  |    |
|  %m  |  月份（01~12）  |    |
|  %M  |  分钟数（00~59）  |    |
|  %p  |  本地AM或PM相应  |  1  |
|  %S  |  秒（01~61  |  2  |
|  %U  |  一年中的星期数，（取值00~53，星期天为一星期的开始，第一个星期天之前的所有天数都放在第0周  |  3  |
|  %w  |  一个星期中的第几天（0~6），0是星期天  |  3  |
|  %W  |  和%U基本相同，不同的是%W以星期一为一个星期的开始  |    |
|  %x  |  本地相应日期  |    |
|  %X  |  本地相应时间  |    |
|  %y  |  去年世纪的年份（00~99）  |    |
|  %Y  |  完整的年份  |    |
|  %Z  |  时区的名字（如果不存在为空字符串）  |    |
|  %%  |  %字符  |  .  |

###### 表格中备注含意：

* 1：%P只有与%I配合才有效果。
* 2：文档中强调确实是```0~61```，而不是59，闰年秒占两秒。
* 3：当使用strptime()函数时只有这一年的周数和天数确定时%U和%W才会被计算。

##### 使用datetime获取年、月、日

```
from datetime import date
today = date.today()
today.year // 年
today.month // 月
today.day // 日期
today.weekday() // 星期
```

#### 使用datetime获取格式化时间

```
>>> from datetime import datetime
>>> now = datetime.now()
>>> now.year
2019
>>> now.month
9
>>> now.day
18
>>> now.hour
2
>>> now.minute
9
>>> now.second
6
>>> now.microsecond
422358
```

##### struct_time 元组

struct_time元组共有9个元素：年、月、日、时、分、秒、一年中第几周、一个中第几天、是否为夏令时。

时间元组

|  序号  |  属性  |  字段  |  值  |
|----|----|----|----|
|  0  |  tm_year  |  4位数年  |  如2008  |
|  1  |  tm_mon  |  月  |  1~12  |
|  2  |  tm_mday  |  日  |  1~31  |
|  3  |  tm_hour  |  小时  |  0~23  |
|  4  |  tm_min  |  分钟  |  0~59  |
|  5  |  tm_sec  |  秒  |  0~61（60或61是闰秒）  |
|  6  |  tm_wday  |  一周的第几天  |  0~6（0是周一）  |
|  7  |  tm_yday  |  一年的第几日  |  1~366（儒略历）  |
|  8  |  tm_isdst  |  夏令时  |  -1、0、1、-1是否决定是夏令时的标志  |

##### time()函数

> time()函数用于返回当前时间的时间戳（1970年01月01日08时00分00秒到现在的浮点数）。

语法：

```
time.time()
```

实例：

```
#! /usr/bin/python
# -*-coding:UTF-8-*-
import time
print("当前时间戳： %f" %time.time())
当前时间戳： 1542299280.144668
```

#### 使用time模块输出格式化时间

```
import time
time.strftime("%y-%m-%d")
# '19-09-18'
time.strftime("%d/%m/%y")
# '18/09/19'
time.strftime("%y-%m-%d %H:%M:%S")
# '19-09-18 02:06:12'
```

##### localtime()函数

> 格式化时间戳为本地时间，如果secs未传入参数，就以当前时间为标准转换。

语法：

```
time.localtime([secs])
```

实例：

```
print("localtime:",time.localtime())
localtime: time.struct_time(tm_year=2018, tm_mon=11, tm_mday=16, tm_hour=0, tm_min=31, tm_sec=0, tm_wday=4, tm_yday=320, tm_isdst=0)
```

##### gmtime([secs])函数

##### asctime([t])函数

##### ctime([secs])函数

##### sleep(secs)函数

> 用于推迟调用线程的运行，通过secs（秒数）指定进程的挂起时间。

语法：

```
time.seelp(secs)
```
实例：

```
print("start: %s" %time.ctime())
time.seelp(3)
print("end: %s" %time.ctime())
```

##### clock()函数

##### strtime()函数

##### strptime()函数

#### datetime模块

##### today()

##### now([tz])

##### datetime.datetime.utcnow()

##### fromtimestamp()

##### utcfromtimestamp()

##### strptime()

##### strftime()

#### 日历模块

##### calendar.calendar(year,w=2,l=1,c=6)

##### calendar.firsttweekday()

##### calendar.isleap(year)

##### calendar.leapdays(y1,y2)

##### calendar.month(year,month,w=2,l=1)

##### calendar.monthcalendar(year,month)

##### calendar.monthrange(year,month)

##### calendar.prcal(year,w=2,l=1,c=6)

##### calendar.prmonth(year,month,w=2,l=1)

##### calendar.setfirstweekday(weekday)

##### calendar.timegm(tupletime)

##### calendar.weekday(year,month,day)