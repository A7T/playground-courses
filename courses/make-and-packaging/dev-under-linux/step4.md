通常实际可用的程序都是由多个子程序组合而成的，如果在一个主程序里调用了另一个子程序，那么该如何进行编译呢？

## 任务

1. 执行 <code exec="vi hello.c">vi hello.c</code> 再次打开 `hello.c` C语言程序代码文件，我们将以这个程序作为主程序。

2. 使用键盘上的方向键将光标移动到 `}` 一行的结尾。

3. 在键盘上点击 `a` 或 `i` 进入编辑模式。

4. 修改文件内容为：
```
#include <stdio.h>

int main(void){
    printf("Hello, World!\n");
    thanks();
}
```

5. 在键盘上点击 `ESC` ，然后输入 `:wq` 保存并退出Vim编辑器

6. 执行 <code exec="vi thanks.c">vi thanks.c</code> 创建并打开一个新的名为`thanks.c`的C语言程序代码文件，我们将以这个程序作为子程序。

7. 在键盘上点击 `a` 或 `i` 或 `s` 进入编辑模式。

8. 将下面的内容输入到终端中：
```
#include <stdio.h>

int thanks(void){
    printf("Thank you!\n");
}
```

9. 在键盘上点击 `ESC` ，然后输入 `:wq` 保存并退出Vim编辑器
