# 简介
主要用来记录学习 git 所涉及的知识。



# Git 入门
Git是一个开源的分布式管理系统。



## 安装
在[Git官网](https://git-scm.com/)上根据系统版本下载对应的Git即可。在 windows 下，直接无脑下一步就行了。Linux下使用下面的命令安装：

```bash
sudo apt-get install git
```



## 概念
1. 工作区：编辑区域
2. 暂存区：临时添加文件的区域，通过 git add
3. 本地仓库：本地托管文件的区域，git commit
4. 远程仓库：如 Github、远程服务器、一些其它的托管平台。git push


能看到的目录或文件称为工作区，工作区中有个.git隐藏目录，该目录称为版本库，当中有个暂存区stage。git add 命令就是把工作区中的文件添加到该暂存区的。还有Git为我们自动创建的第一个分支master，以及指向master的一个指针叫HEAD。git commit就是把暂存区的全部内容更新到版本库中，也就是当前分支。也可以简单理解为，需要提交的文件修改通通放到暂存区，然后一次性提交暂存区的所有修改到本地版本库。

Git 只跟踪并管理修改，而不是文件。如修改A文件，添加到暂存区，再修改，使用git commit更新到当前分支，最后使用git status 查看状态会发现只提交了一次。因为第二次修改没有添加到暂存区。每次修改，如果不用git add到暂存区，那就不会加入到commit中。

删除文件，如果使用 rm 命令删除了文件，在使用 git status 查看后 git 会发现版本库和工作区的内容不一样了，会显示那些文件被删除了。建议使用 git rm 删除指定文件

__远程仓库：github__
1. 创建 ssh key：ssh-keygen -t rsa -C "youremail@example.com"。成功后会在用户目录下产生一个.ssh文件夹，当中有两个文件，id_rsa 和 id_rsa.pub，前者是私有 ssh 秘钥，后面的是公有秘钥。
2. 登陆GitHub，打开“Account settings”，“SSH Keys”页面，点击“Add SSH Key”，填上任意Title，在Key文本框里粘贴id_rsa.pub文件的内容。
3. 在本地仓库，输入下面的命令验证是否成功：

```bash
ssh -T git@github.com
```



## 工作流程
![工作流程](image/git工作流程.png "Git工作流程")

git管理的区域有 4 个，分别是从下往上。左半部分对应推送，右边则是拉取。

![工作流程](image/git工作流程.jpg "Git工作流程")



## 常用命令
暂存区和本地仓库的修改对比：
   ```bash
   git diff HEAD -- Untitled-1.md
   ```

|   命令   |   说明 |
|   :--    |   :--: |
|   init   |   初始化一个git仓库    |
|   add    |   添加文件到暂存区 |
|   commit -m "版本说明"   |  提交文件到本地仓库    |
|   status |   修改的文件状态   |
|   diff|查看difference |
|   log    |   查看历史版本 |
|   git reset --hard HEAD~x |   回退到 x 个版本 |
|   git reset --hard <commit id>    |  切换到指定版本   |
|   git reflog  |    记录你的每一次命令   |
|   git stash、git stash pop    |  暂时储藏起来、提取出来   |
|   git checkout -- <file>  |    撤销修改，暂存区和非暂存区（前者无法回退到添加到暂存区之前需要使用取消暂存命令，后者则是回退到未编辑之前）|
|   git reset HEAD <file>   | 取消暂存 |
|   git rm <file>   | 删除暂存区中的文件   |


[详细教程](https://www.liaoxuefeng.com/wiki/896043488029600)