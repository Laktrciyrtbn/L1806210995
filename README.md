TCP connect()扫描原理是：扫描主机通过TCP/IP协议的三次握手与目标主机的指定端口建立一次完整的连接。连接由系统调用connect开始。如果端口开放，则连接将建立成功；否则，若返回-1则表示端口关闭。设计一个程序做到
（1）输入目的IP地址以及端口范围；         
（2）设置获取的用户输入IP地址为远程IP地址；         
（3）从开始端口到结束端口依次扫描，每扫描一个端口创建一个新的套接字；         
（4）设置远程地址信息中的端口号为需要扫描的当前端口号；         
（5）连接到当前端口号的目的地址；         
（6）若连接成功（ connect（）函数返回0 ）则输出该端口为开启状态，否则输出该端口为关闭状态；         
（7）关闭当前套接字。
 进阶1，采用半连接提高扫描效率。
 进阶2，使用多进程进行端口扫描，进一步提高效率。 
