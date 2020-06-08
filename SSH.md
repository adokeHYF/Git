#SSH 基本操作
      
> ##### 免密登陆之 ssh-agent 代理
ssh-agent $SHELL: 开启ssh-agent 服务

ssh-add ~/.ssh/id_rsa: 将私钥添加到ssh-agent 服务

ssh-add -l: 查看代理中添加的公钥

ssh-agent -k: 关闭ssh-agent 服务

ssh-add -D: 移除代理中所有公钥

ssh-add -d /path/of/key/key_name: 移除指定的私钥



> #### 免密登陆之远程传递ssh 公钥
```
ssh-copy-id -i ~/.ssh/id_rsa.pub user@ip
```





select user,authentication_string,plugin,host from user

创建用户:
create user 'cna'@'%' identified by 'password';

创建cna用户，并且给最高权限
GRANT ALL PRIVILEGES ON *.* TO 'cna'@'%' IDENTIFIED BY 'youpassword' WITH GRANT OPTION;

查看cna用户权限:
show grants for 'cna'@'%'; 


