# Git basic instructions

标签（空格分隔）： Git learing

---

###创建本地工作区
a.` mkdir dirname`
b.` cd dirname` 将这个库变成git所能够管理的库
c.` git init`
```
Initialized empty Git repository in /Users/Perdon/Documents/Programme-Preparation/learngit/.git/
```
 使用` ls -ah`可以查看本目录下隐藏的.git文件，用来记录管理git
###将文件从本地工作区添加到本地版本库
#####先将文件从可见的工作区添加到.git所管理的暂存区(stage)
a. ` git add filename`
将文件从.git管理的暂存区(stage)添加到.git为我们自动创建的第一个分支master
注意：可以add多个文件，再一次性进行commit
b.` git commit -m “标志信息”`
```
[master (root-commit) 81905ae] empty
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 readme.txt
```
（根据提示，本次commit一共修改了1个文件，一共有0处增加和0处减少）
#####将本地版本库文件添加到远程库
a.先在用户主目录（注意不是本目录而是Macbook-Perdon:~ Perdon$目录下看有没有id_rsa和id_rsa.pub这两个文件，若有则跳过b直接进入c）
b.获取你的电脑独有的SSH KEY:
` ssh-keygen -t rsa -C "***@qq.com"`
c.登陆GitHub，打开“Account settings”，“SSH Keys”页面：
然后，点“Add SSH Key”，填上任意Title，在Key文本框里粘贴id_rsa.pub文件的内容
d.将本地特定的仓库和Github上新创的仓库进行关联
在本地仓库内完成一下命令：
`git remote add origin git@github.com:yourGithubusername/Github仓库名.git`
e.第一次把本地版本库的所有内容推到远程库
origin:远程库      master:本地版本库的分支
` git push -u origin master`
之后需要修改的话使用：
` git push origin master`
#####将文件从Github远程库添加到本地工作区
` git clone git@github.com:yourGithubusername/Github仓库名.git`

---


##其他常用指令
###查看当前版本区的情况：
- ` git status`
```
# On branch master
# Changes not staged for commit:
#   (use "git add <file>..." to update what will be committed)
#   (use "git checkout -- <file>..." to discard changes in working directory)
#
#    modified:   readme.txt
```
`# modified:   readme.txt`
这里说明工作区的文件readme.txt有改变
`# Changes not staged for commit`
这里说明没有文件被add进暂存区



` git status`
```
# On branch master
# Changes to be committed:
#   (use "git reset HEAD <file>..." to unstage)
#
#       modified:   readme.txt
```
`# Changes to be committed`
这里说明已经有文件add进暂存区，但是没有进行commit



` git status`
```
# On branch master
nothing to commit (working directory clean)
```
说明所有在暂存区的文件都已经commit到分支，暂存区为空

###查看具体修改情况
- ` git diff filename`
```
diff --git a/readme.txt b/readme.txt
index 46d49bf..9247db6 100644
--- a/readme.txt
+++ b/readme.txt
@@ -1,2 +1,2 @@
-Git is a version control system.
+Git is a distributed version control system.
 Git is free software.
```
###查看历史纪录
- ` git log --pretty=oneline`
```
3628164fb26d48395383f8f31179f24e0882e1e0 append GPL
ea34578d5496d7dd233c827ed32a8cd576c5ee85 add distributed
cb926e7ea50ad11b8f9e909c05226233bf755030 wrote a readme file
```
###进行不同版本的选择：
- ` git reset --hard commit_id`
跳到上一个版本：
` git reset --hard HEAD^`
跳到上面第100个版本
` git reset --hard HEAD~100`

###撤销修改
a.撤销工作区的修改：（实质是将最新版本库的文件给到工作区）
` git checkout -- filename`
b.撤销暂存区的修改：
把暂存区的修改回退到工作区
HEAD:最新版本
` git reset HEAD filename`
再撤销工作区的修改：
` git checkout -- filename`
c.撤销版本库的修改
使用回退到上一个版本的方法

###删除文件
a.删除工作区文件
` rm filename`

b.删除版本库文件
` git rm filename`

c.删错工作区文件想要还原：
` git checkout -- filename`

d.删除Github上面的文件
` git commit -a -m "A file was deleted"`
` git push origin master`
