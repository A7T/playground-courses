在上一节内容中，我们学习了如何将从网上下载得到的Tarball安装到机器中，虽然只需要简单的几行命令就可以完成配置和安装，但是由于安装过程中包含了配置、编译等等过程，对于复杂庞大的项目来说，还是非常耗时的。同时，也不是每个人都会进行源码编译，因此如果能预先在相同的硬件与操作系统上编译好才发布的话，就可以让相同的操作系统发行版具有完全一致的软件版本了，再加上简易的安装、移除、管理等机制的话，对于软件管理就容易多了。

基于这个需求，就诞生了软件管理程序，知名的软件管理程序有`RPM`、`DPKG`等，下面的内容将以 `RPM` 为例进行介绍。

RPM 全名 RPM Package Manager(http://rpm.org/)，是以一种数据库记录的方式将你所需要的软件安装到你的 Linux 系统的一套管理机制

最大的特点：将你要安装的软件先编译过，并且达成 RPM 机制的包装文件，通过包装文件里面的默认的数据库记录，记录这个软件要安装的时候必须具备的相依属性软件，当安装在你的 Linux 主机时，RPM 会先依照软件里的数据查询 Linux 主机的相依属性是否满足，若满足则安装，若不满足，则不安装。那么安装的时候就将该软件的信息整个写入 RPM 的数据库，以便未来的查询、验证与卸载，优点：

1. 不需要再重新编译：由于已经变异完成并且打包完毕，所以软件传输与安装上很方便
2. 由于软件的信息都已经记录在 Linux 主机的数据库上，很方便查询、升级与卸载

我们已经将之前的三角函数计算软件打包成了名为 `anglerpm-0.1-1.x86_64.rpm` 的 `rpm` 软件包，其命名可以体现如下信息：

- 文件名通常遵循这样的格式：`{Name}-{Version}-{Release}.{Arch}.rpm`
- `anglerpm`: 软件名为 `anglerpm` (rpm后缀与手动安装方式区分)
- `0.1-1`: 软件版本为 `0.1` ,编译版本为 `1`(在源代码主体版本没有变化的情况下，编译过程中可能加入了新的patch补丁，修改了编译脚本等等情况下需要重新编译时，bump编译版本)
- `x86_64`: 该rpm软件包支持的平台为x86_64，不同架构的rpm版本通常不能通用

下面我们将展示如何安装该rpm软件包

## 任务 

1. 执行 <code exec="cd /home/coder/make-and-packaging/chapter3/">cd /home/coder/make-and-packaging/chapter3/</code> 返回章节目录。

2. 执行 <code exec="wget https://github.com/opensourceways/playground-courses/releases/download/v0.1/anglerpm-0.1-1.x86_64.rpm">wget https://github.com/opensourceways/playground-courses/releases/download/v0.1/anglerpm-0.1-1.x86_64.rpm</code> 下载rpm软件包。

3. 执行 <code exec="sudo rpm -i anglerpm-0.1-1.x86_64.rpm">sudo rpm -i anglerpm-0.1-1.x86_64.rpm</code> 安装rpm软件包。

4. 执行 <code exec="anglerpm">anglerpm</code> 并与程序交互，查看安装结果

可以看到使用 `rpm` ，可以仅用一条命令就完成我们编写的软件的安装，非常方便，那么对于更复杂的软件呢？

5. 执行下面的命令，下载openEuler 20.03 LTS SP1中的 `mariadb-server-10.3.9` :
    <pre>
    <code exec="wget https://mirrors.tuna.tsinghua.edu.cn/openeuler/openEuler-20.03-LTS-SP1/everything/x86_64/Packages/mariadb-server-10.3.9-9.oe1.x86_64.rpm">wget https://mirrors.tuna.tsinghua.edu.cn/openeuler/openEuler-20.03-LTS-SP1/everything/x86_64/Packages/mariadb-server-10.3.9-9.oe1.x86_64.rpm</code>
    </pre>

6. 执行 <code exec="sudo rpm -i mariadb-server-10.3.9-9.oe1.x86_64.rpm">sudo rpm -i mariadb-server-10.3.9-9.oe1.x86_64.rpm</code> 尝试安装这个rpm

可以看到安装失败了，因为软件 `mariadb-server` 有其他依赖，但是在我们的系统中并没有安装这些依赖，如果要正常安装，则需要先安装完这些依赖的软件。对于庞大且复杂的软件来说，软件的依赖可能达到上百款，同时依赖又有自己的依赖，手动完成软件依赖的查找和安装几乎是不可能完成的任务。