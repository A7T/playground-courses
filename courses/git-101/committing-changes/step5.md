一般我们总会有些文件无需纳入 Git 的管理，也不希望它们总出现在未跟踪文件列表。 通常都是些自动生成的文件，比如日志文件，或者编译过程中创建的临时文件等。 在这种情况下，我们可以创建一个名为 `.gitignore` 的文件，列出要忽略的文件的模式。

## 任务

运行下面的命令为你的Git目录创建`.gitignore`文件：

<code exec="echo '*.tmp' > .gitignore">echo '*.tmp' > .gitignore'</code>

<code exec="git add .gitignore">git add .gitignore</code>

<code exec="git commit -m 'add .gitigonre file">git commit -m 'add .gitigonre file</code>

## Tips

文件 `.gitignore` 的格式规范如下：

- 所有空行或者以 `#` 开头的行都会被 Git 忽略。

- 可以使用标准的 `glob` 模式匹配，它会递归地应用在整个工作区中。

- 匹配模式可以以 `/` 开头防止递归。

- 匹配模式可以以 `/` 结尾指定目录。

- 要忽略指定模式以外的文件或目录，可以在模式前加上叹号 `!` 取反。