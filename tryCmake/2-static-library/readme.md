上一节编译是直接将用到的其他文件编译到一个可执行文件中，这次我们将用到的库文件编译到一个.a二进制文件中，以便其他程序引入。

使用C++库的两种方法：
- 直接将用到的库的源码和自己的代码一起编译
- 使用库编译好的二进制文件（static library），link到自己代码编译出的二进制文件中。

