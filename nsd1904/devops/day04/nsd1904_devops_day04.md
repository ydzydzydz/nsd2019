# nsd1904_devops_day04

CI / CD：持续集成 / 持续交付

流行的自动化运维平台：docker / k8s / ansible / git / jenkins

准备三台机器

- node4.tedu.cn: 程序员PC
- node5.tedu.cn: gitlab服务器  -> 4GB以上内存
- node6.tedu.cn: jenkins

## git

- 软件版本管理系统
- 分布式

```shell
# 安装
[root@node4 ~]# yum install -y git
# 配置基础信息
[root@node4 ~]# git config --global user.name "zzg"
[root@node4 ~]# git config --global user.email "zzg@tedu.cn"
[root@node4 ~]# git config --global core.editor vim
# 查看
[root@node4 ~]# git config --list
[root@node4 ~]# cat ~/.gitconfig 
```

### git的工作区域

- 工作区
- 暂存区
- 版本库

```mermaid
graph LR
w(工作区)--git add-->s(暂存区)
s--git commit-->g(版本库)
```

### 初始化版本库

- 项目之初，直接构建

```shell
[root@node4 ~]# git init mypro
初始化空的 Git 版本库于 /root/mypro/.git/
[root@node4 ~]# cd mypro/
[root@node4 mypro]# ls -A
.git
```

- 已有项目

```shell
[root@node4 ~]# mkdir myweb
[root@node4 ~]# cd myweb
[root@node4 myweb]# echo '<h1>Hello World</h1>' > index.html
[root@node4 myweb]# git init
初始化空的 Git 版本库于 /root/myweb/.git/
[root@node4 myweb]# ls -A
.git  index.html
```

### 添加文件到暂存区

```shell
# 查看状态
[root@node4 myweb]# git status
[root@node4 myweb]# git status -s
?? index.html

# 添加到暂存区
[root@node4 myweb]# git add .
[root@node4 myweb]# git status
[root@node4 myweb]# git status -s
A  index.html

# 从暂存区撤出文件
[root@node4 myweb]# git rm --cached index.html 
[root@node4 myweb]# git status -s
?? index.html
```

### 确认至版本库

```shell
[root@node4 myweb]# git add .
[root@node4 myweb]# git status -s
A  index.html
[root@node4 myweb]# git commit  # 在跳出的vim中写日志
[root@node4 myweb]# git status
# 位于分支 master
无文件要提交，干净的工作区

# 继续提交
[root@node4 myweb]# cp /etc/hosts .
[root@node4 myweb]# git status -s
?? hosts
[root@node4 myweb]# git add hosts 
[root@node4 myweb]# git status -s
A  hosts
[root@node4 myweb]# git commit -m "add hosts"
[root@node4 myweb]# git status
# 位于分支 master
无文件要提交，干净的工作区
```

### 文件改名

```shell
[root@node4 myweb]# git mv hosts zhuji
[root@node4 myweb]# ls
[root@node4 myweb]# git status
[root@node4 myweb]# git status -s
R  hosts -> zhuji
[root@node4 myweb]# git commit -m "mv hosts zhuji"
[root@node4 myweb]# git status
# 位于分支 master
无文件要提交，干净的工作区
```

### 删除文件

```shell
[root@node4 myweb]# git rm zhuji 
[root@node4 myweb]# git status
[root@node4 myweb]# git commit -m "rm zhuji"
[root@node4 myweb]# git status
# 位于分支 master
无文件要提交，干净的工作区

```


















