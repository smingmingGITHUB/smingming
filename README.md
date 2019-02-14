# smingming
happy
git checkout -b dev origin/dev 依赖于远程分支创建本地分支

先更新-合并
git fetch origin master 更新远程分支

git merge origin/master 合并到本地

提价步骤
git add .
git commit -m "注释"
git push -u origin master:master

问题：error: 无法推送一些引用到 ‘git@gitlab.xxx:xxx.git’
解决方案：$ git push -u origin +master 强制推送

$ git pull 同步远程仓库到本地，出现冲突强制合并


初次使用Git的设置

如果初始化配置已经在之前弄过的可以直接跳过这一部分至push到远程仓库的内容。

1. 初次运行Git前需要先对Git的工作环境进行配置（如果之前已经设置过那么就不需要再设置一次），采用的工具是git config。主要设置用户信息即可，包括用户名和邮箱


$ git config --global user.name "用户名"

$ git config --global user.email 自己的邮箱

设置结束后可以通过以下指令查看配置信息


$ git config --list

2. Git本地仓库与Github远程仓库之间的传输主要是通过SSH方式加密传输，所以之前没有设置过需要创建SSH Key。创建方式如下


$ ssh-keygen -t rsa -C "自己的邮箱"
运行过程中会出现让你设置密码等要求，直接按回车，使用默认值即可



3. 如果上述指令运行成功，那么会在主目录（home）下生成一个.ssh的隐藏文件夹，按ctrl+h可以显示。点击进入后可以找到两个文件，分别为：id_rsa和id_rsa.pub。这两个文件对应了私密密钥和公开密钥，接下来就是要将公开密钥文件（即id_rsa.pub文件）中的代码复制到github中的“SSH Key”下面，具体过程 见CSDN。
