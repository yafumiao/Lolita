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
