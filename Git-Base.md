# Git Basc

## 概述Git：
- Git简述：
> Git是目前世界上最先进的分布式版本控制系统,也称之为分布式版本控制器。是IT从业人员进行代码管理、迭代、分布式开发的**必备利器**。

- Git的诞生：
> 1991年Linux之父**Linus**创建了开源的操作系统`LINUX`，从此Linux系统不断发展；已经成为世界上最流行的服务器操作系统。虽然Linus创建并开源了Linux系统，但是Linux的发展壮大是世界上众多的程序员共同参与编写的。2002年以前，来自全世界的志愿者通过diff的方式将源代码发给Linus，然后Linus通过手动合并的方式进行代码管理，可以说是非常麻烦的。因为Linus坚决反对使用`SVN`、`CVS`集中式版本控制系统，因为其速度满、必须付费、联网使用等，与开源精神不符。2005年BitMover公司出于人道主义精神允许Linus与Linux社区的开发人员使用商业版版本控制系统`BitKeeper`,但是出于特殊原因`BitMover`公司收回了Linux社区的免费使用权；后来Linus花了两周的时间，自己用`C`语言写了一个分布式管理控制系统`Git`,后续Linux源码就由Git管理了。
> 2008年`GitHub`网站上线，它为免费开源项目提供Git存储；无数开源项目迁移至GitHub，比如`PHP`、`Jquery`、`Ruby`等。


## 初识Git：
## 使用Git：
- Windows系统下载安装Git：
> 浏览器打开[Git 官网](https://git-scm.com/downloads "Git for Windows")或者[国内Git镜像](https://github.com/git-for-windows/git/releases "Git CDN")，根据自己系统位数下载相应的版本，然后双击安装程序。安装完成之后，打开【开始菜单】，找到【Git】下的【Git Bash】单击打开；如果出现类似Windows下的【命令行】窗口，并出现提示`Welcome to Git`等字样，代表安装成功。

- 初始化Git配置：

> 打开【Git Bash】窗口，输入如下Git命令，完成初始化操作：

```

	git config --global user.name "You GitGub User Name"
	git config --global user.email "example@example.com"

```

- 本地创建Git存储仓库：
> 切换到本地磁盘下的纯英文【强烈建议】文件夹，新建一个文件夹，并执行`git init`命令，将新建的目录变成可管理的仓库：

```

	cd /d f:\NoteBook\Git
	mkdir dir lerangit
	cd learngit

	//Git init
	git init

	//Add
	git add {File Name}

	//Commit
	git commit -m "Effective Description"

	//Push
	git push origin master

```

- 本地创建项目到GitHub远程仓库：

```

	git remote add origin git@github.com:{You GitHub Account Name}/{Project Name}.git
	git remote add origin git@github.com:yanbog/learngit.git

```

- 克隆GitHub远程项目到本地：
> 执行`git clone`克隆命令，将远程GitHub项目拷贝到本地磁盘中，如果出现失败问题；需要配置GitHub `SSH KEY`

```

	git clone git@github.com:{You GitHub Account Name}/{Project Name}.git
	git clone git@github.com:yanbog/learngit.git

```

- 添加`SSH KEY`保证安全的授权访问：
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