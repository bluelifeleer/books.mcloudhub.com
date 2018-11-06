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