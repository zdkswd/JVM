# 性能监控工具

# 1.系统性能监控

> linux>     uptime

系统时间 运行时间 连接数(打开的终端数) 1，5，15分钟内系统平均负载(运行队列中的平均进程数)

> linux>  top

uptime CPU 内存 每个进程占CPU的情况

> linux>  vmstat  数值(采样频率) 数值(采样次数)

可以统计系统的CPU，内存，swap，io等情况

> linux>  pidstat

- 细致观察进程
- 需要安装  sudo apt-get install sysstat
- 监控CPU
- 监控IO
- 监控内存
- 参数 -p 数值(指定进程) -u(监控CPU) 数值(采样频率) 数值(采样次数) -t(显示线程)



# 2.Java自带工具

> jps

- 列出java进程，类似于ps命令
- 参数-q可以指定jps只输出进程ID，不输出类的短名称
- 参数-m可以用于输出传递给Java进程(主函数)的参数
- 参数-l可以用于输出主函数的完整路径
- 参数-v可以显示传递给JVM的参数



> jinfo

- 可以用来查看正在运行的Java应用程序的扩展参数，甚至支持在运行时，修改部分参数。
- -flag < name > 打印指定JVM参数值
- -flag [+|-] < name > 设置指定JVM参数的布尔值
- -flag < name > = < value > 设置指定JVM参数的值



> jmap

- 生成Java应用程序的堆快照和对象的统计信息
- jmap -histo 2972 > c:/s.txt
- jmap -dump:format=b,file=c:\heap.hprof 2972



> jstack

- 打印线程dump
- -l打印锁信息
- -m 打印java和native的帧信息
- -F强制dump,当jstack没有响应时使用



> JConsole

- 图形化监控工具
- 可以查看Java应用程序的运行情况，监控堆信息、永久区使用情况，类加载情况等。

> Visual VM

Visual VM是一个功能强大的多合一故障诊断和性能监控的可视化工具。