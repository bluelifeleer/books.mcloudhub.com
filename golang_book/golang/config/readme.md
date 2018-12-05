### Golang开发环境配置

#### 添加环境变量，修改```/etc/profile```。

```
vim /etc/profile

export GOROOT=/usr/local/go
export GOPATH=/home/project/go
export PATH=$PATH:$GOROOT/bin:$GOPATH/bin
```

#### 刷新```/etc/profile```。

```
source /etc/profile
```

### 创建开发目录

```
mkdir -p $GOPATH/bin
mkdir -p $GOPATH/src
mkdir -p $GOPATH/pkg
```

### 开发第一个程序```Hello word```。

* 创建工作目录

```
mkdir $GOPATH/src/github.com/user/hello
```

* 创建程序文件

```
vim $GOPATH/src/github.com/user/hello/hello.go
```

* 编辑程序代码

```
pagkage main

import "fmt"

func main() {
	fmt.Printf("hello word .\n")
}
```

* 编译```hello Word```。

```
cd $GOPATH/src/github.com/user/hello
go install

// or 

go install $GOPATH/src/github.com/user/hello
```

###### 编译后的可执行文件在```$GOPATH/bin```目录中

* 执行编译后的程序

```
./$GOPATH/bin/hello
```

###### 输出```hello word .```