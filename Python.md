---
title: Python Note
tags: Python
---

[toc]

---
## Config
### Requirement
* Common
```
aniso8601==3.0.0
astroid==1.6.3
beautifulsoup4==4.6.0
bs4==0.0.1
certifi==2018.4.16
chardet==3.0.4
click==6.7
colorama==0.3.9
Flask==0.12.2
Flask-Cors==3.0.3
Flask-Markdown==0.3
Flask-RESTful==0.3.6
Flask-WTF==0.14.2
idna==2.6
isort==4.3.4
itsdangerous==0.24
Jinja2==2.10
lazy-object-proxy==1.3.1
lxml==4.2.1
Markdown==2.6.11
MarkupSafe==1.0
mccabe==0.6.1
numpy==1.14.2
pandas==0.22.0
pylint==1.8.4
python-dateutil==2.7.2
pytz==2018.4
requests==2.18.4
scipy==1.0.1
six==1.11.0
tushare==1.1.5
urllib3==1.22
Werkzeug==0.14.1
wrapt==1.10.11
WTForms==2.1
xlrd==1.1.0
iapws==1.2
```
* More  

```
pip install flask
pip install flask-markdown
pip install flask-cors
pip install xlrd
```

* For iapws 

```
scipy
lxml
```

* For tushare

```
pandas
requests
bs4
```

### Sublime-pylinter

```
pylint (然后把lib/site-packages/pylint写在pylint的path中)
```

## API
### 大小写转换
```
print(str.upper())          # 把所有字符中的小写字母转换成大写字母
print(str.lower())          # 把所有字符中的大写字母转换成小写字母
print(str.capitalize())     # 把第一个字母转化为大写字母，其余小写
print(str.title())          # 把每个单词的第一个字母转化为大写，其余小写 
```
### 类型转换
```
int('12')  #10进制string转化为int
int('12', 16) #16进制string转化为int
str(18) #int转化为10进制string
hex(18) #int转化为16进制string
```
### 时间与日期
- 一般用法
```
import time;  # 引入time模块
ticks = time.time()
print "当前时间戳为:", ticks
#1459994552.51
localtime = time.localtime(time.time())
#本地时间为 : time.struct_time(tm_year=2016, tm_mon=4, tm_mday=7, tm_hour=10, tm_min=3, tm_sec=27, tm_wday=3, tm_yday=98, tm_isdst=0)
print time.strftime("%Y-%m-%d %H:%M:%S", time.localtime()) 
# 2016-03-20 11:45:39
print time.strftime("%a %b %d %H:%M:%S %Y", time.localtime()) 
# Sat Mar 28 22:24:24 2016

```
- 更多格式

```
    %y 两位数的年份表示（00-99）
    %Y 四位数的年份表示（000-9999）
    %m 月份（01-12）
    %d 月内中的一天（0-31）
    %H 24小时制小时数（0-23）
    %I 12小时制小时数（01-12）
    %M 分钟数（00=59）
    %S 秒（00-59）
    %a 本地简化星期名称
    %A 本地完整星期名称
    %b 本地简化的月份名称
    %B 本地完整的月份名称
    %c 本地相应的日期表示和时间表示
    %j 年内的一天（001-366）
    %p 本地A.M.或P.M.的等价符
    %U 一年中的星期数（00-53）星期天为星期的开始
    %w 星期（0-6），星期天为星期的开始
    %W 一年中的星期数（00-53）星期一为星期的开始
    %x 本地相应的日期表示
    %X 本地相应的时间表示
    %Z 当前时区的名称
    %% %号本身

```
- 获取日历

```
#!/usr/bin/python
# -*- coding: UTF-8 -*-

import calendar

cal = calendar.month(2016, 1)
print "以下输出2016年1月份的日历:"
print cal;
#January 2016
#Mo Tu We Th Fr Sa Su
#             1  2  3
# 4  5  6  7  8  9 10
#11 12 13 14 15 16 17
#18 19 20 21 22 23 24
#25 26 27 28 29 30 31
```
- DateTime

```
#!/usr/bin/python
# -*- coding: UTF-8 -*-

import datetime
i = datetime.datetime.now()
print ("当前的日期和时间是 %s" % i)
print ("ISO格式的日期和时间是 %s" % i.isoformat() )
print ("当前的年份是 %s" %i.year)
print ("当前的月份是 %s" %i.month)
print ("当前的日期是  %s" %i.day)
print ("dd/mm/yyyy 格式是  %s/%s/%s" % (i.day, i.month, i.year) )
print ("当前小时是 %s" %i.hour)
print ("当前分钟是 %s" %i.minute)
print ("当前秒是  %s" %i.second)
```
## 相关资源




