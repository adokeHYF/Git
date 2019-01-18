
git 生成密钥：

	1.配置 
	  git config –global user.name ‘xxxxx’ 
	  git config –global user.email ‘xxx@xx.xxx’

	2.生成秘钥 
	  ssh-keygen -t rsa -C ‘上面的邮箱’
	3.接着按3个回车 则
	
	最后在.ssh目录下得到了两个文件：id_rsa（私有秘钥）和id_rsa.pub（公有密钥）
	如果想登陆远端，则需要将rsa.pub里的秘钥添加到远端。
	
git 命令简介：

	1.git branch -a: 查看所有的git 分支

	2.github上已经有master分支 和dev分支
	  在本地:

	  git checkout -b dev 新建并切换到本地dev分支

	  git pull origin dev 本地分支与远程分支相关联
	  
	3.在本地新建分支并推送到远程

	  git checkout -b test
	  
	  git push origin test   这样远程仓库中也就创建了一个test分支
	  
	4.删除远程分支
	  git push origin --delete dev
	  
	5.删除本地分支
	  git branch -d dev

	6.列出Git可以在该处找到的所有的设置
	  git config --list
	  
	7.Git认为的一个特定的关键字目前的值
	  git config user.name

	8.添加配置项 
	  git config [–local|–global|–system] –add section.key value(默认是添加在 local 配置中)注意add后面的 section, key, value 一项都不能少，否则添加失败。比如执行：
	  
	  git config -–add site.name yiibai
	
	9.删除配置项
	  git config [–local|–global|–system] –unset section.key
	  
	  git config --local -–unset site.name
	  
	10.获取帮助
	  $ git help <verb>
	  $ git <verb> --help
	  $ man git-<verb>
	  
	  git help config
	
	11.克隆项目
	  git clone url
	
	12.通过 git add 命令来实现对hello.py 文件的跟踪 (可以用它开始跟踪新文件，或者把已跟踪的文件放到暂存区，还能用于合并时把有冲突的文件标记为已解决状态等)
	  git add hello.py
      git commit -m 'initial project version'