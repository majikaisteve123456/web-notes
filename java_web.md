#深入Web请求过程  
----
互联网的网络架构已经从传统的C/S架构转变为更加方便、快捷的B/S架构  
1. 客户端使用统一的浏览器，由于浏览器具有统一性，不需要特殊的配置和网络连接  
2. 服务端（server）基于统一的http。 和传统的C/S架构使用自定义的应用层协议不同，B/S架构使用的都是统一的HTTP.基于Http的应用服务器就有很多，这些服务器可直接拿来使用，不需要服务开发者单独来使用。  

 

##B/S 网路架构概述
B/S网络架构从前端到后端都得到简化，都基于统一的应用层协议Http来交互数据，与大多数传统的C/S互联网应用程序采用的长连接的交互模式不同，Http采用无状态的短链接的通信方式，通常情况下，一次请求就完成一次数据交互，通常对应一个业务逻辑，然后这次通信连接就断开。采用这种方式是为了能够同时服务更多的用户，因为当前的互联网应用每天都会处理上亿的用户请求，不可能每个用户访问一次后就一直保持这个连接。

当用户输入网址这个URL 的时候  
1. 首先会请求DNS把这个域名解析成对应的IP地址  
2. 然后根据这个IP地址在互联网上找到对应的服务器  
3. 向这个服务器发起一个get请求  
4. 有这个服务器决定返回的默认的数据资源给访问的用户  

在服务器端实际上还有很复杂的业务逻辑：
1. 服务器可能还有很多台，到底指定哪台服务器来处理请求，这需要一个负载均衡设备来平均分配所有用户的请求  
2. 请求的数据是存储在分布式缓存里还是一个静态文件中，或者在数据库里  
3. 浏览器解析数据时发现一些静态资源（如Css、JS或图片）又会发起另外的Http请求，而这些请求很可能在CDN上，那么CDN服务器会处理这个用户的请求。

##如何发起一个请求
**1、能否不借助浏览器组装一个符合HTTP数据包**  
**2、还有那些方式能够简单地发起一个HTTP请求**


如何发起一个HTTP请求和如何建立一个Socket连接区别不大，只不过outputStream.write写的二进制字节数据格式要符号HTTP，浏览器在建立Socket连接之前，必须根据地址栏中的URL的域名DNS解析出IP地址，在根据这个IP和默认的80端口与远程服务器建立Socket连接，然后浏览器根据这个URL组装成一个get类型的HTTP请求头，通过outputStream.write 发送到目标服务器，服务器等待inputStream.read返回 数据，最后断开这个连接。  

发起一个HTTP请求就是一个建立Socket通信过程



##HTTP解析
HTTP Header 控制着用户浏览器的渲染行为和服务器的执行逻辑。例如，当服务器没有用户请求的数据就会返回一个404状态码。






#深入分析Java I/O 的工作机制
---
I/O 问题可以说是当今Web应用所面临的主要问题之一  
在这个海量数据时代，数据在网络中随处流动  

##Java的I/O类库的基本架构
I/O问题是整个人机交互的核心问题
1. 基于字节操作的I/O接口：InputStream 和 OutputStream
2. 基于字符操作的I







## spring##

---

1. spring 概念和ioc 入门
2. spring的IOC操作和aop概念
3. jdbc Template 和spring管理事务
4. ssh框架整合开发  



spring boot 提供的特征：

1. spring boot可以建立独立的Spring应用程序
2. 内嵌了如Tomcat，Jetty和Undertow这样的容器，也就是说可以直接跑起来，用不着再做部署工作了 
3. 不需要向xml文件配置
4. 自动配置Spring
5. 提供了一些现有的功能，如量度工具，表单数据验证以及一些外部配置这样的一些第三方功能 
6. 提供的POM可以简化Maven的配置
7. 

