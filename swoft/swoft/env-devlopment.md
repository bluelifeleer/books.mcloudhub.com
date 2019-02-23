# Swoft环境搭建

### 环境必要的依赖需求：

* 安装PHP并且版本至少 >7.0，推荐 7.1+
* 安装php包管理器 composer
* 安装redis的异步客户端 hiredis
* 连接迭代器依赖 pcre 库
* 安装php扩展swoole, 并且版本至少 >=2.1
* * swoole开启协程和异步redis
* 其他需要安装和启用的php扩展有：PDO

### 有冲突扩展：

##### 面列出一些已知的和swoole有冲突的php扩展，请使用swoft时不要安装或禁用它们：

* xdebug
* xhprof
* blackfire
* zend
* trace
* uopz

[文档连接：https://doc.swoft.org/master/zh-CN/quickstart/enviroment.html](https://doc.swoft.org/master/zh-CN/quickstart/enviroment.html 'https://doc.swoft.org/master/zh-CN/quickstart/enviroment.html')