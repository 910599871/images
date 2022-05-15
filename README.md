# images
My first repository on Github

I love ☕: 🐜: and 🍕



yum list | grep docker 
#查看yum列表中有没有docker这个安装的依赖文件包

yum makecache
#进行元数据缓存

yum remove + 要移除的包名       
#这就就可以将一些已经安装的包进行删除，这个只能用于通过yum安装的，要是二进制安装的则在不同的安装目录下，是不能被移除删除的

yum update
#更新目前安装的包的最新动态，升级版本信息，但是这样是不能直接升级到最新的，因为根据内核而定的，是更据考虑适配当前系统的版本而定

1.1了解linux云计算的基本概念及linux基础
什么是云计算，将一切的资源整合，通过各项的服务来进行分配相关的资源属性。
linux：其中linux的发展史，从最基础的unix转变而来的，进行开源的操作系统。遵守GNU协议，所谓的牛岭。
2.linux系统中常用的一些操作系统，Redhat,suse,centos,ubuntu,debian,redflag,麒麟，深度，中标麒麟等等。都是通过底层的内核进行交互。
3.最基础的linux系统的安装及配置基础。了解系统的安装步骤。
常见的安装英文字样：
install or upgrade an existing system       #全新安装或更新一个已经存在的系统
rescue installed system                  #救援安装系统模式
boot from local drive                    #从本地设备磁盘进行引导
4.安装操作系统中对系统的各项系统和数据进行分区。
/ ：      系统根分去
/boot :    系统引导分区
/swap :    系统交换空间
/data:     数据分区
安装完成后的系统配置。

1.2如何在虚拟软件WMware 中安装操作系统以及使用该软件

1.如何增加虚拟机的可用内存
2.如何添加硬件设备，注意在安装虚拟机开机状态下不能添加硬件设备。
3.对虚拟软件的控制切换，使用alt+crtl进行虚拟软件与win直接的切换
4.如何正确的关闭使用的虚拟机。
5.如何结束虚拟机任务。通过虚拟软件ctrl+alt+ins，相当于物理环境中的ctrl+alt+del
6.如何显示模式切换
7.如何做网络配置，是NAT模式，还是桥接模式，还是only模式
8.如何删除虚拟机
9.如何对虚拟机进行快照管理
10如何进行ISO光盘文件进行挂载



如何在图形界面下放大或缩小命令行
ctrl+shift+ +    放大图形化界面的字体大小
ctrl+-         缩小图形界面下的字体大小
如何对满屏的界面进行清屏处理
ctrl+l         清屏


第二章 linux基础操作

2.1安装完成后如何正确认识基本的命令

首先在安装完成后的操作系统，认识下操作系统的界面中都是什么内容
了解下在linux中的终端介绍

在安装完成后的有图形化界面和命令行界面，其中的图形化界面是一个程序，不同的操作系统，所使用的开发语言的操作界面也是不一样的，有KDE界面，GONE界面，运用C语言与C++进行编译，在linux中，图形界面是可以删除的，主要也是运用在命令行模式下。
1.图形化界面下：tty1
命令行字符界面：tty2-tty6,通过图形界面下ctrl+alt+f1到f6进行切换。
2.在图形界面下，打开一个图形界面，通过ctrl+shift+t可以重新打开终端界面，在打开的图形界面下我们称为PTS虚拟终端。（pts:pseudo terminal slave）所谓的伪终端、
3.了解打开的终端下shell提示符。
root:  为#
普通用户：$

4.了解BASH shell的基本语法
首先我们了解下常见的shell,就是常见的壳，也是用C语言编写的，同时shell也是一门编程语言了，这样的情况下我们也可以将shell写成脚本，进行运维或者编程使用。shell命令解释器。我们最常见的就是bash,sh.csh，tcsh,ksh.等以红帽为基础的，则已debain为基础的zsh，功能非常强大。我们平常说的linux是指的内核，在以内核的情况下，进行二次开发出来的系统。

