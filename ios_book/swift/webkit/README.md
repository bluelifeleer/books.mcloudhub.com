#### WebKit

##### Display web content in windows. Implement browser features such as following user-activated links, managing a back-forward list, and managing a history of recently visited pages.
##### 在窗口中显示web内容。实现浏览器特性，例如跟踪用户激活的链接、管理后向列表和管理最近访问的页面的历史记录。

##### WebKit provides a set of classes to display web content in windows, and implements browser features such as following links when clicked by the user, managing a back-forward list, and managing a history of pages recently visited. WebKit greatly simplifies the complicated process of loading webpages—that is, asynchronously requesting web content from an HTTP server where the response may arrive incrementally, in random order, or partially due to network errors. WebKit also simplifies the process of displaying that content which can contain various MIME types, and compound frame elements each with their own set of scroll bars.
##### WebKit提供了一组类来在windows中显示web内容，并实现了浏览器特性，如用户单击后跟随链接、管理后退列表和管理最近访问的页面历史。WebKit极大地简化了加载web页面的复杂过程——也就是说，异步地从HTTP服务器请求web内容，响应可能以增量方式、随机顺序或部分由于网络错误而到达服务器。WebKit还简化了显示内容的过程，这些内容可以包含各种MIME类型，并使用各自的滚动条组合框架元素。

###### 提示

###### Call WebKit functions and methods only from your app’s main thread or main dispatch queue.
###### 只从应用程序的主线程或主调度队列调用WebKit函数和方法。


重要的