github仓库与本地仓库通过ssh加密
在使用git中添加远程或者是从远程库克隆之前需要将自己的SSH key添加到账户的列表中
创建SSH key
$ ssh-keygen -t rsa -C "你的邮箱"
这样会在用户主目录中生成  .ssh目录
目录中包含id_rsa和id_rsa.pub文件，id_rsa文件时私钥一定不能泄露，id_rsa.pub是可以公开的
回到github，点击setting -> SSH and GPG key -> add SSH key
title可以随意写 key将id_rsa.pub内容填入


本地添加远程库的方法
$ git remote add origin <仓库ssh地址>
将本地内容推送至远程仓库
$ git push -u origin master
以后每次将内容推送至库
$ git push origin master

$ git remote 查看远程库的信息
$ git remote -v 查看远程库的权限
远程仓库和本地的关系就是将本地的分支与远程库的分支对应起来

分支推送
$ git push origin dev
如果当前远程已有分支
$ git checkout -b dev origin/dev


注意：在多人开发中，推送分支可能会失败，原因是远程分支内容比本地的分支更新
需要将远程更新后的内容与本地合并 $ git pull
再 $ git push origin 分支名（branch-name）
如果在 $git pull 时发生错误，错误信息为no tracking information
远程仓库分支与本地仓库没有建立联系
$ git branch --set-upstream 分支名 origin 分支名
建立完毕联系后再$
