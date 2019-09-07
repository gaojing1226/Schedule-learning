#### 一、HTTP简介
HTTP协议是Hyper Text Transfer Protocol（超文本传输协议）的缩写,是用于从万维网（WWW:World Wide Web ）服务器传输超文本到本地浏览器的传送协议。  
HTTP是一个基于TCP/IP通信协议来传递数据（HTML 文件, 图片文件, 查询结果等）。

#### 二、HTTP工作原理
HTTP协议工作于客户端-服务端架构上。浏览器作为HTTP客户端通过URL向HTTP服务端即WEB服务器发送所有请求。

HTTP三点注意事项：
- HTTP是无连接：无连接的含义是限制每次连接只处理一个请求。服务器处理完客户的请求，并收到客户的应答后，即断开连接。采用这种方式可以节省传输时间。  
- HTTP是媒体独立的：这意味着，只要客户端和服务器知道如何处理的数据内容，任何类型的数据都可以通过HTTP发送。客户端以及服务器指定使用适合的MIME-type内容类型。  
- HTTP是无状态：HTTP协议是无状态协议。无状态是指协议对于事务处理没有记忆能力。缺少状态意味着如果后续处理需要前面的信息，则它必须重传，这样可能导致每次连接传送的数据量增大。另一方面，在服务器不需要先前信息时它的应答就较快。

#### 三、HTTP消息结构
1. 客户端请求信息
请求行（请求方法、URL、协议版本）、请求头部（头部字段名、值）、空行、请求数据
2. 服务器响应信息
状态行、消息报头、空行和响应正文。

#### 四、HTTP请求方法
根据 HTTP 标准，HTTP 请求可以使用多种请求方法。  
HTTP1.0 定义了三种请求方法： GET, POST 和 HEAD方法。  
HTTP1.1 新增了六种请求方法：OPTIONS、PUT、PATCH、DELETE、TRACE 和 CONNECT 方法。  
其中GET POST较常用。

1. **GET**	请求指定的页面信息，并返回实体主体。  
2. **HEAD**	类似于 GET 请求，只不过返回的响应中没有具体的内容，用于获取报头
3. **POST**	向指定资源提交数据进行处理请求（例如提交表单或者上传文件）。数据被包含在请求体中。POST 请求可能会导致新的资源的建立和/或已有资源的修改。  
4. **PUT**	从客户端向服务器传送的数据取代指定的文档的内容。  
5. **DELETE**	请求服务器删除指定的页面。
6. **CONNECT**	HTTP/1.1 协议中预留给能够将连接改为管道方式的代理服务器。  
7. **OPTIONS**	允许客户端查看服务器的性能。  
8. **TRACE**	回显服务器收到的请求，主要用于测试或诊断。  
9. **PATCH**	是对 PUT 方法的补充，用来对已知资源进行局部更新 。

#### 五、HTTP状态码
1. HTTP状态码分类
HTTP状态码由三个十进制数字组成，第一个十进制数字定义了状态码的类型，后两个数字没有分类的作用。HTTP状态码共分为5种类型：
  ```js
    1  信息，服务器收到请求，需要请求者继续执行操作  
    2  成功，操作被成功接收并处理  
    3  重定向，需要进一步的操作以完成请求  
    4  客户端错误，请求包含语法错误或无法完成请求  
    5  服务器错误，服务器在处理请求的过程中发生了错误
  ```
  下面是常见的HTTP状态码：

  200 -  请求成功  
  301 -  资源（网页等）被永久转移到其它URL  
  404 -  请求的资源（网页等）不存在  
  500 -  内部服务器错误