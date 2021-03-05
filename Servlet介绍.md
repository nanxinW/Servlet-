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
