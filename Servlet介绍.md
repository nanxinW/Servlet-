# 什么是Servlet？
Servelt（Java Servlet的简称），本质上是一个**Java编写的接口，运行在服务器上的程序**，是HTTP客户端与服务器上的数据库或者应用程序之间交互的中间件。
# Servlet的作用是什么？
读取客户端的数据，处理数据得到结果，将结果返给客户端

# Servlet接口实现类
* Http服务器能调用的【动态资源文件】必须是一个servlet接口实现类
~~~java
class Student{
    //不是动态资源文件，Tomcat无权调用
}
class Teacher implements Servlet{
    //合法动态资源文件，Tomcat有权调用
    //因为实现了Servlet接口
    Servelt obj = new Teacher();
    obj.doGet();
}
~~~
## servlet接口实现类开发步骤

* 第一步：创建一个java类实现Servelet接口，成为一个Servlet接口实现类

* 第二步：重写(Override)HttpServlet父类两个方法。doGet方法或者doPost方法

  ​             					get方式

  ​				浏览器   -------------->    oneServlet.doGet()

  ​									post方式

  ​				浏览器   --------------->   oneServlet.doPost()

* 第三步：将Servlet接口实现类信息【注册】到Tomcat服务器

  ​				【网站】 ---》 【web】 ---》 【WEB_INF】-----》 web.xml


  ~~~xml
  <!--将servlet接口实现类类路径地址交给Tomcat-->
  <servlet>
      <servlet-name>OneServlet</servlet-name><!--声明一个变量存储servlet接口实现类类路径-->
      <servlet-class>com.wang.controller.OneServlet</servlet-class><!--声明servlet接口实现类类路径-->
  </servlet>
  ~~~
  

  ~~~xml
  <!--为了降低用户访问Servlet接口实现类难度，需要设置简短请求别名-->
  <servlet-mapping>
      <servlet-name>mm</servlet-name>
      <url-pattern>/one</url-pattern><!--设置简短请求别名，别名在书写时必须以“/开头-->
  </servlet-mapping>
  ~~~

  如果现在浏览器向Tomcat索要OneServlet时 地址可以简化为：http://localhost:8080/myWeb/one
  
  # servlet对象生命周期
1. 网站中所有的Servlet接口实现类的实例对象，只能**由Http服务器负责创建**
     在默认的情况下，Http服务器接收到对于当前Servlet接口实现类第一次请求时自动创建这个Servelet接口实现类的实例对象
2. Server 调用 Servlet 的 init() 方法，始化该 Servlet
3. Server 创建一个请求对象，处理客户端请求 & Server 创建一个响应对象，响应客户端请求
4. Server 激活 Servlet 的 service() 方法，传递请求和响应对象作为参数。
     service() 方法获得关于请求对象的信息，处理请求，访问其他资源，获得需要的信息
     service() 方法使用响应对象的方法，将响应传回Server，最终到达客户端。service()方法可能激活其它方法以处理请求，如 doGet() 或 doPost() 
   
