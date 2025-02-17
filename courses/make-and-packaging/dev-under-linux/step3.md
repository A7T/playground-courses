我们平时所说的程序，是指双击后就可以直接运行的程序，这样的程序被称为可执行程序（Executable Program）在 Windows 下，可执行程序的后缀有 `.exe` 和 `.com`（其中 `.exe` 比较常见）；在类 UNIX 系统（Linux、Mac OS 等）下，可执行程序没有特定的后缀，系统根据文件的头部信息来判断是否是可执行程序。

可执行程序的内部是一系列计算机指令和数据的集合，它们都是二进制形式的，CPU 可以直接识别，毫无障碍；但是对于程序员，它们非常晦涩，难以记忆和使用，因此诞生了诸如我们刚才编写的C语言程序等高级编程语言。

但是对于CPU，C语言代码就是天书，根本不认识，CPU只认识几百个二进制形式的指令。这就需要一个工具，将C语言代码转换成CPU能够识别的二进制指令，也就是将代码加工成可执行程序；这个工具是一个特殊的软件，叫做编译器(Compiler)。

Linux 下常用的是 GUN 组织开发的 GCC，Linux 发行版通常都自带 GCC。


## 任务

执行：

<code exec="gcc hello.c -o hello">gcc hello.c -o hello</code>

执行 <code exec="ls -l">ls -l</code> 查看当前目录，可以看到生成了名为 `hello` 的可执行文件。

执行 <code exec="./hello">./hello</code> 运行该可执行文件并查看运行结果。


## Tips

更多有关GCC的使用方法请参考：
https://www.runoob.com/w3cnote/gcc-parameter-detail.html 