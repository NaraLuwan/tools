在 Linux 服务器上或安装了 Python 的机器上，Python自带了一个WEB服务器 SimpleHTTPServer。

可以很简单的使用  python -m SimpleHTTPServer 快速搭建一个http服务，提供一个文件浏览的web服务。

### 命令如下：
- python -m SimpleHTTPServer 8000

把当前目录发布到8000端口。但是这条命令是当前运行的，不是后台运行的，也就是说如果Ctrl + C，则该端口就会关闭。

- python -m SimpleHTTPServer 8000 &
在上述命令的最后加一个 & ，则该命令产生的进程在后台运行，不会影响当前终端的使用（在只有一个bash的环境下）。生成的新的进程为当前bash的子进程，所以如果关闭当前bash，相应的子进程也会被kill掉。

- nohup python -m SimpleHTTPServer 8000 &
在命令的开头加一个nohup，忽略所有的挂断信号，如果当前bash关闭，则当前进程会挂载到init进程下，成为其子进程，这样即使退出当前用户，服务依然可用。