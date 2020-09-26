## UML

![image-20200926154505576](E:\Markdown\UML.assets\image-20200926154505576.png)

![image-20200926160554145](E:\Markdown\UML.assets\image-20200926160554145.png)

![image-20200926160617497](E:\Markdown\UML.assets\image-20200926160617497.png)

### 在结构上

#### 一、类图

在UML类图中，类使用包含==类名、属性(field) 和方法(method) 且带有分割线的矩形来表示==，比如下图表示一个Employee类，它包含name,age和email这3个属性，以及modifyInfo()方法。

![image-20200926165641910](E:\Markdown\UML.assets\image-20200926165641910.png)

**使用StarUML软件创建类图**

[教程](http://www.flyne.org/article/379)

1. File --> New Project By Approach --> Empty Project --> OK
2. Model --> Add --> Model
3. Model --> Add --> Diagram --> Class Diagram
4. Model --> Profile…”菜单去设置工程所需的profile。**这决定了工程所使用的规则和约定**。一定要包含”JAVA Porfile”这一项目。

**1、创建图表**

从默认就在屏幕的左边的“Toolbox”面板选择“类”图标，然后左键单击diagram窗口的某处。这样就使用通用名字创造了一个新的类。双击，将类改名为Circle。

<img src="E:\Markdown\UML.assets\image-20200926172112217.png" alt="image-20200926172112217" style="zoom: 50%;" />

<img src="E:\Markdown\UML.assets\image-20200926172138655.png" alt="image-20200926172138655" style="zoom:50%;" />

**2、添加属性**

右击图中的目标，在弹出菜单中选择“Add”中的“Attribute”(被标示为绿色)，为其添加一个属性(或者域)，填入期望的名字“name”。

在窗体右下边的Properties面板中，找到“Type”输入框，输入String作为name属性的类型。

类的内部数据（域/属性）都是私有的，因为他们是严格由类内部使用的。所以，在Properties面板中将name设置为“私有”。

**3、添加方法**

Operation（红色）

右击你刚刚创建的modifyInfo方法，并选择“Add Parameter”。在“Properties”框中，将参数的名子变为空，将“DirectionKind”变为“RETURN”，将“Type”变为void。
如果是抽象方法：将IShape和getArea的IsAbstract属性框打上勾，他们在图标上的名字将变为斜体。这是UML的标准，表示这是接口或者其他抽象实体。



- 