远程连接：
    ssh协议：secure shell
[root@qtxsm ~]#ss –ntl    #查看系统是否监听于tcp协议的22号端口；
[root@qtxsm ~]# ifconfig     #查看网络地址，minia系统下但是要安装net-tools工具
[root@qtxsm ~]# ip addr     #也是可以查看网络地址








创建完成环境后，第一步就是关闭所有机器防火墙，给后期的搭建服务提供便利。这样也是关键的一步。

关闭防火墙：
[root@qtxsm ~]#systemctl stop  firewalld && systemctl disable firewalld - - now  #将防火墙关闭，开机不启动
[root@qtxsm ~]# vi /etc/selinux/config     #修改selinux配置文件内容
selinux=disabled   #将配置文件中的这个选项改成这样
之后重启服务器
[root@qtxsm ~]#reboot

或在6的环境下
[root@qtxsm ~]#service iptables stop
[root@qtxsm ~]#chkconfig iptables off

输入命令的语法规则

命令 【选项】 (参数) 【选项的值】 【数的值】
在命令结束后用空格进行分隔，例：
[root@centos7~]# ls /etc/passwd   在ls查看命令后用空格分割开选项的内容

5.常见的选项（参数）：-h, - -h  -y  -l  -a  -d  等等
6.基本操作命令：

echo命令
表示一个打印信息，所有不清楚使用命令的可以通过man,或着- -h来查询使用方法。
有些命令是不能通过- -h来获取帮的。
可以通过man  echo来查询使用echo的使用方法，下面举几个例子可以看下echo使用的不同场合。
服务器再用的时候也不是一个人在用，是有好多的人员一起在使用，同时使用的也是不同的项目，这样我们在使用的项目中，多人会共同在一个组里使用不同的用户名，我们可以理解为多用户模式下，同一组或不同组使用的服务器。这样自然就避免不了会有重启服务器的时候，这样我们会在关机的时候，通知下其它使用终端的使用人员，在什么时候关机，在什么时候做什么事，就要广播给各个使用者知道。

例子：
[root@master1 ~]# echo hell0 > /dev/pts/1
[root@master1 ~]# echo 我要关机了，能做好准备吗？ > /dev/pts/1
以上就显示了一个要做什么事，给提个醒。以上我们可以理解为通过echo这个命令，写上需要做什么事情，通常写为英文的格式，有可能会有不同的显示文本，会出现乱码，在通过重定向符号“>”将所需要的内容输出给设备文件目录/dev/ 下的终端模式/pts/下的哪一个界面模式。同时也可以通过其它的命令进行广播给其它的用户知道，该命令就是后面所说的wall命令。

 



[root@qtxsm ~]# echo !$    #表示打印上一步执行的什么命令

[root@qtxsm ~]# echo http   #打印一个输出，也可以将打印的内容通过输出或输入重定向的符号（>或<）或者是追加到某个文件（>>:追加符号）
[root@qtxsm ~]# echo $SHELL  大写的SHELL可以查看shell的类型。
[root@qtxsm ~]#echo $PATH   环境变量里面去找

wall命令

这个命令可以广播到其他用户，提示执行什么命令，希望其他的组人员了解

[root@qtxsm ~]# wall welcome to linux
[root@qtxsm ~]# 
Broadcast message from root@qtxsm (pts/0) (Tue Nov  9 04:39:40 2021):

welcome to linux

通过这样就可以通知其他的伪终端进行广播要做什么事，希望大家引起主要。


[root@master1 ~]# wall 大家好，在多少分钟后，我这边要关机，希望其他同事抓紧时间进行文档的保存。

Broadcast message from root@master1 (pts/0) (Thu Mar 24 14:56:29 2022):

