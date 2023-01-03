# README

<https://www.bilibili.com/video/BV1vR4y1u77h>

## CMake Hello World 语法简介

`PROJECT` 关键字

```cmake
PROJECT(HELLO) # 指定项目名称是 HELLO，支持所有语言
PROJECT(HELLO CXX) # 指定项目名称是 HELLO，支持语言为 C++
PROJECT(HELLO C CXX) # 指定项目名称是 HELLO，支持语言为 C 和 C++
```

`SET` 关键字

用来设置变量，

```cmake
SET(SRC_LIST main.cpp) # SRC_LIST 变量包含了 main.cpp 
```

`MESSAGE` 关键字

向终端输出用户自定义的信息

```cmake
SEND_ERROR # 产生错误，就跳过
STATUS # 打印输出，前缀是 - 
FATAL_ERROR # 立即终止 cmake 过程
```

`ADD_EXECUTABLE` 关键字

生成可执行文件，

```cmake
ADD_EXECUTABLE(hello main.cpp) # 生成的可执行文件名是 hello，源文件为 main.cpp
```

语法的基本规则

- 变量使用 `${}` 读取，在 `IF` 语句中直接使用变量名。
- 指令 {参数1 参数2 参数3} ，参数之间用空格或者分号隔开。
- 指令是大小写无关的，参数和变量是大小写相关的。指令建议全部大写。

`ADD_SUBDIRECTORY` 指令

- 这个指令用于向当前工程添加存放源文件的子目录，并可以指定中间二进制和目标二进制存放的位置

## 安装

- 一种是代码编译后直接 `make install`
- 一种是打包时指定目录安装
  - 简单的可以这样指定目录， `make install DESTDIR=/tmp/test`
  - 稍微复杂一点可以这样指定目录， `./configure -prefix=/usr`

### 如何安装 HelloWorld

使用 `CMAKE` 一个新的指令： `INSTALL`，可以安装：二进制，动态库，静态库以及文件，目录，脚本等。

`CMAKE_INSTALL_PREFIX`