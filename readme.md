# 爬虫
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
1. urllib.request.urlopen('URL', data=None, [timeout,]*, cafile=None, capath=None, cadefault=False, context=None)
```
import urllib.request
response = urllib.request.open('https://www.baidu.com')
print(type(response))
```
得到response是一个HTTPResponse类型的对象，包含read(), getheader('name'), getheaders(), readinto(), fileno()等方法，以及msg, version, status, reason, debuglevel, closed等属性。
