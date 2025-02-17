在上一章中我们学习到了如何在Linux环境下编译自己的软件包，那么如果我们想安装其他开发者开发的软件应该如何操作呢？

Linux开源软件通常有多种发布形式，其中最基本的发布方式是以Tarball进行发布：软件开发者将将软件的所有源码文件以 tar 打包，然后再压缩（通常是 gzip），所以 tarball 文件一般的扩展名为 `*.tar.gz` 或是简写为 `*tgz`。不过，近来由于 bzip2 与 xz 的压缩率较佳，因此它对应的后缀名为 `*.tar.bz2` 、`*.tar.xz` 。

所以，Tarball 是一个软件包，将它解压之后，里面的文件通常会有：

- 源代码文件
- 检测程序（可能是 configure 或 config）
- 本软件的简易说明与安装说明（INSTALL 或 README）

通过阅读解压后的项目目录中的`INSTALL`或`README`文档就可以按照步骤完成安装，下面为大家展示典型的Tarball安装过程。


## 任务

我们将上一章的示例代码以Tarball形式进行了发布，依次执行下面的命令完成 `angle` 的安装。

1. 执行 <code exec="cd chapter3">cd chapter3</code> 进入章节目录

2. 执行 <code exec="ls -l">ls -l</code> 查看当前目录中的文件情况

3. 执行 <code exec="tar -xzvf angle-0.1.tar.gz">tar -xzvf angle-0.1.tar.gz</code> 将Tarball进行解压缩

4. 执行 <code exec="cd angle && ls -l">cd angle && ls -l</code> 进入项目源码目录并查看目录内容，可以看到目录有包含项目源码的 `src` 文件夹、说明文件 `README.md` 以及若干其他文件

5. 执行 <code exec="mkdir build && cd build">mkdir build && cd build</code> 创建 `build` 文件夹并进入，这样做的好处是可以保持原项目目录的整洁

6. 执行 <code exec="../configure">../configure</code> 进行项目配置，这个操作会启动对系统依赖、配置等的自动检查和配置，并生成针对于当前主机的 `Makefile` ，有关 `Makefile` 的内容我们已经在前面的章节中介绍过。由于软件开发者与使用者的实际环境可能存在不一致的情况(架构不同、软件版本不同等等)，因此对于复杂的项目使用工具根据使用者环境的实际情况生成 `Makefile` 是最为合理的

7. 执行 <code exec="make">make</code> 完成项目的编译

8. 执行 <code exec="sudo make install">sudo make install</code> 完成项目的安装

9. 执行 <code exec="angle">angle</code> 并与程序进行交互