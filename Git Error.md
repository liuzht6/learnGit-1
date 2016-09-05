# some Git Error

标签（空格分隔）： Git learing

---

-  `git push -u origin master`
```
To git@github.com:******/Demo.git
 ! [rejected]        master -> master (non-fast-forward)
error: failed to push some refs to 'git@github.com:******/Demo.git'
hint: Updates were rejected because the tip of your current branch is behind
hint: its remote counterpart. Merge the remote changes (e.g. 'git pull')
hint: before pushing
again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.
```
解决方案：push前先将远程repository修改pull下来

a.  `git pull origin master`

b. ` git push -u origin master`

- fatal: remote origin already exists
解决方案：

a.` git remote rm origin`

b.` git remote add origingit@github.com:Githubusername/Github仓库名` 



