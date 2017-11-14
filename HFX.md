# 说明
* 如README所描述这是用来完(ying)成(fu)Xiaomo的作业的...
* 所以这个仓库里什么鬼都会有并且每天都会更新（emmm...）
---
## November
### 11.07
* 之前建了个ILOVEYOU版本库打算收集520张“我爱你”电影截图
（好啦我知道早就有大佬做过这件事情并且轮子都造好了...我就是想收集一下好嘛）
在建ILOVEYOU的时候对版本库的远程操作还不大了解，趁着完(ying)成(fu)Xiaomo的作业再来干一遍并记录一下我常用的基本命令。
#### 下载Git
* 没啥好说，就是想吐槽一下GUI真难看
* 下载地址：https://git-scm.com/downloads
#### git clone
* 从远程主机克隆一个版本库，然后在本机生成一个目录，实现远程操作。  
` $ git clone <版本库的网址> <本地目录名> `
* 如果不写本地目录名则直接克隆在Git的安装目录下
#### cd <仓库名>
* 刚开始时直接在MINGW64下直接对仓库进行操作，然后就GG了
* 应先输入命令` cd <仓库名> `进入到对应仓库，再进行操作
#### git add
* git add跟踪一个文件，如果你给已跟踪文件1.jpg改名成2.jpg，可以输入  
` $ git add 2.jpg `  
此时2.jpg进入了暂存区（此时1.jpg还没被移除）
#### git rm
* git rm 移除指定文件
* 要从Git中移除某个文件，就必须要从已跟踪文件清单中移除（确切地说，是从暂存区域移除），然后提交。 可以用 git rm 命令完成此项工作，并连带从工作目录中删除指定的文件，这样以后就不会出现在未跟踪文件清单中了。
#### git commit
* 我懒起来一般直接git commit -a，Git就会把所有add过的文件暂存并提交
* 也可以` $ git commit -m "...." `""内的是注释
#### git status
* 在commit之前其实可以git status一下查看文件状态（有没有add漏的）
（我这么懒的就不会status，所以我的commit乱七八糟的...）
#### git push
* 把本地仓库中的数据推送到远程仓库（这个环节最爽了）
#### git pull
* 说人话大概就是“同步”“更新”的意思吧
* 当push前如果远程仓库有更新，那么push操作就会被驳回，这是时要先pull一下再进行push
---
### 11.08
#### 静态网站
* 通常以.html结尾。用户无论以何种方式请求，返回的资源信息都是相同的。
#### 动态网站
* 根据用户提交信息的不同返回不同的信息（asp，php，jsp）。当用户请求这些资源时，服务器端返回的信息会因用户提交的信息的不同而变化，在服务器想客户端传送网页内容时，服务器首先将这些程序处理成客户端可以查看的方式，然后再将数据发送到客户端，因此，表现为一种动态的响应过程。
* SQL注入（SQL Injection）：此风险只存在于动态页面中。
---
### 11.09
* 一个系统从无到有的过程：可行性分析-需求分析-设计-实现-部署-运维
* 需求分析：
1. 基于结构化的方法
2. 基于面向对象的方法
#### 基于面向对象的需求分析步骤和制品
1. 写问题陈述（Problem Statement）：包括主要角色、主要功能、非功能需求
2. 用例析取（Achieve Usecase）：画**用例图（Usecase Diagram）**
3. 写用例规约（Usecase Specification）：即，写每一个用例的**事件流**[主事件流and辅助事件流]
4. 写补充规约：写非功能需求
5. 术语表（Glossary）：写本系统会用到的词（生僻的词）
---
### 11.10
* 之前由于一些我不明白的原因出现了代码冲突情况导致文件不能成功push，出现了以下提示：  
` error: Your local changes to the following files would be overwritten by merge:  
XIAOMO/HFX.md  
Please, commit your changes or stash them before you can merge. `  
Google之，得到以下方法:  
** 若希望保留生产服务器上所做改动，仅仅并入新配置项，方法如下：  
` git stash ` 保存当前工作进度（储存本地修改）  
` git pull ` 更新  
` git stash pop ` 还原暂存内容  
可以使用git diff -w +文件名 来确认代码自动合并情况  
** 若希望用代码库中的文件完全覆盖本地工作版本.，方法如下:  
` git reset `  
` git pull `  
* END
---
### 11.11-11.12
* 周末都用来肝字幕了！！！
---
### 11.13
* 今天踩过的坑： 
* 在安装完Kali Linux的时候忘记了用户名密码（其实是不知道用户名是root，以为是自己命名的Username）于是一直密码错误进不到主页面。同时想到了一个问题，如果真的忘了密码该怎么办呢？然后得到以下方法：
#### Kali Linux密码重置
1. 启动Kali Linux系统后，出现   
` Kali GUN/Linux `   
` *Advanced options for Kali GUN/Linux `   
  两个选项时，选择第二个并按E键进入编辑模式   
  ![GitHub](http://a3.qpic.cn/psb?/V11bbUf720k94q/.DxnUthm*5YBpOq6GL7qPBVswRsVs7vjNJfh2mwPvJc!/b/dI4BAAAAAAAA&bo=gQLeAYEC3gEDByI!&rf=viewer_4)
2. 找到以下代码，把ro改为rw，在.gz后面写上init=/bin/bash   
![GitHub](http://a3.qpic.cn/psb?/V11bbUf720k94q/8sU.MYTVk*5fYo6Sz57dXu2mgJO0tJCYxdjOWlWEUSo!/b/dOAAAAAAAAAA&bo=SwIiAEsCIgADACU!&rf=viewer_4)
3. 改完后按F10或CTRL+X继续启动，出现以下画面，输入新密码。   
![GitHub](http://a2.qpic.cn/psb?/V11bbUf720k94q/ZPSfHQDW4jEfeuwlGYBsgf5rzjFPtTcAtel9rcaffjA!/b/dOIAAAAAAAAA&bo=5QJdAeUCXQERADc!&rf=viewer_4)
* 此时就可以使用新密码登录了。（登录到主页面中间差不多有一分钟的黑屏害我以为是我镜像的问题，硬是重启了好几次）
---
### 11.14
* test