#master

> ##### git 生成密钥

1.配置 用户名和emial

```
git config –global user.name "xxxxx"
git config –global user.email "xxx@xx.xxx"
```
2.生成秘钥

```
ssh-keygen -t rsa -C ‘上面的邮箱’
```

3.接着按3个回车,则在.ssh目录下得到了两个文件：id_rsa（私有秘钥）和id_rsa.pub（公有密钥）如果想登陆远端，则需要将rsa.pub里的秘钥添加到远端。

	
> #####git 命令简介：

[1] 查看所有的git 分支
```
  git branch -a
```

[2] github上已经有master分支 和dev分支在本地:
```
  git checkout -b dev 新建并切换到本地dev分支
  git pull origin dev 本地分支与远程分支相关联

```

[3] 在本地新建分支并推送到远程
```
  git checkout -b test
  git push origin test   这样远程仓库中也就创建了一个test分支
```

[4] 删除远程分支
```
  git push origin --delete dev
```

[5] 删除本地分支
```
  git branch -d dev
```

[6] 列出Git可以在该处找到的所有的设置
```
  git config --list
```

[7] Git认为的一个特定的关键字目前的值
```
  git config user.name
```

[8] 添加配置项 
```
  git config [–local|–global|–system] –add section.key value(默认是添加在 local 配置中)注意add后面的 section, key, value 一项都不能少，否则添加失败。比如执行：
  git config -–add site.name yiibai
```

[9] 删除配置项
```
  git config [–local|–global|–system] –unset section.key
  git config --local -–unset site.name
```

[10] 获取帮助
```
  $ git help <verb>
  $ git <verb> --help
  $ man git-<verb>
  git help config
```

[11] 克隆项目
```
  git clone url
``` 

[12] 通过 git add 命令来实现对hello.py 文件的跟踪 (可以用它开始跟踪新文件，或者把已跟踪的文件放到暂存区，还能用于合并时把有冲突的文件标记为已解决状态等)
```
git add hello.py
git commit -m 'initial project version'
```

[13] 创建本地分支，将本地分支推送到远程

```
git branch 分支名称
git push --set-upstream origin 分支名称
``` 

> ##### git commit之后，想撤销commit

```
git reset --soft HEAD^
```
HEAD^的意思是上一个版本，也可以写成HEAD~1,如果你进行了2次commit,想都撤回,可以使用HEAD~2

***--soft***: 不删除工作空间改动代码，撤销commit，不撤销```git add .```

***--mixed***: 不删除工作空间改动代码，撤销commit，并且撤销```git add . ```操作这个为默认参数, ```git reset --mixed HEAD^``` 和 ```git reset HEAD^``` 效果是一样的。

***--hard***: 删除工作空间改动代码，撤销commit，撤销```git add .```

***git commit --amend***: 如果commit注释写错了,只是想改一下注释,此时会进入默认vim编辑器,修改注释完毕后保存就好了。

> #### git 自动转换 换行符问题
在windows的git bash中使用vim编辑文本文件，那么，在你每次使用git add命令可能都会出现类似如下warning
```
$ git add .
warning: LF will be replaced by CRLF in file2.
The file will have its original line endings in your working directory
```
这是由于换行符冲突引起的报警，因为git bash默认使用vim作为文件编辑器，vim默认使用LF作为换行符，与linux中的换行符一直，它们都是用LF换行符，但是windows默认使用CRLF作为换行符，大多数程序员都会使用IDE或者文本编辑器来编辑文本，这些编辑器通常能够自动识别换行符，除了windows自带的记事本等文本编辑器，记事本只会使用CRLF作为换行符，由于我习惯使用vim编辑文本，所以文件中的换行符都是LF，当git检测到时，它会贴心的帮我装换一下，但是其实我并不是特别需要，因为我在bash中不会使用记事本编辑文件，所以，我们可以禁用自动转换的功能，使用如下设置，禁用自动转换换行符：

``` git config --global core.autocrlf false ```

> #### git将某个版本作为 新的分支
```
git log --online
git checkout 分支哈希
git branch -b 新的分支
```