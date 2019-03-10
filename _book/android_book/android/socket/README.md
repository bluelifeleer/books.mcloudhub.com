### Android中Socket数据通信

##### 网络上两个程序通信通过一个双向的通讯连接实现数据的交换，双向链路一端称为一个Socket。Socket通常用来实现一个客户端跟服务端的连接。Socket是 TCP/IP中的一个非常流行的数据传输方式，一个Scoket由一个IP地址和一个端口号唯一确定。但是Socket所支持的协议各类也不止 TCP/IP 一种，因此两者之间也没有必然的联系。在Java环境下，Socket编程主要是指基于TCP/IP 的网络编程。

* 1：Socket的通信流程
* * ###### Server(服务)端Listen(监听)某个端口是否有连接请求，Client(客户)端向Server端发出Connect(连接)请求，Server端向Client发回Accept(接收)消息。一个连接就建立起来了，Server端和Client端都可以通过Send、Write等方法与对方通信。

	* 1）创建Socket
	* 2）打开连接到Socket的输入/输出流
	* 3）按照一定的协议对Socket进行读/写操作
	* 4）关闭Socket

* 2：Socket创建
* * ##### 在Java网络编程应用中，在包java.net中提供了两个类Socket和ServerSocket，分别用来表示双向连接和客户端和服务商品，其中包含了如下的构造方法：

	* Socket(InteAddress address, int port)
	* Socket(InteAddress address, int port, boolean stream)
	* Socket(String host, int port)
	* Socket(String host, int port, boolean stream)
	* Socket(SocketImpl impl)
	* Socket(String host, int port, InteAddress localHost, int localPort)
	* Socket(InteAddress address, int port, InteAddress localAddr, int localPort)
	* ServerSocket(int port)
	* ServerSocket(int port, int backlog)
	* ServerSocket(int port, int backlog, InteAddress bindAddr)

* * ##### 参数介绍
|  名称  |  描述  |  值  |
|----|----|----|
|  InteAddress address  |    |    |
|  int port  |    |    |
|  boolean stream  |    |    |
|  String host  |    |    |
|  SocketImpl impl  |    |    |
|  int localPort  |    |    |
|  InteAddress localHost  |    |    |
|  int backlog  |    |    |
|  InteAddress binAddr  |    |    |

* 3：使用ServeletSocket
* 4：使用Socket