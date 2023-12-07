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

## 工作流程
![工作流程](image\git工作流程.png "Git工作流程")

git管理的区域有 4 个，分别是从下往上。左半部分对应推送，右边则是拉取。

![工作流程](image\git工作流程.jpg "Git工作流程")



## 常用命令
暂存区和本地仓库的修改对比：
   ```bash
   git diff HEAD -- Untitled-1.md
   ```

[详细教程](https://www.liaoxuefeng.com/wiki/896043488029600)