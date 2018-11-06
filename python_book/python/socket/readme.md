### Python 中的 socket

#### 描述
> Python 接口是将 Unix 系统调用和套接字库接口直接音译为 Python 的面向对象风格:socket()函数返回一个套接字对象，其方法实现各种套接字系统调用。参数类型比 C 接口中的要高级一些:与 Python 文件上的 read()和 write()操作一样，接收操作上的缓冲区分配是自动的，发送操作上的缓冲区长度是隐式的。

#### 使用方法

###### 创建一个 socket 服务端

```
import socket
bufsize = 1024
ipAddr = ('127.0.0.1', 9999)
# 创建一个socket服务端
socketServer = socket.socket(socket.AF_INET,socket.SOCK_STREAM,0)
socketServer.bind(ipAddr)
socketServer.listen(5)
conn,addr = socketServer.accept()
if conn:
  while True:
    data = socket.recv(bufsize).decode("utf-8")
    print("client post data : %s " %(str(data)))
    socketServer.send(bytes(data,bufsize)).encode("utf-8")
socketServer.close()
```
###### 创建一个 socket 客户端

```
import socket
ipAddr = ('127.0.0.1', 9999)
client = socket.socket()
conn = client.connect()
print("socket service connection ....")

while True:
    input_str = input(">>>")
    if len(input_str) == 0: continue
    client.send(bytes(input_str,"utf-8"))
    respones = client.recv(1024)
    print('service respones %s' %(respones.decode("utf-8")))
client.close()
```

#### Socket 中的方法跟函数

|  函数  |  描述  |  参数  |
|----|----|----|
|  socket()  |  初始化一个 socket 实例  |  rouserce  |
|  bind()  |  绑定一个 IP:端口  |  参数是一个包含 ip 跟端口元组，如：ipAddr = ('127.0.0.1', 9999)  |
|  listen()  |  监听连接的个数  |  Number  |
|  recv()  |  接收一定字节的数据  |  Buffer  |
|  send()  |  发送一定字节的数据  |  Buffer  |
|  connect()  |  连接 socket 服务器  |  rouserce  |
|  close()  |  关闭 socket 连接  |  rouserce  |

###### 更多方法及使用请查看下面连接：
[参考连接：https://docs.python.org/3.5/library/socket.html?highlight=socket#module-socket](https://docs.python.org/3.5/library/socket.html?highlight=socket#module-socket 'https://docs.python.org/3.5/library/socket.html?highlight=socket#module-socket')