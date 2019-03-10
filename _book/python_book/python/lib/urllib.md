### urllib库

> urllib是一个处理url网络请求的包。

#### 导入urllib库

```
import urllib
import urllib.request
```

#### request

```
urllib.request.urlopen(url, data=None, [timeout, ]*, cafile=None, capath=None, cadefault=False, context=None)
```

#### request方法

* ##### request.OpenerDirector
* ##### request.BaseHandler
* ##### request.HTTPDefaultErrorHandler
* ##### request.HTTPRedirectHandler
* ##### request.HTTPCookieProcessor(cookiejar=None)
* ##### request.ProxyHandler(proxies=None)
* ##### request.HTTPPasswordMgr
* ##### request.HTTPPasswordMgrWithDefaultRealm
* ##### request.HTTPPasswordMgrWithPriorAuth
* ##### request.AbstractBasicAuthHandler(password_mgr=None)
* ##### request.HTTPBasicAuthHandler(password_mgr=None)
* ##### request.ProxyBasicAuthHandler(password_mgr=None)
* ##### request.AbstractDigestAuthHandler(password_mgr=None)
* ##### request.HTTPDigestAuthHandler(password_mgr=None)
* ##### request.ProxyDigestAuthHandler(password_mgr=None)
* ##### request.HTTPHandler
* ##### request.HTTPSHandler(debuglevel=0, context=None, check_hostname=None)
* ##### request.FileHandler
* ##### request.DataHandler
* ##### request.FTPHandler
* ##### request.CacheFTPHandler
* ##### request.UnknownHandler
* ##### request.HTTPErrorProcessor

#### respons方法

* ##### respons.getHeaders()  获取请求头信息
* ##### respons.read()	获取返回的内容
* ##### respons.read().decode('utf-8')	返回的内容解析为```utf-8```编码
* ##### respons.getHeader('key')	获取一个指定的信息
* ##### respons.status 	获取请求状态码

#### 实例：

```
import urllib
import urllib.request
import ssl

opener = urllib.request.build_opener()

UA = ("user-agen", "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_13_6) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/69.0.3497.92 Safari/537.36")

opener.addheaders = [UA]

urllib.request.install_opener(opener)

context = ssl._create_unverified_context()

data = urllib.request.urlopen("http://www.jd.com", context=context).read().decode("utf-8", "ignore")

print(data)
```

#### error

```
svfsfvsfvf
```

#### parse可以解析url的各个部分

```
import urllib
import urllib.parse
from urllib.parse import urlparse
o = urlparse("https://www.jd.com")
print(o) #ParseResult(scheme='https', netloc='www.jd.com', path='', params='', query='', fragment='')
```


#### robotparser