#### WKWebView

#### A WKWebView object displays interactive web content, such as for an in-app browser. You can use the WKWebView class to embed web content in your app. To do so, create a WKWebView object, set it as the view, and send it a request to load web content.
#### WKWebView对象显示交互式web内容，例如应用程序内浏览器。您可以使用WKWebView类在应用程序中嵌入web内容。为此，创建一个WKWebView对象，将其设置为视图，并向其发送一个请求来加载web内容。

> 提示

> Starting in iOS 8.0 and OS X 10.10, use WKWebView to add web content to your app. Do not use UIWebView or WebView.

> 从iOS 8.0和OS X 10.10开始，使用WKWebView将web内容添加到应用程序中。不要使用UIWebView或WebView。


#### 说明

#### After creating a new WKWebView object using the init(frame:configuration:) method, you need to load the web content. Use the loadHTMLString(_:baseURL:) method to begin loading local HTML files or the load(_:) method to begin loading web content. Use the stopLoading() method to stop loading, and the isLoading property to find out if a web view is in the process of loading. Set the delegate property to an object conforming to the WKUIDelegate protocol to track the loading of web content. See Listing 1 for an example of creating a WKWebView programmatically.

#### 实例

```
import UIKit
import WebKit
class ViewController: UIViewController, WKUIDelegate {
    
    var webView: WKWebView!
    
    override func loadView() {
        let webConfiguration = WKWebViewConfiguration()
        webView = WKWebView(frame: .zero, configuration: webConfiguration)
        webView.uiDelegate = self
        view = webView
    }
    override func viewDidLoad() {
        super.viewDidLoad()
        
        let myURL = URL(string: "https://www.apple.com")
        let myRequest = URLRequest(url: myURL!)
        webView.load(myRequest)
    }}
```