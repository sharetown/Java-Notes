#### Servlet

##### 一、xml文件的解释

```xml
<!--servlet标签给tomcat配置servlet程序-->
    <servlet>
        <!--servlet-name标签 servlet程序起一个别名（一般是类名）-->
    <servlet-name>HelloServlet</servlet-name>
        <!--servlet-class是servlet程序的全类名-->
    <servlet-class>com.sharetown.cn.HelloServlet</servlet-class>
</servlet>

    <!--servlet-mapping标签给servlet程序配置访问地址-->
    <servlet-mapping>
        <!--servlet-name标签的作用是告诉服务器，我当前配置的地址是给哪个servlet程序使用-->
        <servlet-name>HelloServlet</servlet-name>
        <!--url-pattern配置访问地址<br>
        / 斜杠在服务器解析的时候，表示地址为：http://ip.port/工程路径  <br>
        / hello 表示地址为：http://ip.port/工程路径/hello   <br>-->
        <url-pattern>/hello</url-pattern>
    </servlet-mapping>
```

#####  二、Servlet-url地址是如何定位到servlet程序去访问的

![image-20200613141509419](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20200613141509419.png)

##### 三、Servlet的生命周期

1. 执行servlet构造器

2. 执行init初始化方法

   第1、2步是在第一次访问的时候创建Servlet程序会调用

3. 执行service方法

   第3步每次访问都会调用

4. 执行destroy销毁方法

   第4步，在web工程停止的时候调用

   

   

##### 四、Get、Post 请求

![image-20200613145342088](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20200613145342088.png)

![image-20200613145510614](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20200613145510614.png)



##### 五、通过继承HttpServlet实现Servlet程序

一般在实际项目开发中, 都是使用继承HttpServlet类的方式去实现Servlet程序。

1. 编写一个类去继承HttpServlet 类
2. 根据业务需要重写doGet或doPost方法
3. 到web.xml中的配置ServVlet程序的访问地址

##### 六、Servlet类的继承体系

![image-20200613142900518](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20200613142900518.png)

##### 七、获取请求的参数值

> request.getParameter()S

##### 八、请求的转发

![image-20200613154326413](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20200613154326413.png)

##### 九、base标签

> base标签设置页面相对路径工作时参照的地址
>
> href属性就是参数的地址值

##### 十、HttpServletResponse类的作用

HttpServletResponse类和HttpServletRequest类- 样。每次请求进来，Tomcat 服务器都会创建一个Response对象传递给ervlet程序去使用。HttpServletRequest 表示请求过来的信息, HttpServletResponse 表示所有响应的信息,我们如果需要设置返回给客户端的信息,都可以通过HttpServletResponse对象来进行设置

##### 十一、请求重定向

![image-20200613161209651](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20200613161209651.png)

##### 十二、JavaEE的三层架构

![image-20200613162036351](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20200613162036351.png)

##### 十三、Servlet的java类中的代码说明（补充）

```java
package com.sharetown.ch;

import javax.servlet.ServletException;
import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;
import java.io.IOException;
import java.io.PrintWriter;

public class MyJavaWebProject extends HttpServlet {
    //新建一个类，继承HttpServlet类
    //之后可按需求重写doGet()方法和doPost()方法
    
    //doGet方法，用于接收客户端的get请求
    @Override
    protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        //在这里书写请求的方法体，如果发生get请求，则执行下面方法体中的代码
        System.out.println("hello");
    }

    //doPost请求，用于接收客户端的post请求
    //request代表请求，response代表响应
    //当需要获取客户集提交过来的数据时，使用request对象；
    //当需要向客户机输出数据时，使用response对象。
    @Override
    protected void doPost(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        //request.setCharacterEncoding("utf-8");//处理乱码
        //获取客户端提交的信息
        String username=request.getParameter("username");
        String password=request.getParameter("password");
        System.out.println("用户名："+username);
        System.out.println("密码"+password);

        //response.setContentType("text/html;charset=utf-8");
        response.setHeader("content-type","text/html;charset=utf-8");//获取请求头信息
        PrintWriter out = response.getWriter();
        out.println("用户名:"+username);
        out.print("密码："+password);
        //向客户端输出刚刚输入的用户名和密码
        response.addHeader("refresh", "3;url=ind.html");//这句代码会将页面在客户端停留3秒后跳转到ind.html

        //请求重定向
        /**
         * 请求重定向：
         * 1· 地址栏发生改变
         * 2. 两次请求和响应
         * 3. 可以访问web应用以外的资源
         */
        //可以访问外部资源（百度之类的连接）
        //response.sendRedirect("http://www.baidu.com");

        //请求转发
        /**
         * 不可以访问外部资源
         * 地址栏不会发生改变
         * 一次请求和响应
         */
        //request.getRequestDispatcher("http://www.baidu.com").forward(request, response);
    }
}

```

##### 十四、理解request和response

[理解request和response](https://www.jianshu.com/p/d2716d8cd823)