大家好ﻞL䝜¨壞Z寞Q䝈^F蝒^_䝐^NﻞL坈^Q辞Y边襞A䝅³坜ºﻞL州L坜^[䝅¶亞V䝐^L乞K坊^S紧块¶蝗´辞[蠞L坖^G档杚^D侞]嬞X❀^B


通过wall这条命令我们可以很容易看到，这个在英文情况下能好好的显示，中文显示乱码，但是这个可以显示出是从哪个终端上或者是从什么发出来的信息，就上面写的很详细，广播信息来自什么地方的什么，谁发出来的。
type命令

通过type查看一个命令是外部命令还是一个内部命令，所谓的外部命令，就是一个应用服务或者除shell以外的直接调用shell内核使用的命令。顾名思义，内部命令就是直接通过shell调用内核的命令。

[root@qtxsm ~]# type cd
cd is a shell builtin

pwd 命令
查看当前所在的路径下
 [root@qtxsm etc]# pwd
/etc
[root@qtxsm etc]#

whoami 命令
当前在什么用户模式下
[root@qtxsm ~]# whoami
root
su 命令

切换用户
[root@qtxsm ~]# su - root

tail 命令
显示文件的多少行，默认显示一个文件的后十行，也可以通过参数来显示多少行，也可以作为一个显示日志。
 [root@qtxsm ~]# tail /etc/passwd
games:x:12:100:games:/usr/games:/sbin/nologin
ftp:x:14:50:FTP User:/var/ftp:/sbin/nologin
nobody:x:99:99:Nobody:/:/sbin/nologin
systemd-network:x:192:192:systemd Network Management:/:/sbin/nologin
dbus:x:81:81:System message bus:/:/sbin/nologin
polkitd:x:999:998:User for polkitd:/:/sbin/nologin
tss:x:59:59:Account used by the trousers package to sandbox the tcsd daemon:/dev/null:/sbin/nologin
sshd:x:74:74:Privilege-separated SSH:/var/empty/sshd:/sbin/nologin
postfix:x:89:89::/var/spool/postfix:/sbin/nologin
chrony:x:998:996::/var/lib/chrony:/sbin/nologin
[root@qtxsm ~]#



head命令
显示文件的前十行内容，也可以通过其他的参数指定显示多少行 –n来指定显示数
[root@qtxsm ~]# head /etc/passwd
root:x:0:0:root:/root:/bin/bash
bin:x:1:1:bin:/bin:/sbin/nologin
daemon:x:2:2:daemon:/sbin:/sbin/nologin
adm:x:3:4:adm:/var/adm:/sbin/nologin
lp:x:4:7:lp:/var/spool/lpd:/sbin/nologin
sync:x:5:0:sync:/sbin:/bin/sync
shutdown:x:6:0:shutdown:/sbin:/sbin/shutdown
halt:x:7:0:halt:/sbin:/sbin/halt
mail:x:8:12:mail:/var/spool/mail:/sbin/nologin
operator:x:11:0:operator:/root:/sbin/nologin


head在参数使用的过程中，后面所要跟的参数，直接取决于是如何使用
语法：head  +  -  + 参数 + 数值 + 目录文件
例：[root@qtxsm ~]#head -c 10 /etc/passwd
表示在以开头以10字节的显示该文件的信息
-c: 表示字节，一个字符算一个
-n: 表示行数，后面的参数写多少就显示多少行
-q: 不显示包含给定文件名的文件头
-v: 总是显示包含给定文件名的文件头或者是版本信息。
ls 命令
查看当前目录下有那些文件（list）
常见的有命令后面跟的选项
ls  -a  查看所有目录下的文件
ls  -l  查看详细的文件内容
ls  -S  按排序的方式列出文件
等等很多选项
[root@qtxsm yum.repos.d]# ls -l
total 36
-rw-r--r--  1 root root 1684 Nov  9 02:53 CentOS-Base.repo
-rw-r--r--  1 root root 1663 Oct 30 05:18 CentOS-Base.repo.backup
-rw-r--r--. 1 root root 5701 Nov 23  2018 CentOS-Vault.repo
[root@qtxsm yum.repos.d]# ls -l
total 36
-rw-r--r--  1 root root 1684 Nov  9 02:53 CentOS-Base.repo
-rw-r--r--  1 root root 1663 Oct 30 05:18 CentOS-Base.repo.backup
-rw-r--r--. 1 root root 1309 Nov 23  2018 CentOS-CR.repo

[root@qtxsm yum.repos.d]# ls -lS
total 36
-rw-r--r--. 1 root root 5701 Nov 23  2018 CentOS-Vault.repo
-rw-r--r--  1 root root 1684 Nov  9 02:53 CentOS-Base.repo


cd 命令
对目录的路径进行切换，在此目录下，我们要了解下什么是绝对目录，什么是相对路径
其中在当前目录下cd  . . 表示上一级目录，cd .表示的是当前目录
history命令
查看都有那些命令记录，可以用ctrl+r、！+数字或！+字母，查看最近使用过的命令
mkdir 命令
创建一个目录文件，也可以创建目录后的子目录，进行递归
mkdir  -p /etc/a/b   理解为创建一个在etc目录下创建一个a目录下创建一个b
也是可以通过大括号创建多个目录

[root@qtxsm ~]#mkdir {a,b,c,,f}  #创建出a,b,c,d,e,f文件目录
mv 命令
对一个文件或文件目录进行重命名或移动
touch 命令
创建一个空文件，不能创建目录
shutdown命令
关机命令，后面选项参数，比方shutdown 22:00 在22点的时候关机，也可以写在几小时或几分钟后关机，或shutdown  -h now  现在关机。关机的方法有好多，也有poweroff halt ,init0等
reboot 命令
重启服务器，也可以使用init 6来实现重启服务
cp 命令
拷贝文件，具体使用方法
scp命令
通过SSH连接的服务器之间进行传输文件
alias命令
别名的使用
有临时的创建别名，永久性的创建别名
临时举例：
[root@qtxsm ~]# alias ls =`ls –l` 别名是随便创建的随意取名 
永久性举例：
在隐藏文件 .bashrc下写一个别名就可以
root@qtxsm ~]# vim .bashrc  在配置文件里面添加需要改的别名文件就行
root@qtxsm ~]# source .bashrc   这样的情况下通过source重启别名生效
若是全部生效，必须在/etc/bashrc下更改，所有用户都生效。而以上则是在当前用户的情况生效。

