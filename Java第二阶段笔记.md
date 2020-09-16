## Java第二阶段笔记

### 一、选择器

1. 类原则器
2. id选择器
3. 标签选择器

### 二、table布局

1. table布局：
   - `<tr>`：行；`<th>`：如果表格需要标题行，th可以制作标题行，默认空第一个单元格。
   - `<td>`：单元格
2. 字体大小：`font-size:8px;`设置字体大小
3. td样式：
   - border（边线）:1px solid（实现）;
   - border-color（边线颜色）
   - margin-xxx：外部空间
   - padding-xxx：内部空间
   - border-radius圆角
   - color 字体颜色
   - colspan n 横向合并单元格
   - rowspan n 纵向合并单元格
4. float 浮动

### 三、盒子模型

1. 盒子模型

   ![image-20200828212121082](E:\Markdown\Java第二阶段笔记.assets\image-20200828212121082.png)

### 四、音视频标签

1. 音频播放标签：`<audio controls="controls">`

   ```html
   <audio controls="controls">
       <source src="music.mp3"></source>
   </audio>
   ```

2. 视频播放标签：`<video controls="controls">`

   ```html
   <video controls="controls" width="400">
       <source src="mv.mp4"></source>
   </video>
   ```

### 五、动画

1. 动画

   - 关键帧：
     `@keyframes myName{`
     	`from{}`
     	`to{}`
     `}`

   - 在css中定义动画需要设置的参数：`animation`

   - `animation`即为动画的意思。它的后面有多个参数。第一个参数为myName（自定义动画的名字）2s（动画持续的时间） infinite（动画重复的次数，可以为纯数字）

   - `类名选择器:hover{}`设置鼠标移上去后的状态，移开后继续之前的状态

   - `transition`过渡的意思，从初始状态过渡到设置的过渡状态 还需要设置过渡时间

     ```html
     <!DOCTYPE html>
     <html>
     	<head>
     		<meta charset="utf-8">
     		<title></title>
     		<style>
     			.moveBox{
     				width: 100px;
     				height: 5px;
     				background-color: #11ee66;
                     /* 背景色，直接写英文，写RGB数字，3个16进制值构成，前面# */
     				/* 动画三个参数 （动画名称，执行动画的时间，infinite无限次循环）*/
     				animation: mymove 2s infinite;
     			}
     			/* @keyframes关键帧 动画的名称 由第一帧到关键帧（最后一帧）中间帧都是动画引擎自己实现 */
     			@keyframes mymove{
     				from{width: 0px; }/* 第一帧 */
     				to{ width: 300px; }/* 最后一帧 */
     			}
     			.transitionBox{
     				width: 100px;
     				height: 100px;
     				background-color: blue;
     				transition: width 2s;/* transition拉伸，宽度，持续2s */
     			}
     			.transitionBox:hover{/* 触发动画：鼠标移到上面hover，移除自动恢复 */
     				width: 300px;/* 动画，从width=100，持续s2， 拉伸width=300 */
     			}
     		</style>
     	</head>
     	<body>
     		<div>移动效果：</div>
     		<div class="moveBox"></div>
     		
     		<div>拉伸效果：</div>
     		<div class="transitionBox"></div>
     	</body>
     </html>
     
     ```

### 六、菜单导航和超链接

1. 菜单导航

   - `<ul>`
   - `<li>`
   - `<li>`通常搭配`<a>`标签一起使用
   - 去掉导航前的小点：`list-style: none;	`
   - 去掉超链接的下划线等修饰：`text-decoration: none;	`

2. 超链接标签：`<a>`

   href 超链接
   target 目标，
       _self 在自身窗口打开页面，覆盖之前链接页面
       _blank 打开新窗口来展示页面，之前链接页面还展示

1. 让div的边框变斜：`-webkit-transform: skewX(30deg);`
2. `margin: 0 auto` ，两个参数auto实现最终横向居中
3. `background-image` 默认背景图片平铺repeat，如果大小没有占满，
4. `background: url(img/earth.png) no-repeat;` 不平铺，只展示一个，其他地方空白

