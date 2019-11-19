# 与本地相关的命令
```
git config --global user.name mingzi //设置名字github
git config --global user.email youxiang//设置邮箱github
git init //新建一个git客户端版本库 初始化
git status //查看当前状态（只要有改动 那么文件名为红色 先add 然后commit）
git add . //添加进客户端的暂存区
git commit -m "注释" //提交到本地所在分支的版本库
----------------版本---------------------
git log //查看版本日志
git log --pretty=oneline //查看版本一行显示
git reset --hard ^ //回退到上一个版本 上上个就是^^（是在工作区的改变）
git reset --hard 版本id //回退到该版本id的版本（是在工作区的改变）
git reflog //查看所有的操作日志(可以滚回去再滚回来)
----------------分支---------------------
git branch //查看本地有哪些分支
git branch 分支名 //添加分支
git checkout 分支名 //切换分支
git checkout -b 分支名 //创建并切换分支
git branch -d 分支名 //删除本地分支
```

# 与远程服务器端相关的命令
```
新建仓库：仓库名称 描述 Public 不选README 
git remote add origin(远程仓库的别名) https://github.com/LZY622/仓库名.git(远程仓库的真实连接) //建立本地与远程的连接
git remote //查看本地与远程的链接的所有别名
git remote -v //查看所有远程链接的地址
git remote rm origin //删除某个链接别名
git push -u(第一次推的时候加之后就不需要了) origin(远程仓库别名) master(从本地分支名):master(到远程分支名) -f（一般不加意味强制推）//推到指定服务器上,如果此时所在分支名(a)与远程目标分支名(a)一致,可以只写一个分支名(表示从本地a分支推至远程a分支)
git pull （-–allow-unrelated-histories） origin master//拉下来服务器中的分支中的内容并合并（等于fetch + merge）
git clone 仓库地址 //初始化克隆仓库里面的内容(在项目文件夹外面克隆)
git clone -b 分支名仓库地址 // 克隆仓库分支
git fetch 仓库别名//查看远程各个分支的状态并拉取到本地版本库中(如果是默认origin 可以省略)
git merge 仓库别名/分支 //在版本库中合并代码
git diff // 查看合并之后的冲突
git reset --hard head  //解决MERGING状态，如果报错这个意思是在.git目录下已经有一个index.lock文件夹存在了，只需要去这个目录下删了这个文件夹，然后再输入 git reset --hard head 就ok了
```

# 生成公私钥：为了每次推到远程仓库的时候不输入账号密码
> 进入程序家目录看看是否已经有公钥（windows中c盘用户目录 linux中cd ~/.ssh）

> `ssh-keygen -t rsa -C "注释（邮箱）" `//点3次回车，在家目录中出现.ssh文件夹,后缀.pub是公钥另一个是私钥

> 打开公钥文件复制
账号下拉菜单->setting->SSH and GPGkeys->New SSH key->title与项目名一致，粘贴公钥，添加

# 添加协作者
> 项目仓库->setting->collaborators(协作者)->搜索github用户名添加；对方收到邮件点击同意即可。

# 实际项目中开发流程
```
//(开始项目)
克隆项目 
git clone
切进目录
新建并切换一个分支dev
git checkout -b dev
//(在dev分支上进行开发)
开发一个阶段后
更新本地dev分支版本库
git add .
git commit -m ""（这次注释要让所有人看懂）
切到master分支
git checkout master
合并本地dev版本库中的内容
git merge dev
推至远程版本库分支
git push origin master:shuaige
切回dev分支
git checkout dev
//(新一轮的开发)
拉取远程库的所有分支
git fetch origin
合并远程master分支
git merge origin/master
解决冲突
git diff
更新本地dev分支版本库
git add .
git commit -m ""（此次注释自己看懂就好了）
//(继续在dev分支上进行开发)
...
```