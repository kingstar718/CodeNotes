# shell学习

## 第一个shell脚本

将如下代码保存在新建文件`test.sh`中：
```
#!/bin/bash
echo "Hello World !"
```

`#!`是一个约定标记，他告诉系统这个脚本需要什么解释器来执行，即使用哪一种Shell。
echo命令用于向窗口输出文本。

运行Shell脚本的两种方式：
1、作为可执行程序：
```
chmod +x ./test.sh #使脚本具有执行权限
./test.sh # 执行脚本
```

注意：一定要写成`./test.sh`，而不是test.sh，运行其他的二进制程序也一样。
直接写成test.sh时，Linux系统会直接去PATH寻找有没有叫test.sh的文件；
而只用/bin，/sbin，/usr/bin，/usr/sbin等在PATH里，你的当前目录不在PATH里，所以找不到。
而写成`./test.sh`则是告诉系统：就在当前目录找。

2、作为解释器参数
这种方式是直接运行解释器，其参数就是shell脚本的文件名，如：
```
/bin/sh test.sh
/bin/php test.php
```
注意：这种方式运行的脚本，不需要再第一行指定解释器信息，写了也没用。
