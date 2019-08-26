![Git Learn Logo](https://images.cnblogs.com/cnblogs_com/hollow/1530701/o_Git-Logo.png)

# Git Learn 2 Basic - Basic usage of Git【Git 基础使用方法】

> 一篇文章快速掌握Git的使用

## 概述Git：

- Git简述：
> Git是目前世界上最先进的分布式版本控制系统,也称之为分布式版本控制器。是IT从业人员进行代码管理、迭代、分布式开发的**必备利器**。

- Git的诞生：
> 1991年，Linux之父`Linus`创建了开源的操作系统`LINUX`，从此Linux系统不断发展；已经成为世界上最流行的服务器操作系统。虽然Linus创建并开源了Linux系统，但是Linux的发展壮大是世界上众多的程序员共同参与编写的。

> 2002年以前，来自全世界的志愿者通过diff的方式将源代码发给Linus，然后Linus通过手动合并的方式进行代码管理，可以说是非常麻烦的。因为Linus坚决反对使用`SVN`、`CVS`集中式版本控制系统，因为其速度满、必须付费、联网使用等，与开源精神不符。

> 2005年，BitMover公司出于人道主义精神允许Linus与Linux社区的开发人员使用商业版版本控制系统`BitKeeper`,但是出于特殊原因`BitMover`公司收回了Linux社区的免费使用权；后来Linus花了两周的时间，自己用`C`语言写了一个分布式管理控制系统`Git`,后续Linux源码就由Git管理了。

- Git发展：
> 2008年4月10，`GitHub`网站上线，它为免费开源项目提供Git存储；后续无数开源项目迁移至GitHub，比如`PHP`、`Jquery`、`Ruby`等。

> 2008年至今，GitHub以发展10余多年。据官方介绍全世界使用GitHub的人数已经有4000万，并且还在持续稳定增长中；被广大开发人员和各国网友“戏称”为`全世界认可，最大的同性交友平台`。

> 2018年6月4日，微软宣布，通过75亿美元的股票交易收购代码托管平台GitHub。

> 2018年10月26日，微软以75亿美元收购GitHub交易已完成。同年10月29日微软开发者服务副总裁奈特·弗里德曼(Nat Friedman)将成为GitHub的新一任CEO。

## 初识Git：

### Git的工作原理及基本使用流程：

- Git工作原理介绍：
> 
![](https://git-scm.com/book/en/v2/images/lifecycle.png)

- Git文件状态：
> Git管理文件有三种状态：已提交`committed`、已修改`modified`和已暂存`staged`,我们在处理项目文件时，你的文件可能就出于这三种状态之中。

1. 已提交`committed`：已提交表示数据已经安全的保存在本地数据库中。 
2. 已修改`modified`：修改了文件，但还没保存到数据库中。
3. 已暂存`staged`：对一个已修改文件的当前版本做了标记，使之包含在下次提交的快照中。

![](https://git-scm.com/book/en/v2/images/areas.png)

- Git基本使用流程：

	1. 修改文件：在工作目录中修改文件。
	2. 暂存文件：将文件的快照放入暂存区域。
	3. 提交更新：找到暂存区域的文件，将快照永久性存储到`Git`仓库目录`Repository`中。

### Git常用命令介绍：

> Git基本的常用命令介绍，更多Git命令可以在`Git Bash`中使用`git --help`或者`git help -a`命令查看，或者在官网的官方文档中查看。如果需要查看某个命令的详细帮助信息，可以使用`git help {commands}`命令打开本地离线的HTML帮助文档，eg：要查看`git`命令的帮助信息，可以使用`git help git`。

Git命令 | 描述 | 常用参数 | 示例
-|-|-|-
git init|初识化Git||git init
git help|Git帮助信息|-a|git help -a
git config|配置Git|--global、--unset、--list|git config --global {option}
git add|将文件内容添加到索引中|{filename}、-A、--all、*.{ext}|git add -A
git commit|记录对存储库的更改|-m、-C|git commit -m "last commit"
git clone|将存储库克隆到新目录中|{repository}|git clone {repository}
git push|推送更新到远程存储库中|{repository}|git push origin master
git status|跟踪文件状态|-s|git status -s

## 配置Git：

### Windows系统下载安装Git：
> 浏览器打开[Git 官网](https://git-scm.com/downloads "Git for Windows")或者[国内Git镜像](https://github.com/git-for-windows/git/releases "Git CDN")，根据自己系统位数下载相应的版本，然后双击安装程序。安装完成之后，打开【开始菜单】，找到【Git】下的【Git Bash】单击打开。如果出现类似Windows下的【命令行】窗口，首次运行会出现提示`Welcome to Git`等字样；或者`Win+R`运行`CMD`，输入`git --version`来查看Git版本并且验证【系统环境变量`PATH`】是否配置成功。详细安装教程详见上一章节【Windows下安装配置Git】。

### 初始化Git配置：

> 打开【Git Bash】窗口，输入如下Git命令，完成初始化操作：`git config --global`为全局配置，你当前所有的提交，都会以此`user name`和`email`为标识提交【推荐设置为Github 用户名和邮箱】。配置完成后会在`C:\Users\{YouUserName}\`文件夹下生成一个`.gitconfig`配置文件，如果需要重新进行全局配置，可以删除、更改`.gitconfig`文件或者重新运行`git config --global`命令。

```

	git config --global user.name "You GitGub User Name"
	git config --global user.email "example@example.com"

```

> 如果做好全局配置，但是想用其他`user name`和`email`提交，可以在当前项目文件夹下使用`git config`重新配置。

```

	git config user.name "You GitHub User Name"
	git config user.email "example@example.com"

```

### 配置Git忽略文件`.gitignore`：

> 在项目开发和测试中，许多文本编辑器或者测试工具会自动生成一些缓存、日志、测试等一些不必要的文件，而我们在提交时又不需要这些随着其他必要文件一起提交。可以在完成仓库初始化之后，就应该立即创建`.gitignore`文件。

```

	echo "*.log" > .gitignore
	echo "*.tmp" >> .gitignore

```

### 配置Git默认文本编辑器：

> 默认情况下我们在安装Git客户端时就已经配置好了默认的文本编辑器，如果你想重新配置，可以使用`git config --globa`;如果需要删除默认文本编辑器配置,可以使用`git config --unset`:

```

	git config --global core.editor "{TextEditorName}"
	git config --global core.editor {Text Editor Install Path}

	git config --unset --global core.editor
	git config --unset --global core.editor "{Text Editor Install Path}"

```

### 检查Git配置信息：

> 配置完成后，如果需要检视你的配置信息，可以使用`git config --list`列出你当前的配置信息。

```

	git config --list

```
## 使用Git

### 在现有目录中初始化仓库：

> 切换到本地磁盘下的工作目录文件夹，并执行`git init`命令，将新建的目录变成可管理的仓库：

```

	cd /d f:\NoteBook\Git
	mkdir dir lerangit
	cd learngit

	//Git init
	git init

	//Create Ignore File
	echo "*.log" > .gitignore
	echo "*.tmp" >> .gitignore

	//Create README.md File 
	echo "Git Learning Project learngit" > README.md

	//Add
	git add {File Name}


	//Commit
	git commit -m "Effective Description"

	//Push
	git push origin master

```

### 本地创建项目到GitHub远程仓库：

```

	git remote add origin git@github.com:{You GitHub Account Name}/{Project Name}.git
	git remote add origin git@github.com:yanbog/learngit.git

```

### 克隆GitHub远程项目到本地：

> 执行`git clone`克隆命令，将远程GitHub项目拷贝到本地磁盘中，如果出现失败问题；需要配置GitHub `SSH KEY`

```

	git clone git@github.com:{You GitHub Account Name}/{Project Name}.git
	git clone git@github.com:yanbog/learngit.git

```

### 添加`SSH KEY`保证安全的授权访问：

1. 配置Git Bash全局配置：

	```
	
		git config --global user.name "You GitGub User Name"
		git config --global user.email "example@example.com"
	
	```

2. 生成`SSH KEY`安全密钥：

	```
	
		ssh-keygen -t rsa -C "YouEmail@email.com"
	
	```

3. 拷贝公有`SSH KEY`密钥，并添加到`GitHub`账户的`SSH KEY`中：
 
	> 浏览器打开GitHub官网，登录GitHub账户。点击【用户头像】->【Settings】->【SSH and GPG keys】->【SSH keys】->【New SSH Key】;填写`SSH KEY Title`,在`Key`中粘贴已复制好的密钥内容，点击`Add SSH Key`保存内容。
 
4. 测试SSH密钥是否验证通过：

	```
	
	 	ssh -T git@github.com
	 	//Hi {You User Name}! You've successfully authenticated, but GitHub does not provide shell access
	
	```