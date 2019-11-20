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



# 工作流程
1. 初始化本地仓库
2. 跟远程仓库建立连接
	```
	git remote add 远程仓库的别名(origin) 远程地址
	git remote add origin git@github.com:lizelong/ceshi.git
	```
3. 开发模块
4. 先添加所有文件
	```
	git add .
	```
5. 提交到本地仓库
	```
	git commit -m '添加index.html'
	```
# github pages
目的： 为了更方便的查看HTML文件解析后的内容

# markdown语法

## 标题标记
* 用`#`表示标题标记，个`#`表示一级标题（h1）
* 用`#`表示标题标记，个`#`表示二级标题（h2）
* 用`#`表示标题标记，个`#`表示三级标题（h3）
* 用`#`表示标题标记，个`#`表示四级标题（h4）
* 用`#`表示标题标记，个`#`表示五级标题（h5）
* 用`#`表示标题标记，个`#`表示六级标题（h6）

## 列表
###无序列表
- 用`-`表示无序列表
- 用`-`表示无序列表
* 用`*`表示无序列表
* 用`*`表示无序列表
+ 用`+`表示无序列表
+ 用`+`表示无序列表

### 有序列表
1. 用数字+.`1.`表示有序类表
1. 用数字+.`1.`表示有序类表
5. 代码写5，但显示依旧是3

## 代码段
> 用3个 ` 表示代码段,用>代表引用内容
```
console.log("123");
```

## 图片和链接
![alt代替文本](.img/meiyou.jpg)

[文字链接](https://zzt-tao.github.io/tao/)

[![图片链接](http://img.ixinwei.com/iww201805/125069.jpg)](http://img.ixinwei.com/iww201805/125069.jpg "微笑的单身狗")
