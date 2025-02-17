在任何一个阶段，你都有可能想要撤消某些操作。注意，有些撤消操作是不可逆的。 这是在使用 Git 的过程中，会因为操作失误而导致之前的工作丢失的少有的几个地方之一。

如果已经修改了两个文件并且想要将它们作为两次独立的修改提交， 但是却意外地输入 `git add *` 暂存了它们两个，那么使用 `git reset` 命令可以将文件从暂存区中移除。

如果你需要连工作目录中的修改一并回退，则可以使用 `git reset --hard` 命令，这个命令将会将你的工作目录连同暂存区域一并回退到Git仓库中上一次提交的状态。

## 任务

依次运行下面的命令，并观察系统的输出：

1. 添加一个新文件：
    <pre>
    <code exec="echo 'This is a new file' > new_file">echo 'This is a new file' > new_file</code>
    <code exec="git add new_file">git add new_file</code>
    </pre>

2. 查看当前状态：
    <pre>
    <code exec="git status">git status</code>
    </pre>

3. 回退暂存区修改，并查看状态：
    <pre>
    <code exec="git reset">git reset</code>
    <code exec="git status">git status</code>
    </pre>

4. 修改现有文件，并将新增文件提交到暂存区：
    <pre>
    <code exec="echo 'This is a new line' > old_file">echo 'This is a new line' > old_file</code>
    <code exec="git add .">git add .</code>
    </pre>

5. 回退所有修改，并查看状态：
    <pre>
    <code exec="git reset --hard">git reset --hard</code>
    <code exec="git status">git status</code>
    </pre>