### JSP知识总结

#### `JSP简介`

1. 什么是Java Server Pages?

JSP全称Java Server Pages，是一种动态网页开发技术。它使用JSP标签在HTML网页中插入Java代码。标签通常以<%开头以%>结束。
JSP是一种Java servlet，主要用于实现Java web应用程序的用户界面部分。网页开发者们通过结合HTML代码、XHTML代码、XML元素以及嵌入JSP操作和命令来编写JSP。

JSP通过网页表单获取用户输入数据、访问数据库及其他数据源，然后动态地创建网页。

JSP标签有多种功能，比如访问数据库、记录用户选择信息、访问JavaBeans组件等，还可以在不同的网页中传递控制信息和共享信息。

2. 为什么使用JSP？

JSP程序与CGI程序有着相似的功能，但和CGI程序相比，JSP程序有如下优势：
* 性能更加优越，因为JSP可以直接在HTML网页中动态嵌入元素而不需要单独引用CGI文件。
* 服务器调用的是已经编译好的JSP文件，而不像CGI/Perl那样必须先载入解释器和目标脚本。
* JSP基于Java Servlets API，因此，JSP拥有各种强大的企业级Java API，包括JDBC，JNDI，EJB，JAXP等等。
* JSP页面可以与处理业务逻辑的servlets一起使用，这种模式被Java servlet 模板引擎所支持。
最后，JSP是Java EE不可或缺的一部分，是一个完整的企业级应用平台。这意味着JSP可以用最简单的方式来实现最复杂的应用。

3. JSP的优势

以下列出了使用JSP带来的其他好处：

* 与ASP相比：JSP有两大优势。首先，动态部分用Java编写，而不是VB或其他MS专用语言，所以更加强大与易用。第二点就是JSP易于移植到非MS平台上。
* 与纯 Servlets相比：JSP可以很方便的编写或者修改HTML网页而不用去面对大量的println语句。
* 与SSI相比：SSI无法使用表单数据、无法进行数据库链接。
* 与JavaScript相比：虽然JavaScript可以在客户端动态生成HTML，但是很难与服务器交互，因此不能提供复杂的服务，比如访问数据库和图像处理等等。
* 与静态HTML相比：静态HTML不包含动态信息。

##### JSP / Velocity / FreeMarker对比
* JSP -> Velocity -> FreeMarker
    * JSP
        * 优点：
            1. 支持好。官方背书，标签库众多，支持JSP标签, 支持EL表达式语言, 功能强大，可以写JAVA代码
            2. 方便开发调试。
        * 缺点：
            1. 破坏了mvc结构
            2. jsp需要编译成class文件执行
    * Velocity: Apache出品，最早用于替代jsp的模板语言
        * 优点：
            1. 可以实现严格的mvc分离
            2. 据说性能比jsp要好一些
            3. 简单易学
        * 缺点：
            1. 第三方标签库少
            2. 难调试
            3. 对jsp标签支持不好
    * FreeMarker： Apache出品
        * 优点：
            1. 可以实现严格的mvc分离
            2. 内置常用功能强大，使用方便
            3. 对jsp标签支持良好
        * 缺点：
            1. 第三方标签库没有jsp多
            2. 难调试

4. 使用JSP的痛点
* 无法做到真正的动静分离。动态资源（JSP中内嵌的JAVA代码）和静态资源（HTML/CSS）耦合在一起，服务器压力大，一旦服务器不稳定，前后端会一起宕机，用户体验差。
* JSP必须要在支持JAVA的Web服务器里运行。对于一些纯静态的资源如图片/CSS/JS等，无法使用Nginx，性能提不上来。
* 第一个请求会比较慢。第一次请求JSP时，需要在web服务器中编译成servlet。
* 效率没有直接使用html高。每次请求jsp都是访问servlert再用输出流输出html页面。
* JSP本身时同步加载的，页面结构复杂的话，响应会慢。

#### `JSP结构`

1. JSP处理流程

JSP处理
以下步骤表明了Web服务器是如何使用JSP来创建网页的：

* 就像其他普通的网页一样，您的浏览器发送一个HTTP请求给服务器。
* Web服务器识别出这是一个对JSP网页的请求，并且将该请求传递给JSP引擎。通过使用URL或者.jsp文件来完成。
* JSP引擎从磁盘中载入JSP文件，然后将它们转化为servlet。这种转化只是简单地将所有模板文本改用println()语句，并且将所有的JSP元素转化成Java代码。
* JSP引擎将servlet编译成可执行类，并且将原始请求传递给servlet引擎。
* Web服务器的某组件将会调用servlet引擎，然后载入并执行servlet类。在执行过程中，servlet产生HTML格式的输出并将其内嵌于HTTP response中上交给Web服务器。
* Web服务器以静态HTML网页的形式将HTTP response返回到您的浏览器中。
* 最终，Web浏览器处理HTTP response中动态产生的HTML网页，就好像在处理静态网页一样。

一般情况下，JSP引擎会检查JSP文件对应的servlet是否已经存在，并且检查JSP文件的修改日期是否早于servlet。如果JSP文件的修改日期早于对应的servlet，那么容器就可以确定JSP文件没有被修改过并且servlet有效。这使得整个流程与其他脚本语言（比如PHP）相比要高效快捷一些。

总的来说，JSP网页就是用另一种方式来编写servlet而不用成为Java编程高手。除了解释阶段外，JSP网页几乎可以被当成一个普通的servlet来对待。


#### `JSP生命周期`
#### `JSP语法`
#### `JSP指令`
#### `JSP动作元素`
#### `JSP隐式对象`
#### `JSP客户端请求`
#### `JSP服务端响应`
#### `JSP HTTP状态码`
#### `JSP表单处理`
#### `JSP过滤器`
#### `JSP Coolies处理`
#### `JSP Session`
#### `JSP文件上传`
#### `JSP日期处理`
#### `JSP页面重定向`
#### `JSP点击量统计`
#### `JSP自动刷新`
#### `JSP发送邮件`
#### `JSP标准标签库JSTL`
#### `JSP连接数据库`
#### `JSP XML数据处理`
#### `JSP JavaBean`
#### `JSP自定义标签`
#### `JSP表达式语言`
#### `JSP异常处理`
#### `JSP调试`
#### `JSP国际化`
