## **git安装教程**

```sudo yum install -y git```

#### 查看安装版本
[root@39 ~]#``` git version```\
git version 1.8.3.1

#### 配置：
```
$ git config --global user.name "Your Name" #添加管理用户
$ git config --global user.email "email@example.com"  #添加管理用户邮箱
```

### git使用：

#### **开始使用**
```
mkdir catalog #创建空白目录
cd catalog #进入该目录
git init  #初始化 将该目录变为git可以管理的仓库
git add filename #将文件添加到仓库
git commit -m "description" #将文件提交到git服务器
```
#### **git查看**
```
git status #查看结果
git diff  #查看difference
git commit -a -m "desription" #提交所有
git log #查看历史记录
 git log --pretty=oneline #只显示日志id和描述
```


## **版本回退**
**回退到之前版本**
```
git reset --hard HEAD^ #回退到上一个版本
git reset --hard 版本号 #回退到哪个版本
```
回退后再返回原来版本
```
git relog #查看提交reset版本
git reset --hard 版本号
```

#### 撤销修改
```
已修改工作区的内容，但还没有add到暂存区 git checkout -- readme.txt 回到历史版本
已add到暂存区，但还没有commit git reset HEAD readme.txt 回到1
已add到暂存区，并做修改，但还没有commit git checkout -- readme.txt 回到2
```



#### git删除文件
``` rm filename #本地删除文件
git status #查看修改状态
git rm filename  #git暂存区删除文件
git commit  #提交
```
#### 删除恢复
```
git checkout -- filename  #错误删除恢复：(一键还原)
```



## 连接远程仓库
注册github账户(1540774503@qq.com 密码：xxx 账户名：ananzhoujiaan project:test1)
将主机秘钥添加至github sshkey中： 
```
ssh-keygen -t rsa -C "youremail@example.com"
```
>将~/.ssh/id_rsa.pub内容拷贝到github-setting--SSH and GPG keys --New SSH key 

```
git remote add origin git@github.com:ananzhoujiaan/test1.git
git push -u origin master #这里一般需要先pull远程主机master节点 
<!--git pull origon master-->
git push origin master #后续需要同步执行
```
**删除注册**
```
git remote remove origin 
```

#### 从远程库克隆
git clone git@github.com:ananzhoujiaan/hello-world.git


---
## git分支管理

创建dev分支并切换:```git checkout -b dev``` \
创建dev分支：```git branch dev```\
切换分支 ```git checkout dev```\
查看当前分支情况：```git branch```\
分支合并到master:```git merge dev```\
删除dev分支```git branch -d dev```

<<<<<<< HEAD
=======

>>>>>>> 54f9219c92f509757755620401222e7db87c4b11
---

精华笔记\
查看分支：git branch

创建分支：git branch <name>

切换分支：git checkout <name>

创建+切换分支：git checkout -b <name>

合并某分支到当前分支：git merge <name>

删除分支：git branch -d <name>

---
