- 原因不明
#### 排查：
- 检查防火墙是否允许端口通过
- 检查用户权限
- 在数据库连接软件中指定数据库版本
#### 最终解决
- 跳过密码登录
- 修改密码
```mysql
update mysql.user set authentication_string=password("!09051223aA!") where user="root";
```
刷新权限 成功解决

