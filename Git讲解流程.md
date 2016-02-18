# GIT
-------
## 1. Git 的身世

作者：林纳斯·托瓦兹 （Linus Torvalds），Linux 的伟大的副产物

![Linus](http://s.siliconimg.com/kb/content_images/2013/08/21/227988/1377031471_938.jpg)

Linus 在 1991 年创建了开源的 Linux 之后靠着开发者共同维护。

2002 ago ，contributors 把源代码文件通过 diff 的方式发给 Linus，Linus 和 维护者 `手工方式` merge。

维护者受不了了，Linus 选择了 BitKeeper，很喜欢 BitKeeper.

理查德・斯托尔曼（Richard Stallman）自由软件倡导者，精神领袖，GNU计划创造者

![RS](https://pic4.zhimg.com/2a980372a1e5aa27334e128fba5d556f_b.jpg)
![RS2](https://pic4.zhimg.com/da98a459ed043acc176c6ca79d564417_b.jpg)

![xx](https://ss1.baidu.com/70cFfyinKgQFm2e88IuM_a/forum/pic/item/adaf2edda3cc7cd9684f8ce83e01213fb80e91a5.jpg)

并且有人开始对 BitKeeper 逆向，破解，BitKeeper 收回了 Linus 的免费使用权。

不得不要写一个自己的版本控制系统：

* 1.速度优势，有能力高效管理类似 Linux 内核一样的超大规模项目（速度和数据量）

* 2.对非线性开发模式的强力支持（允许上千个并行开发的分支）

* 3.完全分布式

* 4.简单易用的设计，bullshit

Linus 不到两周时间， C 写了一个分布式版本控制系统，1300 行左右，之后靠 contributors 去壮大。

**身世评价:**

亲爹：Linus </br>
干爹：世界各地 contributors </br>
外表：Source Tree, TortoiseGit 等等等 </br>
内涵：[这里](http://pic002.cnblogs.com/img/1-2-3/201007/2010072023345292.png)

## 2. 集中式 与 分布式

集中化的版本控制系统：SVN

![集中化的版本控制系统](http://git.oschina.net/progit/figures/18333fig0102-tn.png)

单一的集中管理的服务器，保存所有文件的修订版本，协同者通过客户端连到这台服务器，查看提交记录或者进行提交。checkout 的只是某个版本的代码，没有任何版本信息记录。

分布式版本控制系统：Git

![分布式版本控制系统](http://git.oschina.net/progit/figures/18333fig0103-tn.png)

客户端并不只提取最新版本的文件快照，而是把代码仓库 `完整地镜像` 克隆（clone） 提取（fetch) 到本地

* 1.分布式，去中心化 </br>
* 2.本地提交 </br>
 * 断网提交 </br>
 * 小步提交，颗粒化，跟踪代码时，更加细腻 </br>
 * 不用 sever，也可以进行版本控制 </br>
* 3.高速度，所以 commit，checkout 变得飞快 </br>

## 3. Git 结构模型

为什么要理解 Git 结构模型？</br>

* 我 tmd 在哪？
* 我 tmd 的代码呢? 
* 屏幕上的提示信息到底是 tmd 让我干嘛?

![四个区](http://www.ruanyifeng.com/blogimg/asset/2015/bg2015120901.png)

**四区：**

* Workspace：工作区，就是你在电脑里能看到的目录 </br>
* Index / Stage：暂存区，在暂存区的东西，才能 commit 到 Repository </br>
* Repository：本地仓库区</br>
* Remote：远程仓库

**六指令：**

* add：增加 </br>
* commit：提交 </br>
* push：推送 </br>
* fetch：拉取 </br>
* checkout：检出 </br>
* pull：fetch + merge </br>

## 4. Git 命令讲解

###1. 新建版本控制

```
//	初始化 git
git init 	
//	从服务器 clone repo，
git clone 
```
	
###2. 配置 Git

```
//	查看配置
git config --global --list
//	编辑配置
git config --global --eidt
	
//	设置提交人
git config --global user.name "John Doe"
//	设置邮件
git config --global user.email johndoe@example.com
//	设置编辑器
git config --global core.editor emacs			
```

###3. add

从`工作区`选取一些代码快照，加入到`暂存区`，即将要`commit`的内容

```
//	将 <path> 放到 暂存区
git add <path>

//	将 改动的跟踪文件 放到暂存区，但是不包括 新增的 
git add -u stages 
//	将 所有 放到暂存区
git add . 
```

* 提问：为什么会有`暂存区`这个概念？
* 快照？


#### 高级用法

```
//	操作片段
git add -p

y:	暂存此片
n:	不暂存此片
a:	暂存此片和剩余的片
d:	不暂存和剩余的片
?:	查看帮助
q:	退出
e:	手动编辑选择是否暂存
s:	切片

git add -i

```

###4. commit

将`暂存区`的代码快照`提交`到`本地仓库`






3. 分支 branch 

和 SVN 不同，


1. 新建项目
2. git config 不讲
3. init add commit remote push pull fetch clone

常用指令讲解：
clone </br>
init </br>
add </br>
commit </br>
push </br>
merge </br>
rebase </br>
reset </br>

高级指令：
rebase -i
cherry-pick </br>
reflog 

### Git一些高级用法

1. Oh My Zsh
2. git reflog
3. 


### GitFlow

![GitFlow](http://nvie.com/img/git-model@2x.png)
