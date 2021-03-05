# 什么是Servlet？
Servelt（Java Servlet的简称），本质上是一个**Java编写的接口，运行在服务器上的程序**，是HTTP客户端与服务器上的数据库或者应用程序之间交互的中间件。
# Servlet的作用是什么？
读取客户端的数据，处理数据得到结果，将结果返给客户端

# Servlet接口实现类
* Http服务器能调用的【动态资源文件】必须是一个servlet接口实现类
```
class Student{
    //不是动态资源文件，Tomcat无权调用
}
class Teacher implements Servlet{
    //合法动态资源文件，Tomcat有权调用
    //因为实现了Servlet接口
    Servelt obj = new Teacher();
    obj.doGet();
}
```
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
