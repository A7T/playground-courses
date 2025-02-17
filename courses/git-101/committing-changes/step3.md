如果在一个已存在文件的文件夹（而非空文件夹）中进行版本控制，或在初始化完成的Git目录中添加了新的文件后，你应该开始追踪这些文件并进行初始提交。可以通过`git add`命令来指定所需的文件来进行追踪。

Git包含三个区域：工作目录(Working Directory)、 暂存区域(Staging Area)以及仓库本身。开发者首先在工作目录中对文件进行修改， 修改完成后将修改提交到暂存区域，并最终提交到仓库中。

Git的核心思想之一就是将开发活动分散的尽量小和频繁的提交中(small and frequent)。 暂存区域可以很好的帮助开发者每次只从工作目录中选取一部分修改提交到仓库中。

## 任务

使用 <code exec="git status">git status</code> 查看当前目录状态，可以看到有一个未被跟踪的文件`untracked`

使用 <code exec="git add untracked">git add untracked</code> 添加该文件(修改)到暂存区域(Staging Area)。

再次使用 <code exec="git status">git status</code> 查看当前目录状态，可以看到所有文件已被跟踪。


## Tips

如果你对某些文件进行了重命名或删除，你可能需要再次将其添加
到暂存区域(Staging Area)，你也可以使用`git mv`和`git rm`
来进行相应的操作，这样Git会自动完成其他工作。