### 七、谷歌高级动画

1. 让图片旋转：

   - `-webkit-animation: run 5s linear 0s infinite;`

     -webkit只能谷歌浏览器支持

     run 动画名称

     5s 耗时

     linear 动画轨迹，线型

     0s 进入时延迟n秒，才开始播放

     ```html
     @-webkit-keyframes run{
         from{ -webkit-transform: rotate(0deg); }
         to{ -webkit-transform: rotate(360deg); }
     }
     
     /*动画run，谷歌浏览器关键帧定义*/
     /*rotate旋转0°到to360°*/
     ```

   - `-webkit-animation-play-state`

     play播放

     state状态

     play-state:paused暂停

### 八、引入外部css和javascript

1. 在html文件在使用css的三种方法：

   - 将css样式写在head的style标签中

   - 将css样式直接用style属性写在标签中

   - 外部引入：

     `<link rel="stylesheet" href=""/>`

   - 

2. 外部引入JavaScript文件

   - html标签中`onclick="alert('hello')"`
   - `<script>`标签中`<script>js代码</script>`
   - js文件在，导入外部js文件——`<script src=""></script>`

   

### 九、JavaScript

1. 文档对象模型DOM（Document Object Model）与HTML网页API接口
2. 浏览器对象模型BOM（Browser Object Model），与浏览器进行交互的API接口
3. Window对象
   - window.alert("text")——提示信息会话框
   - window.setIntervel(func, time)——每隔指定时间(毫秒)执行，反复执行
   - window.setTimeout(action,time)——等待指定时间(毫秒)后再执行，执行一次
   - window.clearInterval()——清除时间间隔
4. Document对象
   - document.write() ——动态向页面写入内容
   - document.getElementById(id)——获得指定id值的元素
   - document.getElementsByName(name)——获得指定Name值的元素
   - document.getElementsByClassName(name)——通过类名来查找元素
   - document.getElementsByTagName——标签名称，得到数组

#### ES6高级语法

1. var：用来定义一个变量，不用指定变量的数据类型，js作为一门脚本语言，在变量的定义方式上与Java有很大的区别，跟python有异曲同工之妙。例如定义一个整数类型的变量和字符串类型的变量的语法为：`var num=123;var str="String;"`

2. let：由let关键字定义的变量为局部变量，只在局部范围内生效。假设有一个全局变量被var定义，在局部中有同名变量被let关键字定义，则在局部遵循变量的就近原则，出了局部let将不再生效，而是var生效，而且局部变量的值的更改不会影响全局变量的值

3. const：被const定义而来的变量被常量，不能修改，不能再次赋值

4. undefined：变量的值，表示被定义但没有被初始化，比Java中的null更加灵活

5. NaN：

6. JavaScript的数据类型：数字、字符串、布尔、数组

7. 对象：`var person = new Person()`。也可以简写为：`var person={}`

8. 声明对象并添加属性及方法：

   - 静态：

     ```javascript
     <script>
         var person={
     		//静态定义属性
     		name:"dasd",
     		age:45
         	//静态定义方法
     		nameToUp:function(){
     			return this.name.toUpperCase()
     		}
     	}
     	console.log("name:"+person.name)
     	console.log("age:"+person.age)
     	console.log(person.nameToUp())
     </script>
     ```

   - 动态：

     ```javascript
     <script>
     	var person={}
     	//动态扩充属性
     	person.school="黔南民族师范学院"
     	console.log("school"+person.school)
     		//动态扩充方法
     	person.abc=function(){
     		return this.name+"abc"//调用对象的属性需要加this关键字
     	}
     	console.log(person.abc())
     </script>
     ```

#### event事件

