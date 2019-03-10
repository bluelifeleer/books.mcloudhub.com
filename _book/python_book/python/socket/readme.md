### Python 中的 socket

#### 描述
> Python 接口是将 Unix 系统调用和套接字库接口直接音译为 Python 的面向对象风格:socket()函数返回一个套接字对象，其方法实现各种套接字系统调用。参数类型比 C 接口中的要高级一些:与 Python 文件上的 read()和 write()操作一样，接收操作上的缓冲区分配是自动的，发送操作上的缓冲区长度是隐式的。

### socket.socket([family[,type[,protocol]]])

* ##### family:可以是AF_UNIX（UNIX域，用于同一机器上的进程通信），也可以是AF_INET（对于IPV$协议的TCP和UDP）或AF_INET6（对于IPV6）。
* ##### type:套接字类型可以根据面向连接和非连接分为SOCKET_STREAM（流套搂字）或SOCKET_DGRAM（数据报文套接字）
* ##### protocol:一般不填，默认为0。

#### family 参数指定调用者期待返回的套接口地址结构类型。family的值包括3种：

* ##### 如果指定AF_INET，函数就不能返回任何IPV6相关的地址信息。
* ##### 如果仅指定AF_INET6,就不能返回任何IPV4相关的地址信息。
* ##### AF_UNSPEC意味着函数返回的是适用于指定主机名和服务名且适合任何协议族的地址。
* ##### 如果某个主机既有AAAA记录（IPV6）地址，又有A记录（IPV4）的地址，那么AAAA记录高尔夫作为socketaddr_in6结构返回，而A记录作为socketaddr_in结构返回。
* ##### AF_INET6用于IPV6系统，AF_INET和PF_INET用于IPV4系统。 
* ##### AF表示ADDRESS FAMILY地址族。
* ##### PF表示PROTOCOL FAMILY协议族。

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
|  recv()  |  接收一定字节的数据，bufsize指定要接收的最大数据量。  |  Buffer  |
|  send()  |  发送一定字节的数据  |  Buffer  |
|  sendall()  |  完整发送TCP数据，将string中的数据发送到连接的套接字，返回的值是要发送的字节量，成功返回none，失败抛出异常。  |  string  |
|  recvform()  |  接收UDP数据，与recv()类似，返回值是(data,address)。其中data是包含接收数据的字符串，address是发送数据的套接字地址。  |    |
|  sendto()  |  发送UDP数据，将数据发送到套接字，address是形式为(ipaddr,port)的元组，指定远程地址。返回是发送的字节数  |    |
|  getpeername()  |  返回连接套接字的远程地址。返回通常是元组(ipaddr,port)  |    |
|  getsocketname()  |  返回套接字的地址。通常是一个元组(ipaddr,port)  |    |
|  setsockeopt(level,optname,value)  |  设置给定套接字选项值  |    |
|  getsockeopt(level,optname[.buflen])  |  返回套接字选项值  |    |
|  settimeout(timeout)  |  设置套接字操作的超时，timout是一个浮点数，单位是秒。值为none表示没有超时，一般超时应该在创建套接字时设置，因为可能用于连接操作，如(connect())  |    |
|  gettimeout(timeout)  |  返回当前超时的值，单位是秒，如果没有设置超时就返回none  |    |
|  fileno()  |  返回套接字的文件描述符  |    |
|  setblocking(flag)  |  如果flag为0,就将套接籽设为非阻塞模式，否则将套接字设为阻塞模式（默认值）。非阻塞模式下，如果调用recv()没有发现任何数据，或send()调用无法立即发送数据，就会引起socket.error异常。  |    |
|  makefile  |  创建一个与该套接字相关联的文件  |    |
|  connect()  |  连接 socket 服务器  |  rouserce  |
|  connect_ex()  |  connect()函数的扩展版本，出错时返回出错码而不是招聘异常。  |    |
|  close()  |  关闭 socket 连接  |  rouserce  |
|  accept()  |  被动接收TCP客户端的连接，等待连接的到来  |  。  |

###### 更多方法及使用请查看下面连接：
[参考连接：https://docs.python.org/3.5/library/socket.html?highlight=socket#module-socket](https://docs.python.org/3.5/library/socket.html?highlight=socket#module-socket 'https://docs.python.org/3.5/library/socket.html?highlight=socket#module-socket')