删除别名：unalias +别名称
rm命令
删除命令，要是删除某个文件或着是某个目录，只要rm +文件名称就删除文件或目录，若是有子目录的则要用递归删除，rm  -r +目录名称*，但是我们要慎用rm  -rf /*，多用mv。

cat 命令
查看一个文件的内容也可以使用less,more,head,tail 查看里面的文件，要是文件少的话可以用cat查看，要是文件内容多的话，就用more 或less 

df命令
df-hT可以查看文件系统的使用情况。
diff 命令
对比两个编辑文件的不同，或分别进行编辑
例：
[root@qtxsm ~]# diff vim /etc/passwd  /etc/shadow
date命令
查看、修改时间命令
[root@qtxsm ~]# date "+%F"
2021-11-10
[root@qtxsm ~]# date "+%F %H:%M:%S"           #简写
2021-11-10 02:31:31
或者
[root@qtxsm ~]# date "+%Y-%m-%d %H:%M:%S"    #全写
2021-11-10 02:31:31
其中小写的y是显示年的后两位数
-s 是设置时间

hwclock命令
查看硬件时间
timedatectl 命令
查看详细的时区： timedatectl  list-timezones   列出时区
                 timedatectl  set-timezones   设置时区
tzselect命令
[root@qtxsm ~]# echo “TZ=’Asia/shanghai’;export TZ”  >>  /root/.bash_profile
将变量追加到.bash_profile文件中

切换到字符界面
[root@qtxsm ~]# systemctl  isolate multi-user.target  切换字符界面
[root@qtxsm ~]# systemctl  default graphical.target  设置图形界面





第三章 熟悉linux的文件系统和XFS文件系统的备份和恢复
/bin: 是一个软链接文件，里面存放的可执行文件命令
/sbin: 存放系统管理程序
/   : 是一个根目录
/dev: 设备的目录文件，是块设备文件，
/boot: 存放系统启动的一些引导文件
/etc: 里面放的是二进制的配置文件，一些服务的配置文件
/proc: 是一个动态的进程目录，里面是一些进程的，是内存的映射
/home: 存放用户的家目录文件
/lib: 存放的是软连接的库文件
/lib64:存放的是软连接的64位的库文件，相当于win里面的dll文件，就是动态库文件
/mnt : 是一个文件设备挂载目录，可以将一个光驱或者U盘挂载里面
/tem: 是一个存放缓存的临时文件目录
/run: 是一个运行命令，可以看到的是进程的PID。 
/srv : 是放的一些服务
/sys :放的是一些硬件信息
/usr :存放应用程序，命令程序文件，程序库，手册和其他文档
/var: 系统默认日志的存放目录
/root： 是root用户的家目录

[root@qtxsm ~]#cat /proc/cpuinfo   #cpu信息
[root@qtxsm ~]#cat /proc/meminfo   #内存信息

tree命令可以查看树目录，要是没有，需要下载 

在用VIM编辑的时候，直接退出后，又重新开启了一个文件，这样就会出现问题，没有正常退出，这样就产生了一个隐藏的缓存文件，在这样的情况下我们可以直接删除隐藏的缓存文件。

XFS提供了xfs和xfsrestore 工具协助备份xfs文件系统中的数据。xfsdump按inode顺序备份一个xfs文件系统。可以支持8EB，
默认的是0，表示完全备份。
level 1-9依次增量备份。每提高一个级别等于上一个备份基础上只备份产生变化出来的部分。
yum命令
mv /etc/yum.repos.d/CentOS-Base.repo /etc/yum.repos.d/CentOS-Base.repo.backup

yum-config-manager --add-repo=http://mirrors.aliyun.com/repo/Centos-7.repo

wget-O /etc/yum.repos.d/CentOS-Base.repo http://mirrors.aliyun.com/repo/Centos-7.repo   这个必须安装wget工具包，要是有网的情况下，可以将yum –y install wget下载下来。
或者
curl-o /etc/yum.repos.d/CentOS-Base.repo http://mirrors.aliyun.com/repo/Centos-7.repo 

yum makecache 

yum-config-manager

1.简介
yum-config-manager命令的本质是对/etc/yum.repos.d/(库数据的储存位置)文件夹下文件的管理。
2.安装
如果在系统上没有yum-config-manager命令的话，使用yum -y install yum-utils。
3.添加仓库
执行完下边的命令后就会在/etc/yum.repos.d下产生源文件。
下边都是以centos7为例。
阿里云源 ：
yum-config-manager --add-repo= http://mirrors.aliyun.com/repo/Centos-7.repo
yum-config-manager --add-repo=http://mirrors.aliyun.com/repo/epel-7.repo
163源：
yum-config-manager --add-repo=http://mirrors.163.com/.help/CentOS7-Base-163.repo
若是出现了yum源中不能安装的情况下，我们要配置一个yum源地址，或者我们将原来的repo源的地址给重新备份下来，我们通过本地的yum源仓库进行。
[root@node1~]#curl-o/etc/yum.repos.d/CentOS-Base.repohttp://mirrors.aliyun.com/repo/Centos-7.repo 
[root@node1 ~]#yum makecache
若是没有了wget或者没有了使用不了yum-config-manager，就要重新安装wget这个工具和 yum-utils工具
[root@node1 ~]# yum -y install yum-utils
[root@node1 ~]# yum-config-manager --add-repo= http://mirrors.aliyun.com/repo/Centos-7.repo
[root@node1 ~]# yum-config-manager --add-repo=http://mirrors.163.com/.help/CentOS7-Base-163.repo
Loaded plugins: fastestmirror
adding repo from: http://mirrors.163.com/.help/CentOS7-Base-163.repo
grabbing file http://mirrors.163.com/.help/CentOS7-Base-163.repo to /etc/yum.repos.d/CentOS7-Base-163.repo
repo saved to /etc/yum.repos.d/CentOS7-Base-163.repo
出现上述就表示添加成功了。

xfsdump常用的参数
xfsdump 
ls /usr/sbin/xfsdump 
ls /usr/sbin/xfsrestore
这些都只能由root命令来执行
-L: <session Label>备份的会话标签，这里写对此次备份的说明。如： dump_sdb1_v2 ，
可以随意写
-M: <media label> 储存设备的标签，这里写对备份设备的简易描述。如： sdb1_v2 ，可以
随意写。
-I:是L的小写，就是指定level，有0~9工10个等级，默认为0，即完整备份。
-l:大写的i,从/var/lib/xfsdump/inventory 列出目录备份的信息状态。
-f:后面接产生的文件和destination file。例如/dev/sto设备文件名或其他一般文件名
完全备份：每次都把指定的备份目录完整的复制一遍，不管目录下的文件有没有变化；如CP
增量备份：每次将之前（第一次，第二次，直到前一次）做过备份之后有变化的文件进行备份；
差异备份：每次都将第一次完整备份以来有变化的文件进行备份。如：rsync备份。
ls  /dev/sd* 可以查看包含sd的所有磁盘。

fdisk命令或gdisk命令
fdisk /dev/sd* 将sd命令中创建一个分区的命令，
mkfs.xfs /dev/sdb 将sdb中创建的磁盘进行格式化
blkid 查看分区的目录
之后进行创建一个目录，在将mount挂载到目录下面
[root@qtxsm~]# mkfs.xfs /de/sdb1    #格式化磁盘
[root@qtxsm~]# blkid /dev/sdb1       #查看详细信息
[root@qtxsm~]# mkdir /test           #创建一个目录为test
[root@qtxsm~]# mount /dev/sdb1 /test/   #把磁盘sdb1挂载到test这个目录下
[root@qtxsm~]# df –Th               #查看都有那些磁盘分区

[root@qtxsm ~]# mount  /dev/sdb /test   #将/dev/sdb中的磁盘挂载到/test这个目录下，就是在test下的文件里的数据全部保存到了dev/sdb这个分区上。

文件的备份：
xfsdump –f /iop/dump_sdb1  /dev/sdb1    #将备份的文件放在opt这个目录下，备份的文件是dev/sdb1这个里面的内容。

xfsdump –f /iop/dump_sdb1  /dev/sdb1 –L dump_sdb1 –M dump_sdb1   #指定一个地方，不在进行交户。
–L dump_sdb1：备份的是什么东西，就是告诉自己备份的是什么文件
–M dump_sdb1：备份的是什么，就是告诉自己是什么设备
[root@qtxsm ~]# xfsdump –I  #备份的是什么内容列表。
文件的恢复：
xfsrestore –f 指定恢复文件的位置   指定存放恢复后的文件的路径

xfsrestore  –f /iop/dump_sdb1 –s 路径目录下 里面的内容 恢复后的文件路径 （恢复的是目录，写的是相对路径，-s就是文件目录）
xfsrestore  –f /iop/dump_sdb1 –t  #查看备份文件里面的内容（-t就是查看备份的文件中的文件）


六、查看某个命令是那个软件包安装的命令
1、比方是有一个软件命令是哪个软件包安装的，就用rpm  -qf 来查询
[root@qtxsm~]# rpm –qf /usr/bin/vi
或者
[root@qtxsm~]# rpm –qf `which vi`   #其中将which vi 包起来的是数字键的反引号
或者
[root@qtxsm~]# rpm –qf $(which vi)   #这样也是可以查看出来的

2、vim 编辑器的几种模式
正常模式：
命令行模式：
插入模式：
可视模式：
  
  
  
  
  
  