1. onclick——用户点击HTML元素
2. ondblclick——用户双击HTML元素
3. onchange——内容改变事件，特别常用于下拉框
4. onmouseover——鼠标移动到HTML元素上
5. onmouseout——鼠标移开HTML元素
6. onkeydown——用户按下键盘按键
7. onkeyup——用户松开键盘按键
8. onload——浏览器已经完成页面加载
9. onunload——浏览器关闭时执行，但通常无用，用户直接关闭浏览器甚至中断
10. 后期绑定：

#### 关于JavaScript的备忘录

1. 在清空input标签的内容操作中，不能直接使用`obj.innerText=""`而是应该使用`obj.value=""`

2. 要想浏览器在我们操作input框时有下拉菜单提示之前输入的内容，则input的标签的id需要规范设计，目前发现，当`id="username"`时能弹出提示

   ![image-20200831210150046](E:\Markdown\Java第二阶段笔记.assets\image-20200831210150046.png)

### 十、Jquery

前端框架：react、vue、vue-element-admin

动态绑定事件：

jQuery 封装javascript基本api，工具包，开发者使用起来更加好用

1. 页面元素4种方法方式：

   |                 javaScript                  |           jQuery            |
   | :-----------------------------------------: | :-------------------------: |
   |                  document                   |            $( )             |
   |    document.getElementsByTagName("div")     |          $("div")           |
   |   document.getElementsByName("username")    | $("input[name='username']") |
   | document.getElementsByClassName("username") |       $(".username")        |
   |     document.getElementById("username")     |       $("#username")        |

2. 使用jQuery动态设置样式

   ```html
   <!DOCTYPE html>
   <html>
   	<head>
   		<meta charset="utf-8">
   		<title></title>
   		<script src="js/jquery.min.js"></script>
   	</head>
   	<body>
   		<div id="msg">使用jQuery来实现div中的字体变大、变色</div>
   	</body>
   	<script>
   		//获取div的对象，设置css样式，改变字体大小
   		$("#msg").css("font-size", 36);		//样式：font-size: 36
   		$("#msg").css("color", "red");		//样式：color: red
   	</script>
   </html>
   ```

3. 使用jQuery动态绑定事件

   ```html
   <script>
   	//给按钮动态绑定一个事件onclick
   	//onclick没有on，参数是匿名函数
   	$("#pay").click(function(){
           //禁止按钮：html 属性：disabled true禁止，false可以点击
   		$("#pay").prop("disabled", true);			//属性方法
   	});
   </script>
   ```

4. `$().ready(function(){})`。将jQuery代码放在`$().ready(function(){})`的方法体中可以保证里面的代码在页面加载完成后再运行，解决因页面未加载完成的报错问题。与`body`中的`onload`效果类似

5. jQuery实现复选框全选

   ```html
   //实现全选，jQuery选择器[]，过滤出我想要的元素，[id标签的id=ck（id给定名称)]
   //jQuery可以针对一组值进行设定，动态绑定click事件
   $("#selectAll").click(function(){
   	$("[id=ck]").prop("checked", true);		//所有ck框全部选中
   })
   $("#unSelectAll").click(function(){
   	$("[id=ck]").prop("checked", false);		//所有ck框全部取消选中
   })
   ```

### 十一、json

json字符串相当于一个字符串数组，里面的每个元素(记录)都可以单独看成一个字典，而且完全符合key-value数据类型的特点。可以通过key的值访问value的值。

1. 把json字符串先转换成js对象，然后就可以js进行操作data[0]

   `var obj = JSON.parse(json字符串）`
   
2. js对象转json字符串

   `var jsonstr = JSON.stringify(obj)`

### 十二、Ajax

1. jQuery提供ajax方法：

   ```ht
   $.ajax	7个参数
   $.ajax(function(){
   	type: "POST", 访问类型
   	url: 访问地址
   	contentType: 请求字符集 application/json; charset=utf-8;	防止中文乱码
   	data: {} kv多个参数和值，传递后台服务
   
   	dataType: 请求的返回值类型：html/json/jsonp（跨域，访问别人的网站）
   
   	//回调callback，函数
   	//这个参数就是请求网站的返回值json字符串，ajax把json字符串转化data对象
   	success: function(data){	
   		//获取数据json，展示在页面
   	}
   	error: function(){
   		alert('操作失败!');
   	}	
   })
   ```



