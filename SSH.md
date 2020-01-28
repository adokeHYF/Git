#SSH 基本操作
      
> ##### ssh-agent
ssh-agent $SHELL: 开启ssh-agent 服务

ssh-agent -k: 关闭ssh-agent 服务

ssh-add ~/.ssh/id_rsa: 将私钥添加到ssh-agent 服务

> #### 免密登陆之远程传递ssh 公钥
```
ssh-copy-id -i ~/.ssh/id_rsa.pub user@ip
```