#### MVC开发模式

##### 一、MVC开发模式的角色组成：

C：controller，控制层

M：model，业务模型层：完成业务处理

1. dao层：直接操作数据库
2. service层：调用dao层来完成业务实现，负责管理dao层的事务

V：view，视图层：将处理结果写入响应包

##### 二、Dao层作用：


