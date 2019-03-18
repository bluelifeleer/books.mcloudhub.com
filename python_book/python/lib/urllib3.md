# urllib3库

### 安装

```
pip install urllib3
```

### 简单实例使用

```
imprt urllib3
http = urllib3.PoolManager()
r = http.request('GET', 'http://www.baidu.com/robots.txt')
r.status
r.data
```

##### 请求https报错的问题。

> 使用urllib3请求https时ssl警告的信息处理

* InsecureRequestWarning（不安全的请求警告）

> 如果在未启用证书验证的情况下向HTTPS URL发出请求，则会发生这种情况。 按照证书验证指南解决此警告。

* InsecurePlatformWarning（不安全的平台警告）

> 发生在具有过时ssl模块的Python 2平台上。这些较旧的ssl模块可能会导致某些不安全的请求在失败的情况下成功，并在失败请求失败的地方确保失败。按照pyOpenSSL指南解决此警告

* SNIMissingWarning（SNI失踪警告）

> 在早于2.7.9的Python 2版本上。这些旧版本缺乏SNI支持。这可能导致服务器显示客户端认为无效的证书。按照pyOpenSSL指南解决此警告。

###### 强烈建议不要进行未经验证的HTTPS请求，但是，如果您了解风险并希望禁用这些警告，则可以使用disable_warnings（）：

```
import urllib3
urllib3.disable_warnings()
```

##### [文档：https://urllib3.readthedocs.io/en/latest。](https://urllib3.readthedocs.io/en/latest/ 'https://urllib3.readthedocs.io/en/latest/')
##### [文档：https://urllib3.readthedocs.io/en/latest/user-guide.html。](https://urllib3.readthedocs.io/en/latest/user-guide.html 'https://urllib3.readthedocs.io/en/latest/user-guide.html')
