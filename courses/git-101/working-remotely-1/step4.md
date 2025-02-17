当你准备好将你的修改推送到远端仓库时，你需要使用`git push`
命令。一个典型的Git工作流通常在完成若干次小的修改和
提交(Commit)后，例如完成某一个具体的任务或重要节点后，
使用`git push`将代码推送到远端以便他人可以使用。

`git push`命令后可附加两个参数，第一个参数是远端仓库的名称，
如在上一步中添加的`origin`。第二个参数是期望提交到的分支(Branch)
的名称。默认情况下，所有Git仓库都有(main/master)分支作为默认
的工作分支。

## 任务

使用 <code exec="git push -u origin master">git push -u origin master</code> 命令将提交推送到远端仓库。
