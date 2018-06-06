# [Linux netstat命令详解](https://www.cnblogs.com/ggjucheng/archive/2012/01/08/2316661.html)

netstat的输出结果可以分为两个部分

* 一个是Active Internet connections
* 另一个是Active UNIX domain sockets

## 常见参数

-a (all)显示所有选项，默认不显示LISTEN相关
-t (tcp)仅显示tcp相关选项
-u (udp)仅显示udp相关选项
-n 拒绝显示别名，能显示数字的全部转化成数字。
-l 仅列出有在 Listen (监听) 的服務状态

-p 显示建立相关链接的程序名
-r 显示路由信息，路由表
-e 显示扩展信息，例如uid等
-s 按各个协议进行统计
-c 每隔一个固定时间，执行该netstat命令。

提示：LISTEN和LISTENING的状态只有用-a或者-l才能看到

## 实用命令实例

1. 列出所有端口:
* 列出所有端口 netstat -a | more
* 列出所有 tcp 端口 netstat -at

1. 列出所有处于监听状态的 Sockets:
* 只显示监听端口 netstat -l
* 只列出所有监听 tcp 端口 netstat -lt