### vue

![image-20200905094127347](E:\Markdown\Java第二阶段笔记.assets\image-20200905094127347.png)

1. index.html

2. src/main.js

   import相当于导包，js包，组件以这样的方式==导入==

3. src/App.vue

   - template：模板，html片段

   - script：脚本

     export——组件==导出==，其他地方就可以调用这个组件

   - style：样式

4. src/router/index.js

5. src/components/HelloWorld.vue

   自己来二次开发改这个文件

==简单来说项目加载的过程是：index.tml->main.js->App.vue->index.js->HelloWorld.vue==

Vue项目运行环境搭建（nodejs+npm+webpack+vue）

端口：localhost:8080



### vue-element-admin

端口：localhost:9527

1. src/router/index.js

   - /* Router Modules */
   - /** when your routing map is too long, you can split it into small modules **/

2. 在src/router/modules中新建与刚刚设置的同名js文件

   - 删除children其他内容，留一个

   - 开始自定义修改

     ```java
     /** When your routing table is too long, you can split it into small modules **/
     
     import Layout from '@/layout'
     
     const jtsysRouter = {
       path: '/jtsys',
       component: Layout,
       redirect: '/jtsys/itemcat',
       name: '商品管理',
       meta: {
         title: '商品分类管理',
         icon: 'table'
       },
       children: [
         {
           path: 'itemcat',
           component: () => import('@/views/jtsys/itemcat'),
           name: '商品分类管理',
           meta: { title: '商品分类管理' }
         }
       ]
     }
     export default jtsysRouter
     
     ```

3. 在src/views下新建一个目录，新建jtsys

   - 再在example中复制一个list.vue过来，重命名为itemcat.vue。
   - 将`<el-table>`标签除第一个子标签外，删除全部的子标签。

   - 将import { fetchList } from '@/api/jtsys/itemcat'修改成这样

4. 在src/api中复制article重命名为itemcat。删除十行以后的内容

   - 修改第五行为`url: '/itemcat/list',`

5. 



### JDBC

#### 0、下载相关jar包

1. [mysql的jar包下载地址](https://dev.mysql.com/downloads/connector/j/)

2. 选择操作系统：Platform Independent![image-20200909193042976](E:\Markdown\Java第二阶段笔记.assets\image-20200909193042976.png)

3. 点击download

   ![image-20200909193249859](E:\Markdown\Java第二阶段笔记.assets\image-20200909193249859.png)

4. 在编译器中导入刚刚下载下来并解压zip后的jar包

#### 1、加载数据库驱动

```java
String driverName="com.mysql.jdbc.Driver";//使用jdbc加载mysql驱动的固定语法
```

#### 2、建立数据库连接

```java
String url="jdbc:mysql://localhost:3306/dbname";
Connection cn = DriverManager.getConnection(url, "root", "root");
```

#### 3、创建statement对象

```java
Statement stat = cn.createStatement();
```

#### 4、执行sql语句 ，得到ResultSet对象

```java
String sql="select * from emp";
ResultSet rs = stat.executeQuery(sql);
```

#### 5、遍历结果集

```java
while(rs.next()){
    int id = rs.getInt("id");
 	String name = rs.getString("name");
 	int age = rs.getInt("age");
 	System.out.println("id="+id + "===name="+name+"==age="+age);
}
```

#### 6、释放资源

```java
if (stat != null){
    try {
        stat.close();
    } catch (SQLException e) {
        e.printStackTrace();
        System.out.println("statement 关闭出现问题，请及时处理");
    }
}
if (cn != null){
    try {
        cn.close();
    } catch (SQLException e) {
        e.printStackTrace();
        System.out.println("Connection关闭出现问题，请及时处理");
    }
}
```

