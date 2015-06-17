# TortoiseGit安装和使用 #

TortoiseGit是Windows下不错的一款Git客户端工具，在Mac下推荐使用sourcetree。下面就介绍一下TortoiseGit安装和使用的方法。
安装TortoiseGit并使用它需要两个软件：TortoiseGit和msysgit。

## 软件下载 ##
TortoiseGit官网下载地址：http://download.tortoisegit.org/tgit/1.8.14.0/
msysGit官网下载地址：http://msysgit.github.io/ 
![](http://i.imgur.com/Y0IpLwK.png)

>下载最新版本时注意，msysGit选“Git for Windows”，TortoiseGit区分64bit和32bit，并选择附带的语言包。

下载的版本分别是：TortoiseGit-1.8.9.0-32bit.msi和TortoiseGit-LanguagePack-1.8.9.0-32bit-zh_CN，以及 Git-1.9.4-preview20140815.exe

## 软件安装 ##

解压`/git`下文档，双击安装程序。先安装Git，再安装TortoiseGit及安装TortoiseGit中文包。  
安装后提示重启电脑。
![](http://i.imgur.com/KkaS6AV.png)

## 使用TortoiseGit ##

先在TortoiseGit安装目录里面找到"Settings"，打开界面，找到"General"，点击“Check now”按钮，可以看到当前git版本。这时候说明，你的配置已经OK，可以开始进行下一步的操作了。   
![](http://i.imgur.com/qG1HemQ.png)
![](http://i.imgur.com/GnXFgfw.png)

## 设置TortoiseGit ##

选择“TortoiseGit > Settings”，在“User Info”输入Name和Email。点击“Remote”，在Remote输入名称，URL输入Git的HTTPS或者SSH地址。点击“Add New/Save”按钮添加一个项目。
![](http://i.imgur.com/FrJLjAS.png)

## 创建的版本库 ##
在项目文件夹用鼠标右键点击，可以看到Git和TortoiseGit已经嵌入右键了，选择“Git Create repository here”，然后点击“OK”按钮，再点击“Proceed”，这样就会在项目文件中创建了一个“.git”的隐藏目录。
![](http://i.imgur.com/QI2Bd1U.jpg)
![](http://i.imgur.com/p7Mwy2g.jpg)
>**注意**
>新建一个文件夹，比如为gitbase作为新建一个项目的测试。目前不要有中文，git对路径中的中文支持还不太好，功能好像没什么问题，但是乱码什么的看起来确实不舒服.>


## Git配合TortoiseGit的基础使用  ##
### 1 新建一个项目 ###
![](http://i.imgur.com/fPxGmQR.png)

图中红框中的选项

![](http://i.imgur.com/mkUAoPT.png)
一般然后会出现这个对话框，直接点击**OK**。

![](http://i.imgur.com/6xDpGif.png)

出来这个对话框就可以了。
>**注意**
![](http://my.csdn.net/uploads/201207/15/1342364840_2658.png)

### 2 新建测试文件 ###

![](http://i.imgur.com/Qm8qF9J.png)

新建一个文本文件（测试效果直接），打开文档，在里面输入“版本一”，然后保存退出

### 3 提交更改 ###
![](http://i.imgur.com/7lsHC5F.png)

在文件中点击右键，选择图中红框选项，弹出以下对话框

![](http://i.imgur.com/sxLy6FG.png)

选中刚才新建的文本文档，在上面的输入框里填写注释，比如填写 版本一，点击**OK**，弹出以下对话框。

![](http://i.imgur.com/vx0dkCP.png)

点击**Close** 就可以了。

然后再打开文本文档，增加 “版本二”内容，保存退出后，再提交，注释填写“版本二”，然后下面查看版本记录。

### 4 版本历史记录 ###

单击右键，选择**Show log**

![](http://i.imgur.com/rcgQucl.png) 


出现窗口，可查看所有版本信息。
![](http://i.imgur.com/6VHdAvG.png) 

### 5 版本恢复 ###

假设现在到了“版本二”，我要做一些更改，但是还不确定是否作为正式版本中的更改，那么我就需要先建立一个版本分支。（先别管分支是什么，做完这一步就知道什么意思了）

![](http://i.imgur.com/QEVO0pq.png)

上图中红框中的选项，建立分支

![](http://i.imgur.com/DG2z8wO.png)

起名为v3，版本三的意思，选择复选框中的 切换至分支，点击**OK**。

此时再点右键，发现菜单变了，下图中的红框部分，提交的时候就会提交到刚才我们建立的分支 v3

![](http://i.imgur.com/y1hLOOT.png)

现在打开文本文档，添加内容“版本三”，保存退出，提交。

再来看版本更新历史

![](http://i.imgur.com/5kkbXFB.png)

里面就出现了**v3**和**master**两条版本路线。

现在提出问题，我觉得分支v3版本稳定，可以作为主版本的一部分，也就是说版本三在基于主版本修改后，要把更改合并到主版本中，现在就要做如下操作

### 6 切换分支 ###

![](http://i.imgur.com/JVxHS0j.png)

上图红框选项，出现对话框

![](http://i.imgur.com/Z5QEp9M.png)

选择**master**，点击**OK**。

![](http://i.imgur.com/Oq3WVpV.png)

上图中红框中的**merge**选项，

![](http://i.imgur.com/M4PHEel.png)

选择合并来源，选择分支**v3**，点击**OK**。

好了，现在看一下文本文档，里面已经有了“版本三”的内容了。

所以，从现在来看，git的主体思路就是不断的建立分析，可靠以后再合并到主分支里面，从而使得整个版本不断更新。当然相关的功能必不可少，比如版本回溯，就是发现当前版本不够好，返回到之前的某个版本重新来过等等，这些功能也非常重要，但是只要明白了主线，就可以明白为什么有那些相关功能了。git本身就是为使用而开发的，所具有的功能都是现实使用中碰到的最常见的问题。如果你在使用过程中，发现一个情况不知道如何处理，你只要想一下这个情况别人是否会遇到，如果是的话，那这个软件应该有相关的功能或者功能组合来帮你处理问题。
