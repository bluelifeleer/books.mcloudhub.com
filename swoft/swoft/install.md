# Swoft安装

### composer安装

> 对于```composer```不清楚的可以查看[这里](https://pkg.phpcomposer.com/ 'https://pkg.phpcomposer.com/')。

```
componse create-project swoft/swoft project_name
```

### 手动安装

```
git clone https://github.com/swoft-cloud/swoft
cd swoft
composer install --no-dev # 不安装 dev 依赖会更快一些
cp .env.example .env
vim .env # 根据需要调整启动参数
```

### Docker方式安装

```
docker run -p 80:80 swoft/swoft
```

### Docker-Compose 安装

```
git clone https://github.com/swoft-cloud/swoft
cd swoft
docker-compose up
```

[文档连接：https://doc.swoft.org/master/zh-CN/quickstart/install.html](https://doc.swoft.org/master/zh-CN/quickstart/install.html 'https://doc.swoft.org/master/zh-CN/quickstart/install.html')