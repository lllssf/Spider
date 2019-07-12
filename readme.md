## 配料
1. Chrome 74, ChromeDrvier 74
2. python3.7 
3. 请求库：requests，selenium, aiohttp
4. 解析库：lxml, beautifulsoup4, pyquery
5. OCR识别库：tesseract-ocr 4.0，tesserocr2.4
6. 数据库：MySQL, MongoDB
7. python储存库：pymysql, pymongo, redis, redis-dump
8. web库：Flask, Tornado
9. 爬虫框架：Scrapy
10. 分布式爬虫：Docker

## 基础操作
### 1. urllib库
### 1.1 urllib.request模拟发送请求
 urllib.request.urlopen('URL', data=None, [timeout,]*, cafile=None, capath=None, cadefault=False, context=None)
```
import urllib.request
response = urllib.request.urlopen('https://www.baidu.com')
print(type(response))
```
得到response是一个HTTPResponse类型的对象，包含read(), getheader('name'), getheaders(), readinto(), fileno()等方法，以及msg, version, status, reason, debuglevel, closed等属性。\
若要传递data参数，要将其转码为 *byte* 类型
```
import urllib.parse
data = bytes(urllib.parse.urlencode({'key':'value}'), encode='utf8')
```
通过 *timeout* 可以设置对响应时间过长的网页跳过抓取：
```
import socket
import urllib.request
import urllib.error

try:
    response = urllib.request.urlopen('URL', timeout=10)
except urllib.error.URLError as e:
    if isinstance(e.reason, socket.timeout):
        print('Time Out!')
```
pass
