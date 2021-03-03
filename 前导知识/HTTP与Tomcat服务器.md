# HTTP服务器
## 服务器
* 安装在服务端计算机上的**资源调用器**
## HTTP服务器
* 是一种与HTTP协议相关的
* 接收请求包-->解析请求包-->定位&访问文件-->文件内容写入包    
(接收来自浏览器的HTTP请求协议包，并自动对协议包内容进行解析，解析后，自动定位到被访问的文件上，并将内容写入到HTTP响应协议包中，在推送回发起请求的浏览器上）
## HTTP服务器的分类
这里仅记录两个
### JBOSS服务器
JBOSS服务器，基于J2EE的开源代码的应用服务器，不但是Servlet容器，而且是EJB容器，一般与TomcatJetty绑定。
### Tomcat服务器
轻量级服务器，是一个支持Servlet和JSP技术的容器。将它配置到我们自己的电脑上后，可以利用它响应HTML页面的访问请求，这样我们就可以在自己的电脑上模拟基于B/S(Browser/Server)结构的互联网通信流程
# Tomcat的安装与配置
## 下载Tomcat
[下载链接](http://tomcat.apache.org/), apache-tomcat-9.0.40-windows-x64.zip 解压即为安装成功
## Tomcat的配置
* JAVA_HOME：指向JDK安装的地址 (eg: F:\java\JDK8\JDK1.8)
* JRE_HOME：指向JRE安装的地址 (eg: F:\java\JDK8\JRE1.8)
![image](https://github.com/nanxinW/Servlet-/blob/main/Figure/java_home.png)
* CATALINA_HOME(部分windows系统要求用户指定tomcat安装地址)：通知windows系统tomcat装在哪里 (eg: F:\tomcat\apache-tomcat-9.0.40-windows-x64\apache-tomcat-9.0.40)
## Tomcat启动与关闭
* 启动与关闭命令存放位置
  Tomcat的安装位置/bin  (eg: F:\tomcat\apache-tomcat-9.0.40-windows-x64\apache-tomcat-9.0.40\bin)
* 启动命令
  startup.bat
* 关闭命令
  shutdown.bat
 ## Tomcat内部工作文件的作用
 简述三个
 * bin： Tomcat管理命令
 * conf： Tomcat配置文件
 * lib： Tomcat使用的jar包
