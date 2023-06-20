- 原因不明
#### 排查：
- 检查防火墙是否允许端口通过
- 检查用户权限
- 在数据库连接软件中指定数据库版本
#### 最终解决
- 跳过密码登录
```mysql
在[mysqld]下添加 skip-grant-tables
关闭mysql服务并重新开启
```
- 修改密码
```mysql
update mysql.user set authentication_string=password("!09051223aA!") where user="root";
flush privileges; 
 
```
刷新权限 成功解决

