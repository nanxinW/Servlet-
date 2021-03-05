# IDEA配置管理Tomcat
File-->Setting
![image](https://github.com/nanxinW/Servlet-/blob/main/Figure/IDEA%E9%85%8D%E7%BD%AE%E7%AE%A1%E7%90%86Tomcat.png)
Run--> Edit Configuration 设置 Tomcat启动与关闭按钮
![image](https://github.com/nanxinW/Servlet-/blob/main/Figure/Tomcat%E5%90%AF%E5%8A%A8%E4%B8%8E%E5%85%B3%E9%97%AD%E6%8C%89%E9%92%AE.png)

# 网站内部结构
* src文件夹：存放作为动态资源文件的java文件

* web文件夹：存放作为静态资源文件【图片，html，css，js】

  ​					存放网站运行时依赖的jar[mysql驱动]

  ​					存放网站的核心配置文件(web.xml)

  * WEB-TNF：依赖的jar[mysq驱动]/核心配置文件(web.xml)
    * lib文件夹：依赖的jar[mysq驱动]
    * web.xml：通知Tomcat当前网站那些java类是动态资源文件
