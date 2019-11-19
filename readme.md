# 第一个仓库
1. `git init` 用于初始化仓库

2. 新建一个readme.md文件

3. `git add 文件名` 添加文件到本地仓库
```
git add .   //添加所有文件
```

4. 添加用户名和邮箱(第一次的时候需要)
```
git config --global user.email '你的邮箱'
git config --global user.name '你的用户名'
```

4. 提交
```
git commit -m '注释' //注释是对本次提交的说明
```

5. 添加远程仓库地址
```
git remote add origin git@github.com:lizelong/ceshi.git
```
6. 将本地提交的内容推送到远程仓库
```
git push 远程仓库的别名 master
git push abc master
```

6. 没有权限，先生成ssh key
```
ssh-keygen -t rsa -C '邮箱'

执行完上一条命令后，会在 ~/.ssh/ 文件夹下面生成公钥文件 id_rsa.pub 
将公钥文件中的内容，放到GitHub中：
	右上角头像 -> settings -> SSH and GPG keys -> New SSH key
	title： 仓库名
	Key： id_rsa.pub 的内容
```