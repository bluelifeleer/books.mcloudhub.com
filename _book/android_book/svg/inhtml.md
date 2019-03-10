### 在HTML中引入svg,可以使用以下三种方式

* 使用```<svg>```标签引入

> ```<embed>``` 标签被所有主流的浏览器支持，并允许使用脚本。
> 注释：当在 HTML 页面中嵌入 SVG 时使用 ```<embed>``` 标签是 Adobe SVG Viewer 推荐的方法！然而，如果需要创建合法的 XHTML，就不能使用 ```<embed>```。任何 HTML 规范中都没有 ```<embed>``` 标签。

#### 语法：

```
 <embed src="rect.svg" width="300" height="100" type="image/svg+xml" pluginspage="http://www.adobe.com/svg/viewer/install/" />
```


* 使用```<object>```对象引入

> <object> 标签是 HTML 4 的标准标签，被所有较新的浏览器支持。它的缺点是不允许使用脚本。
> 注释：假如您安装了最新版本的 Adobe SVG Viewer，那么当使用 <object> 标签时 SVG 文件无法工作（至少不能在 IE 中工作）！


#### 语法：

```
<object data="rect.svg" width="300" height="100" type="image/svg+xml" codebase="http://www.adobe.com/svg/viewer/install/" />
```

* 使用```<iframe>```引入

> ```<iframe>``` 标签可工作在大部分的浏览器中。
> 语法：


```
<iframe src="rect.svg" width="300" height="100"></iframe>
```