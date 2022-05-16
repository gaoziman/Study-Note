命令格式： 命令  [选项]  [参数]

ls -a  -l  -lh  -ld

# Linux操作系统

#### 快捷键

```bash
# ctrl shift +
# ctrl -
# ctrl shift c
# ctrl shift v
# ctrl l / clear
# ctrl shift t
# alt 1
# ctrl alt ←
# ctrl c
# ctrl d
# ctrl z


ctrl w 删除前面单词
ctrl d 删除后面字母

# ctrl alt f1    	//切换图形化
# ctrl alt f2-f6	 //切换字符

```

#### su,su -

```bash
# [centos@localhost ~]$ su user1
Password: 
[user1@localhost centos]$

# [centos@localhost ~]$ su - user1
Password: 
Last login: Tue Sep 14 00:51:14 PDT 2021 on pts/0
[user1@localhost ~]$ 

```

#### 前导符

```bash
[root@loaclhost~] #
root：用户名
@：间隔符
loaclhost：主机名
~：表示当前工作目录，~表示家目录
#：当前用户身份，#代表管理员，$代表普通用户
```

#### tab

命令补全，常用tab键，如果按一次出不来就按两次，此时表示命令不唯一，如果超过两次还没有出来就表示命令错误。

#### man

man + 命令   ----- man ls

#### history

```
# history
!num ----  !60
!cmd ----  !rm
```

#### alias

```bash
[root@localhost ~]# alias wk='pwd'

[root@localhost ~]# alias 
alias cp='cp -i'
alias egrep='egrep --color=auto'
alias fgrep='fgrep --color=auto'
alias grep='grep --color=auto'
alias l.='ls -d .* --color=auto'
alias ll='ls -l --color=auto'
alias ls='ls --color=auto'
alias mv='mv -i'
alias rm='rm -i'
alias which='alias | /usr/bin/which --tty-only --read-alias --show-dot --show-tilde'
alias wk='pwd'

[root@localhost ~]# wk
/root

[root@localhost ~]# pwd
/root
```

作业：将自己名字（全称拼音）设置成history，并查看

#### 基本命令

##### ls

```bash
Linux下一切皆文件

命令格式：
	ls
# ls //显示当前路径下的文件

命令格式：
	ls [OPTION]
	
# ls -a   //显示所有文件（包含以.或..开头的隐藏文件）
# ls --all
# ls -l  //长格式显示文件信息
-rw-------. 1 root root 2770 Sep  7 01:36 anaconda-ks.cfg
文件类型：
	-：普通文件（黑色）
	d：目录/文件夹（蓝色）
	l：链接文件（天蓝色）
rw-------:文件权限
1：节点数
root：用户名
root：组名
2770：文件大小
Sep  7 01:36：最后一次修改时间
anaconda-ks.cfg：文件夹

# ls -lh 人性化显示文件大小，必须配合-l使用
# ls -ld 显示自身属性，必须配合-l使用


命令格式：
	ls [选项]... [FILE] 
	
查看文件和文件夹的长格式信息（文件夹的长格式信息要多加一个d）
[root@localhost ~]# ls -l anaconda-ks.cfg 
-rw-------. 1 root root 2770 Sep  7 01:36 anaconda-ks.cfg
[root@localhost ~]# ls -l Documents 
total 0
[root@localhost ~]# ls -ld Documents 
drwxr-xr-x. 2 root root 6 Sep 14 22:32 Documents

# pwd（print working directory）   打印当前工作目录
```

##### 绝对、相对路径

```
绝对：从/开始，具有唯一性
	湖北省武汉市洪山区光谷广场
相对：从半路开始
	洪山区光谷广场
```

##### cd 更改目录

```bash
 cd  （change directory）

# cd /etc/sysconfig/network-scripts/
# cd ..  返回上一层目录

# cd /tmp
# cd /var
# cd /etc
# cd - 返回上一次进入的目录（相当于遥控器的返回键）
1    115     117
/tmp  /var   /etc   cd

# cd 返回到家目录
```

##### cat、more、less  查看文件内容

```bash
cat 只适合查看短文件
命令格式：cat [选项] 文件名
# cat /etc/passwd

命令格式：more 文件名
more 只能下翻，不能上翻
# more /etc/passwd

命令格式：less 文件名
less 既可上翻，又可下翻
# less /etc/passwd
```

##### head、tail 查看文件内容

```bash
命令格式：head [选项] 文件名
# head /etc/passwd
	# head  -n 3/etc/passwd
	
命令格式：tail [选项] 文件名
# tail /etc/passwd
 	# tail -n /etc/passwd
```

##### touch：1.创建文件；2.刷新时间戳

```bash
命令格式：touch 文件名
[root@localhost ~]# touch 1.txt
[root@localhost ~]# ls -l 1.txt 
-rw-r--r--. 1 root root 0 Sep 15 01:37 1.txt

[root@localhost ~]# touch 1.txt
[root@localhost ~]# ls -l 1.txt 
-rw-r--r--. 1 root root 0 Sep 15 01:39 1.txt
```

##### mkdir:创建文件夹

**（建议创建在/下面）**

```bash
命令格式： mkdir  [选项] 目录名
# mkdir /test2
# mkdir /test2/test20
# ls -ld /test2/test20/

# mkdir /test3/test30    || no
# echo $?
# mkdir -p /test3/test30  || yes
```

##### rmdir：删除空文件夹

```bash
命令格式：mkdir 文件名
[root@localhost /]# ls /test2/test20/
[root@localhost /]# ls /test3/test30/
[root@localhost /]# ls /test40/
[root@localhost /]# rmdir /test2
rmdir: failed to remove ‘/test2’: Directory not empty
[root@localhost /]# rmdir /test2/test20/
[root@localhost /]# rmdir /test40
```

##### rm

-r 递归

-f 强制

```bash
命令格式：rm [选项] 文件名
[root@localhost ~]# ls /test3/test30
[root@localhost ~]# rm /test3
rm: cannot remove ‘/test3’: Is a directory
[root@localhost ~]# rm -f /test3
rm: cannot remove ‘/test3’: Is a directory
[root@localhost ~]# rm -r /test3
rm: descend into directory ‘/test3’? y
rm: remove directory ‘/test3/test30’? y
rm: remove directory ‘/test3’? ^C
[root@localhost ~]# rm -rf /test3/
[root@localhost ~]# echo $?
0
```

##### date

```
[root@localhost ~]# date
Wed Sep 15 01:40:00 PDT 2021

date  月日时分年点秒
[root@localhost ~]# date 091516412021.50
Wed Sep 15 16:41:50 PDT 2021
[root@localhost ~]# date
Wed Sep 15 16:41:55 PDT 2021
```

##### dd

案例1：cpu爆满

```bash
[root@localhost ~]# dd if=/dev/zero of=/dev/null
```

```bash
[root@localhost ~]# top
```

案例2：制作指定大小的文件

```bash
[root@localhost ~]# dd if=/dev/zero  of=4M bs=2M count=2
```

6M(bs大小)　　８M（数量）　１0M 

```bash
[root@localhost ~]# dd if=/dev/zero  of=6M bs=6M count=1

[root@localhost ~]# dd if=/dev/zero  of=8M bs=4M count=2

[root@localhost ~]# dd if=/dev/zero  of=10M bs=5M count=2
```

##### echo回显

```bash
[root@localhost ~]# echo "123"
123
[root@localhost ~]# echo "456"
456
[root@localhost ~]# echo 456
```

##### cp （copy）复制

默认复制文件

```bash
命令格式：
	cp [选项] 源文件  目标文件
[root@localhost ~]# cp 2M /tmp/	
	
[root@localhost ~]# cp test1 /mnt/
cp: omitting directory ‘test1’
[root@localhost ~]# 
[root@localhost ~]# cp -r test1 /mnt/

[root@localhost ~]# echo "123456" > 1.txt
[root@localhost ~]# echo "456" > 2.txt
[root@localhost ~]# cat 2.txt 
456
[root@localhost ~]# cp 1.txt 2.txt
cp: overwrite ‘2.txt’? y
[root@localhost ~]# cat 2.txt 
```

##### mv（remove）

```bash
命令格式：
	mv 源文件  目标文件
[root@localhost ~]# mv 2M /mnt
[root@localhost ~]# ls
1.txt            Desktop    original-ks.cfg  test1
2.txt            Documents  Pictures         Videos
4M               Downloads  Public
anaconda-ks.cfg  Music      Templates

[root@localhost ~]# ls
1.txt            Desktop    original-ks.cfg  test1
2.txt            Documents  Pictures         Videos
4M               Downloads  Public
anaconda-ks.cfg  Music      Templates
[root@localhost ~]# mv 4M /mnt/10M
```

##### 破解密码

```bash
1.重启虚拟机
2.按↑↓键暂停到启动界面吗，按e进入启动程序
3.找到linux16，并按end跳到行尾，添加rd.break
4.按ctrl x进入系统
5.mount -o remount,rw /sysroot    //以读写方式重新挂载系统
6.chroot /sysroot				  //切换到/sysroot
7.echo "123456" | passwd --stdin root   //设置root的密码为123456
8.touch /.autorelabel             //给selinux打上下文关系标签
9.exit							  //退出
10.reboot						  //重启
```

|（管道符）：将左边的执行结果传到右边

##### wc统计

```bash
命令格式：wc [选项] 文件名
	-l 统计行数
	-c 统计字符数
	-w 统计单词
```

##### grep：过滤

```bash
命令格式：grep 关键字  文件名
[root@localhost ~]# grep root /etc/passwd
root:x:0:0:root:/root:/bin/bash
operator:x:11:0:operator:/root:/sbin/nologin

[root@localhost ~]# grep ^root /etc/passwd
root:x:0:0:root:/root:/bin/bash

[root@localhost ~]# grep bash$ /etc/passwd
root:x:0:0:root:/root:/bin/bash
centos:x:1000:1000:Centos7:/home/centos:/bin/bash
```

```bash
1.	vim 1.txt
2.	i
3.	输入内容
4.	esc
5.	：wq

原文件：
[root@localhost ~]# cat 1.txt 
123  we r tt uy u
root

#root
ROOT
-----------------------------------------------------
-i 忽略大小写
[root@localhost ~]# grep root 1.txt 
root
#root
[root@localhost ~]# grep -i root 1.txt 
root
#root
ROOT
-----------------------------------------------------
-v 取反
[root@localhost ~]# grep -v root 1.txt 
123  we r tt uy u

ROOT
-----------------------------------------------------
^$ 过滤空行
[root@localhost ~]# grep ^$ 1.txt 

-----------------------------------------------------
[root@localhost ~]# grep -v ^$ 1.txt 
123  we r tt uy u
root
#root
ROOT
----------------------------------------------------
[root@localhost ~]# grep -v "^$|^#" 1.txt 
123  we r tt uy u
root

#root
ROOT
[root@localhost ~]# grep -Ev "^$|^#" 1.txt 
123  we r tt uy u
root
ROOT
1.关键字
2.^关键字
3.关键字$
4.-i
5.-v
6.^$  -v
```

作业：

```bash
	1.统计root家目录下有多少文件
	[root@localhost ~]# ls | wc -l
	11
	
​   2.统计anaconda-ks.cfg文件有多少单词和字符
	[root@localhost ~]# wc -w anaconda-ks.cfg 
	283 anaconda-ks.cfg
	[root@localhost ~]# wc -c anaconda-ks.cfg 
	2770 anaconda-ks.cfg

​   3.过滤出/etc/shadow文件下带centos的行
	[root@localhost ~]# grep centos /etc/shadow
	centos:$1$c1ZA1AN5$lMitJP.Gyltx2Vo8on8NP0:18877:0:99999:7:::

​	4.过滤出/etc/shadow文件下以centos开头的行
	[root@localhost ~]# grep ^centos /etc/shadow
	centos:$1$c1ZA1AN5$lMitJP.Gyltx2Vo8on8NP0:18877:0:99999:7:::
```

#### 基本命令作业

```bash
1.将环境的主机名改为你的姓名，如wangke
2.进入/tmp目录并显示当前工作目录
3.查看/etc/group文件的前3行和后5行
4.在/root下创建10.txt和100.txt，并用长格式显示文件信息
5.修改系统时间，与windows时间保持一致
6.创建文件夹qwer，并在qwer下创建qaz的文件夹
7.在/qwer/qaz下面创建xinchuang20303-4的文件
8.删除qwer目录
9.创建wangke文件夹，并删除
10.将/root下的10.txt复制到/tmp下
11.将/root下的100.txt3到/mnt下并重命名为200.txt
12.过滤出/etc/login.defs的空行和注释行
13.破解密码，将系统密码改为qwer，（把输入的命令截图）
```

参考答案

```bash
# cd
# head -n 3 /etc/group
# tail -n 5 /etc/group
# pwd
# touch {10,100}.txt
# ls
# ls -l 10.txt
# ls -l 100.txt
# date
# date 100613532021.45
# date
# mkdir /qwer/qaz
# mkdir -p /qwer/qaz
# touch /qwer/qaz/xinchuang20303-4
# cd /qwer/qaz/
# ls
# rm -rf /qwer/
# cd
# mkdir /wangke
# rmdir /wangke/
# ls
# ls | grep 10/txt
# ls | grep 10.txt
# cp 10.txt /tmp/
# cd /tmp/
# ls | grep 10.txt
# cd
# mv /root/100.txt /mnt/200.txt
# pwd
# ls | grep 100.txt
# cd /mnt/
# ls | grep 200.txt
# cd
# grep "^$|^#" /etc/login.defs
# grep -E "^$|^#" /etc/login.defs
# grep -E -v "^$|^#" /etc/login.defs
# history -a
```

##### 通配符

*:匹配一个或多个任意字符

```bash
[root@wangke mnt]# ls
1.txt   a.txt  b.txt
ab.txt  A.txt  B.txt
[root@wangke mnt]# ls *.txt
1.txt   a.txt  b.txt
ab.txt  A.txt  B.txt
```

?:匹配单个字符

```bash
[root@wangke mnt]# ls ?.txt
1.txt  A.txt  B.txt
a.txt  b.txt
[root@wangke mnt]# ls ??.txt
ab.txt
```

[]：匹配[]内的任意单个字符

```
[root@wangke mnt]# ls [abc].txt
a.txt  b.txt
```

[^]、[!]:不匹配[]的任意单个字符

```bash
[root@wangke mnt]# ls
1.txt   a.txt  b.txt
ab.txt  A.txt  B.txt
[root@wangke mnt]# ls [ac].txta.txt
[root@wangke mnt]# ls [!ac].txt
1.txt  A.txt  b.txt  B.txt
[root@wangke mnt]# ls [^ac].txt
1.txt  A.txt  b.txt  B.txt
```

{}

```bash
{a..f}:a到f
[root@wangke mnt]# touch {a..f}.txt
[root@wangke mnt]# ls
a.txt  b.txt  c.txt  d.txt  e.txt  f.txt

{A,C}:A和C
[root@wangke mnt]# touch {A,C}.txt
[root@wangke mnt]# ls
a.txt  b.txt  C.txt  e.txt
A.txt  c.txt  d.txt  f.txt
```

#### vim:创建、查看、编辑文件

##### vi和vim的区别

```bash
vim的vi的升级版
vim有高亮显示
```

##### vim的三种模式

```bash
命令模式：直接用vim打开文件就是命令模式，标识符：1.光标闪动，2.左下角有文件名、行数、字符数
输入模式：按aio任意字符即可进入输入模式，标识符：输入/中，insert/英文
末行模式：最后一行输入保存退出内容，标识符：”：（冒号）“
```

##### 三种模式的切换

```bash
命令模式 aio ---->输入模式
		<-----Esc
		
命令模式  ：------>末行模式
		<------Esc
```

##### aio

```
命令模式
	a：光标所在字符后面输入
	A：光标所在行行尾输入
	I：光标所在行行首输入
	i：光标所在字符前面输入
	o：光标所在行下一行输入
	O：光标所在行上一行输入
```

##### 保存、退出

```bash
末行模式
	w（保存）
	q（退出）
	wq/x（保存退出）
	！表示强制
命令模式
	ZZ（大写）（保存退出）
```

##### 光标的移动

```bash
# vim /etc/passwd
命令模式
	h：左
	j：下
	k：上
	l：右
上下左右方向键
```

##### 行内跳转

```bash
命令模式
	^/home：到行首
	$/end：到行尾
	w：单词跳转
```

##### 行间跳转

```bash
命令模式	
	gg：跳转到首行
	G：跳转到尾行
	3gg：跳转到第3行
末行模式
	:20：跳转到到第20行
	:%：跳转到最后一行
```

##### 页面跳转

```
pageup：向上翻页
pagedown：向下翻页
```

##### 复制

```
命令模式
	yy：复制光标所在行
	2yy：复制光标所在的2行，包含光标所在行
	yw：复制单词
末行模式
	:3,6y：复制3到6行
	:%：复制全文
	:7y：复制第7行
```

##### 粘贴

```
命令模式
	p（小写）：光标下一行粘贴
	P（大写）：粘贴到光标上一行
```



##### apache网站

```bash
[root@localhost ~]# vim /etc/sysconfig/network-scripts/ifcfg-ens32
:set nu
G
ww
dw
a
将ONBOOT=NO改为ONBOOT=yes

[root@localhost ~]# systemctl restart network


1.ping通百度
2.安装软件
	[root@localhost ~]# yum repolist 
	[root@localhost ~]# yum install -y httpd
3.关闭防火墙
	[root@localhost ~]# systemctl stop firewalld.service 
4.关闭selinux
	[root@localhost ~]# setenforce 0
5.开启服务
[root@localhost ~]# systemctl restart httpd

6.自定义网站
[root@localhost ~]# echo 123456 > /var/www/html/index.html

```

##### 删除

```
命令模式
dd：删除光标所在行
dw：删除单词
5dd：删除5行（包含光标所在行）
x/del：删除光标所在字符
D：删除光标所在行后半部分的字符（包含光标所在字符）
dgg：删除光标之前的所有行
dG：删除光标之后的所有行

末行模式：
：4d：删除第4行
：1,9d：删除1到9行
：%d：删除全文
```

##### 撤回

```
命令模式
u：一步步撤回
```

##### 查找

```
命令模式
/root:查找root
	n：往下查找
	N：往上查找
？root:
	n：往上查找
	N：往下查找
```

##### 行号

```
末行模式
：set nu
：set nonu
：noh：取消高亮
```

##### 替换

```
末行模式
：s/root/qq   将光标所在行的第一个root替换为qq
：s/root/qq/g 将光标所在行的所有root都替换为qq
：1,3s/root/qq/g 将1到3行的所有root都替换为qq
：%s/root/qq/g
```

##### 批量注释

```
1.Ctrl v  进入可视化块模式
2.选中你要注释的行
3.按I（大写）
4.按#
5.esc（两下）
```

##### 取消批量注释

```
1.ctrl v
2.选中你要取消注释的行
3.按d
```

##### 读入、写入

```bash
末行模式
:r /etc/hosts   将/etc/hosts文件的内容读入当前文件里面光标所在行下一行

：w /tmp/2.txt  将此文件内容另存为到/tmp/2.txt文件里面
```

##### vim练习

```
1.创建1.txt并在里面写上两行内容（自定义）
2.将/etc/hosts文件内容读入此文件
3.将此文件另存为到/mnt/qq.txt
```

##### 自动设置行号

```
1.vim /etc/vimrc
2.G 
3.o
添加set number
```

#### 管理本地用户和组

```
1.用户分类
	root：0
	普通用户
		RHEL6:500
		RHEL7:1000
	系统用户（程序用户）
```

```
1.UID1000
2。home
shell
```

##### useradd:创建用户

```
root:x:0:0:root:/root:/bin/bash
root：用户名
x：密码占位符
0：uid
0：gid
root：描述信息
/root：家目录
/bin/bash：登录shell（/bin/bash允许用户登录，/sbin/nolgin不允许用户登录）
```

```bash
命令格式：
useradd [选项] 用户名
[root@localhost ~]# useradd user1
[root@localhost ~]# tail -n 1 /etc/passwd
user1:x:1001:1001::/home/user1:/bin/bash
user2:x:1002:1002::/home/user2:/bin/bash

-u 指定uid
localhost ~]# useradd -u 1010 user3
user3:x:1010:1010::/home/user3:/bin/bash

-d 指定家目录
[root@localhost ~]# useradd -d /home/qq user4
[root@localhost ~]# tail -n 3 /etc/
user2:x:1002:1002::/home/user2:/bin/bash
user3:x:1010:1010::/home/user3:/bin/bash
user4:x:1011:1011::/home/qq:/bin/bash

-s 指定登录shell
[root@localhost ~]# useradd -s /sbin/nologin user5
[root@localhost ~]# tail  -n 1 /etc/passwd
user5:x:1012:1012::/home/user5:/sbin/nologin

验证：
[root@localhost ~]# su - user5
This account is currently not available.

-c 指定描述信息
[root@localhost ~]# useradd -c testuser user6
[root@localhost ~]# tail  -n 1 /etc/passwd
user6:x:1013:1013:testuser:/home/user6:/bin/bash


-g 将用户加入到主组（1个）
id 查看用户信息

[root@localhost ~]# groupadd group1
[root@localhost ~]# groupadd group2
[root@localhost ~]# useradd -g group1 user7
[root@localhost ~]# id user7
uid=1014(user7) gid=1014(group1) 组=1014(group1)
[root@localhost ~]# id user6
uid=1013(user6) gid=1013(user6) 组=1013(user6)
[root@localhost ~]# 

-G 将用户加入到附加组
[root@localhost ~]# useradd -G group2  user8
[root@localhost ~]# id user8
uid=1015(user8) gid=1016(user8) 组=1016(user8),1015(group2)

useradd里面的-u是指定uid，-g将用户加入到主组，-G将用户加入到附加
groupadd里面的-g才是指定gid

```

##### 练习题目

```bash
创建组sysadm
创建用户harry，natasha，tom
	要求harry，natasha的附加组为sysadm
	要求tom用户的登陆shell为非交互式shell
	三个用户的密码为redhat
	
	
创建用户user100
	1.描述信息为ptyh
	2.家目录为/home/wx
	3.uid为6666
	4.登录shell为/sbin/nologin
	
[root@localhost ~]# useradd -c ptyh -d /home/wx -u 6666 -s /sbin/nologin user100
[root@localhost ~]# tail -n 1 /etc/passwd
user100:x:6666:6666:ptyh:/home/wx:/sbin/nologin
```

##### usermod：修改用户

```bash
[root@localhost ~]# usermod -c testc -u 1515 -d /qwer c
[root@localhost ~]# tail -n 1 /etc/passwd
c:x:1515:1000:testc:/qwer:/bin/bash
[root@localhost ~]# id c
uid=1515(c) gid=1000(c) 组=1000(c),10(wheel)
[root@localhost ~]# groupadd group1
[root@localhost ~]# groupadd group2
[root@localhost ~]# usermod -g group1 -G group2 c
[root@localhost ~]# id c
uid=1515(c) gid=1001(group1) 组=1001(group1),1002(group2)
[root@localhost ~]# 

-u
-c
-g
-G
-s
-d

useradd user1
echo “123” | passwd --stdin user1

-L：锁定
[root@localhost ~]# usermod  -L user1
[root@localhost ~]#

-U：解锁
[root@localhost ~]# usermod  -U user1
解锁之后可以登录
[root@localhost ~]# su - c
su: 警告：无法更改到 /qwer 目录: 没有那个文件或目录
[c@localhost root]$ su - user1
密码：
[user1@localhost ~]$
```

##### userdel：删除用户

```
-r 递归删除（从用户邮箱删除）
练习：
	1.创建user2
	2.分别检查3个文件中是否有user1和user2  （/etc/passwd  /etc/shadow  /etc/group   cd /var/spool/mail ----- ls）
	3.userdel  user1  -----重复第2步  ----- 只能从3个文件中将用户删除，并不能删除邮箱（路径）---rmdir（空）---rm -rf 文件和目录
	4.userdel -r user2 ----重复第2步  -----删除更加干净
```

##### groupadd：创建组

```bash
-g 指定gid
[root@localhost ~]# groupadd -g 6666 group4
[root@localhost ~]# tail -n 3 /etc/group
group2:x:1002:c
group3:x:1003:
group4:x:6666:
```

##### groupmod：修改组

```bash
-g 修改gid
[root@localhost ~] # groupmod -g 7777 group4
[root@localhost ~]# tail -n 3 /etc/group
group2:x:1002:c
group3:x:1003:
group4:x:7777:

-n 修改组名
[root@localhost ~]# groupmod  -n testgroup4 group4
[root@localhost ~]# tail -n 3 /etc/group
group2:x:1002:c
group3:x:1003:
testgroup4:x:7777:
```

##### groupdel：删除组

```bash
[root@localhost ~]# groupdel testgroup4 
```

##### 补充：将用户加入到组

```bash
1.创建用户的时候将用户加入到组
[root@localhost ~]# groupadd group10
[root@localhost ~]# groupadd group20
[root@localhost ~]# groupadd group30
[root@localhost ~]# useradd -g group10 user10
[root@localhost ~]# usermod -g group20 user10

2.修改用户的组

3.直接将已存在的用户加入到组
[root@localhost ~]# gpasswd -a user10 group10
正在将用户“user10”加入到“group10”组中
[root@localhost ~]# tail -n 5 /etc/group
group2:x:1002:c
group3:x:1003:
group10:x:1004:user10
group20:x:1005:
group30:x:1006:

[root@localhost ~]# gpasswd -d user10 group10
正在将用户“user10”从“group10”组中删除
^[[A[root@localhost tail -n 5 /etc/groupup10
group2:x:1002:c
group3:x:1003:
group10:x:1004:
group20:x:1005:
group30:x:1006:
[root@localhost ~]# 
```

#### Openssh

```
查看信息
1.查看地址
	ip a = ip address show 
	ifconfig
2.查看网关
	ip r = ip route
```

##### 思路

```bash
[root@localhost ~]# vim /etc/sysconfig/network-scripts/ifcfg-ens33 
1.将ONBOOT修改为yes
2.启用windows上面的vmnet8网卡
3.windows和Linux做互通
4.远程到Linux
	ssh root@192.168.184.128  
```

#### 文件权限

```
[root@localhost ~]# ls -l anaconda-ks.cfg 
-rw-------. 1 root root 1225 11月 18 2020 anaconda-ks.cfg

权限：
rw-------：一共9个字符，分3段
第一段（前3个字符）：拥有人、所属者：user：u
第二段（中间3个字符）：拥有组、所属组：group：g
第三段（后3个字符）：其他人：other：o

r：read：读权限：4
w：write：写权限:2
x：execute：执行权限:1
-：无权限
所属关系
root：拥有人、所属者
root：拥有组、所属组
```

| 权限      | 对文件的影响         | 对目录的影响                                         |
| --------- | -------------------- | ---------------------------------------------------- |
| r  （读） | 可以读取文件的内容   | 可以列出目录的内容（文件名）  （列出目录下的文件名） |
| w（写）   | 可以更改文件的内容   | 可以创建或删除目录中的任一文件                       |
| x（执行） | 可以作为命令执行文件 | 可以访问目录的内容      （点进目录下目录）           |

##### 修改普通权限

```bash
rw-------：chmod---修改权限
root root：chown---修改所属

修改权限的两种方式
	1.用字符修改
		命令格式：chmod ugoa +-= rwx filename
		原：rw-------
		现：rwxrw-rw-
		chmod u+x，g=rw，o+rw anac
		
		练习：
		原：rwx   rw-   rw-
		现：rwx   r--   ---
		[root@localhost ~]# chmod g-w,o=- anaconda-ks.cfg 
		[root@localhost ~]# ls -l anaconda-ks.cfg 
		-rwxr-----. 1 root root 1225 11月 18 2020 anaconda-ks.cfg

		原：rwx   r--   ---		
		现：r--   r--   r--
        [root@localhost ~]# chmod a=r anaconda-ks.cfg 
		[root@localhost ~]# ls -l anaconda-ks.cfg 
		-r--r--r--. 1 root root 1225 11月 18 2020 anaconda-ks.cfg

	2.用数字修改
		命令格式：chmod nnn filename
		原：r--   r--   r--
		现：rwx   rw-   rw-
			7    6     6
		[root@localhost ~]# chmod 766 anaconda-ks.cfg 
		[root@localhost ~]# ls -l anaconda-ks.cfg 
		-rwxrw-rw-. 1 root root 1225 11月 18 2020 anaconda-ks.cfg

		原：rwx   rw-   rw-
		现：rw-   rw-   rw-
		chmod u-x  anac
		chmod 666  anac
```

##### 修改所属关系

```bash
root root：chown---修改所属
命令格式：chown user|（.|:）group filename
修改用户命令格式：chown user filename 
修改组令格式：chown 【.|:】group filename 

修改所属者
[root@localhost ~]# ls -l anaconda-ks.cfg 
-rwxrw-rw-. 1 root root 1225 11月 18 2020 anaconda-ks.cfg
[root@localhost ~]# ls -l anaconda-ks.cfg 
-rwxrw-rw-. 1 user4 root 1225 11月 18 2020 anaconda-ks.cfg

用.修改所属组
[root@localhost ~]# chown .c anaconda-ks.cfg 
[root@localhost ~]# ls -l anaconda-ks.cfg 
-rwxrw-rw-. 1 user4 c 1225 11月 18 2020 anaconda-ks.

用：修改所属组
cfg[root@localhost ~]# chown :root anaconda-ks.cfg 
[root@localhost ~]# ls -l anaconda-ks.cfg 
-rwxrw-rw-. 1 user4 root 1225 11月 18 2020 anaconda-ks.cfg


[root@localhost ~]# chown user10:user10 anaconda-ks.cfg 
[root@localhost ~]# ls -l anaconda-ks.cfg 
-rwxrw-rw-. 1 user10 user10 1225 11月 18 2020 anaconda-ks.cfg
[root@localhost ~]# 


练习：
1.创建用户user10和user20
	useradd user10
	useradd user20
2.创建文件1.txt，2.txt
	touch {1,2}.txt
3.将1.txt和2.txt的所属者改为c
	chown c 1.txt
	chown c 2.txt
4.将1.txt所属组改为user10 (要求用.修改)
	chown .user10 1.txt
5.将2.txt所属组改为user20 (要求用：修改)
	chown :user20 2.txt
	
更改目录所属关系：
	[root@localhost ~]# ls -ld /test1
	drwxr-xr-x. 2 root root 6 11月  3 04:10 /test1
	[root@localhost ~]# touch /test1/test.txt
	[root@localhost ~]# ls -ld /test1/test.txt 
	-rw-rw-r--. 1 root root 0 11月  3 04:16 /test1/test.txt
	
	[root@localhost ~]# chown c:user10 /test1
	[root@localhost ~]# ls -ld /test1
	drwxr-xr-x. 2 c user10 22 11月  3 04:16 /test1
	[root@localhost ~]# ls -ld /test1/test.txt 
	-rw-rw-r--. 1 root root 0 11月  3 04:16 /test1/test.txt
	
	-R 递归
	[root@localhost ~]# chown -R user10:c /test1/
	[root@localhost ~]# ls -ld /test1
	drwxr-xr-x. 2 user10 c 22 11月  3 04:16 /test1
	[root@localhost ~]# ls -ld /test1/test.txt 
	-rw-rw-r--. 1 user10 c 0 11月  3 04:16 /test1/test.txt

```

##### 默认权限

```bash
文件夹：755=777-022
文件：644=666-022
[root@localhost ~]# umask 
0022
[root@localhost ~]# umask 0002
[root@localhost ~]# touch 2.txt
[root@localhost ~]# ls -l 2.txt 
-rw-rw-r--. 1 root root 0 11月  3 04:13 2.txt
[root@localhost ~]# mkdir /test2
[root@localhost ~]# ls -ld /test2
drwxrwxr-x. 2 root root 6 11月  3 04:14 /test2

```

#### ACL权限

```bash
setfacl：
getfacl：

命令格式
	setfacl [选项] user：username：rwx |group:groupname:rwx  filename
    
file:xinchuang20303-4
user：banzhang（rwx），tuanzhishu（rw），xuexiweiyuan（rw）
group：diyizu（rwx），dierzu（rw），disanzu（r）

[root@localhost ~]# touch xinchuang20303-4
[root@localhost ~]# useradd banzhang
[root@localhost ~]# useradd tuanzhishu
[root@localhost ~]# useradd xuexiweiyuan
[root@localhost ~]# groupadd diyizu
[root@localhost ~]# groupadd dierzu
[root@localhost ~]# groupadd disanzu

[root@localhost ~]# 
[root@localhost ~]# setfacl -m u:banzhang:rwx,u:tuanzhishu:rw,
u:xuexiweiyuan:rw xinchuang20303-4 

[root@localhost ~]# setfacl -m g:diyizu:rwx,g:dierzu:rw,g:disa
nzu:r xinchuang20303-4 [root@localhost ~]# getfacl xinchuang20303-4 
# file: xinchuang20303-4
# owner: root
# group: root
user::rw-
user:banzhang:rwx
user:tuanzhishu:rw-
user:xuexiweiyuan:rw-
group::r--
group:diyizu:rwx
group:dierzu:rw-
group:disanzu:r--
mask::rwx
other::r--

-x 一步步移除
[root@localhost ~]# setfacl -x g:diyizu xinchuang20303-4
[root@localhost ~]# setfacl -x g:diyizu xinchuang20303-4 

[root@localhost ~]# getfacl xinchuang20303-4 
# file: xinchuang20303-4
# owner: root
# group: root
user::rw-
user:tuanzhishu:rw-
user:xuexiweiyuan:rw-
group::r--
group:dierzu:rw-
group:disanzu:r--
mask::rw-
other::r--

-b一次性移除
[root@localhost ~]# setfacl -b xinchuang20303-4 
[root@localhost ~]# getfacl xinchuang20303-4 
# file: xinchuang20303-4
# owner: root
# group: root
user::rw-
group::r--
other::r--
```

练习

```
1.创建文件1.txt
2.创建用户user1，user2
3.创建组group1、group2
4.给1.txt设置acl权限
	user1（rwx）
	user2（r）
	group1（rw）
	group2（r）
5.移除group2的权限
6.移除所有权限
```

##### 特殊权限

```
suid
	作用：文件的有效身份为文件的拥有者而非执行者
	u+s
	4
sgid
	作用：文件的有效身份为文件的拥有者而非执行者
		继承所属组
	g+s
	2
sticky（t位）
	
	o+t
	1
	
1.txt：默认文件权限：chmod 4644 1.txt
```

##### suid案例

作用：文件的有效身份为文件的拥有者而非执行者
	字符表示法：u+s
	数字表示法：4

```bash
1.用root身份：查看/etc/passwd的文件权限  ----644 
	[root@localhost ~]# ls -l /etc/passwd
	-rw-r--r--. 1 root root 2650 11月 10 00:46 /etc/passwd

2.用户c身份：cat /etc/passwd -----能看
	[root@localhost ~]# su - c
	[c@localhost ~]$ cat /etc/passwd
	root:x:0:0:root:/root:/bin/bash
	
3.用root身份：将查看/etc/passwd的文件权限修改为640
	[root@localhost ~]# chmod 640 /etc/passwd
	[root@localhost ~]# ls -l /etc/passwd
	-rw-r-----. 1 root root 2650 11月 10 00:46 /etc/passwd

4.用户c身份：cat /etc/passwd -----不能看
	[c@localhost ~]$ cat /etc/passwd
	cat: /etc/passwd: 权限不够

5.用root身份：查看cat的二进制文件路径
	[root@localhost ~]# which cat
	/usr/bin/cat
	
6.用root身份：查看/usr/bin/cat的文件权限
	[root@localhost ~]# ls -l /usr/bin/cat
	-rwxr-xr-x. 1 root root 51856 5月  11 2019 /usr/bin/cat
	
7.用root身份：将/usr/bin/cat的文件权限加晚上suid权限
	[root@localhost ~]# chmod 4755 /usr/bin/cat 
	[root@localhost ~]# ls -l /usr/bin/cat
	-rwsr-xr-x. 1 root root 51856 5月  11 2019 /usr/bin/cat

8.用户c身份：cat /etc/passwd -----能看（因为c在使用cat命令时调用了拥有人的权限）
	[c@localhost ~]$ cat /etc/passwd
	root:x:0:0:root:/root:/bin/bash

```

##### sgid案例

作用：

​	1.文件的有效身份为文件的拥有组而非执行组

​	2.继承权限

​	字符表示法：g+s
​	数字表示法：2

```bash
1.用root身份：查看/etc/passwd的文件权限  ----644 
	[root@localhost ~]# ls -l /etc/passwd
	-rw-r--r--. 1 root root 2650 11月 10 00:46 /etc/passwd

2.用户c身份：cat /etc/passwd -----能看
	[root@localhost ~]# su - c
	[c@localhost ~]$ cat /etc/passwd
	root:x:0:0:root:/root:/bin/bash
	
3.用root身份：将查看/etc/passwd的文件权限修改为640
	[root@localhost ~]# chmod 640 /etc/passwd
	[root@localhost ~]# ls -l /etc/passwd
	-rw-r-----. 1 root root 2650 11月 10 00:46 /etc/passwd

4.用户c身份：cat /etc/passwd -----不能看
	[c@localhost ~]$ cat /etc/passwd
	cat: /etc/passwd: 权限不够

5.用root身份：查看cat的二进制文件路径
	[root@localhost ~]# which cat
	/usr/bin/cat
	
6.用root身份：查看/usr/bin/cat的文件权限
	[root@localhost ~]# ls -l /usr/bin/cat
	-rwxr-xr-x. 1 root root 51856 5月  11 2019 /usr/bin/cat
	
7.用root身份：将/usr/bin/cat的文件权限加晚上suid权限
	[root@localhost ~]# chmod 2755 /usr/bin/cat 
	[root@localhost ~]# ls -l /usr/bin/cat
	-rwsr-xr-x. 1 root root 51856 5月  11 2019 /usr/bin/cat

8.用户c身份：cat /etc/passwd -----能看（因为c在使用cat命令时调用了拥有人的权限）
	[c@localhost ~]$ cat /etc/passwd
	root:x:0:0:root:/root:/bin/bash

```

案例2：继承权限

```bash
1.创建目录/test1
	[root@localhost ~]# mkdir /test1
	[root@localhost ~]# ls -ld /test1/
	drwxr-xr-x. 2 root root 6 11月 10 02:36 /test1/
2.在目录下创建1.txt
	[root@localhost ~]# touch /test1/1.txt

3.分别查看/test1和/test1/1.txt的权限和所属
	[root@localhost ~]# ls -ld /test1/
	drwxr-xr-x. 2 root root 6 11月 10 02:36 /test1/
	
	[root@localhost ~]# ls -l /test1/1.txt 
	-rw-r--r--. 1 root root 0 11月 10 02:37 /test1/1.txt

4.修改目录的sgid权限
	[root@localhost ~]# chmod g+s /test1/
	[root@localhost ~]# ls -ld /test1/
	drwxr-sr-x. 2 root root 19 11月 10 02:37 /test1/
	
5.修改目录的所属组为c
	[root@localhost ~]# chown c:c /test1/
	[root@localhost ~]# ls -ld /test1/
	drwxr-sr-x. 2 c c 19 11月 10 02:37 /test1/

6.分别查看/test1和/test1/1.txt所属关系
	[root@localhost ~]# ls -ld /test1/
	drwxr-sr-x. 2 c c 19 11月 10 02:37 /test1/
	[root@localhost ~]# ls -l /test1/1.txt 
	-rw-r--r--. 1 root root 0 11月 10 02:37 /test1/1.txt

7.在/test1/目录下创建新的文件
	[root@localhost ~]# touch /test1/2.txt
	
8.查看的新文件的所属关系--------已经继承
	[root@localhost ~]# ls -l /test1/2.txt 
	-rw-r--r--. 1 root c 0 11月 10 02:42 /test1/2.txt
```

##### sticky（t位）案例

作用：自己只能删除自己上传的文件，不能删除别人的文件

​	字符表示方式：o+t

​	数字表示方法：1

```bash
1.用root身份：创建用户b
	[root@localhost ~]# useradd b
	
2.用b身份：在/tmp下创建b.txt
	[root@localhost ~]# su - b
	[b@localhost ~]$ touch /tmp/b.txt
	
3.用c身份：在/tmp下创建c.txt
	[c@localhost ~]$ touch /tmp/c.txt

4.分成查看b.txt和c.txt所属关系是谁
	[b@localhost tmp]$ ls -ld c.txt 
	-rw-rw-r--. 1 c c 0 11月 10 03:20 c.txt
	[b@localhost tmp]$ ls -ld b.txt 
	-rw-rw-r--. 1 b b 0 11月 10 03:20 b.txt

5.用b身份删除c.txt文件
	[b@localhost tmp]$ rm -rf c.txt 
	rm: 无法删除'c.txt': 不允许的操作
	[b@localhost tmp]$ 
	
6.用c身份删除b.txt文件
	[c@localhost ~]$ cd /tmp/
	[c@localhost tmp]$ rm -rf b.txt 
	rm: 无法删除'b.txt': 不允许的操作
```

给目录设置t位

```bash
用数字法（建议）
[root@localhost ~]# chmod 1777 /test1/
[root@localhost ~]# ls -ld /test1/
drwxrwxrwt. 2 c c 32 11月 10 02:42 /test1/

用字符法
[root@localhost ~]# chmod o+t /test1
[root@localhost ~]# ls -ld /test1/
drwxrwxrwt. 2 c c 32 11月 10 02:42 /test1/
```

#### 进程

```bash
1.前后台任务调度
jobs：查看后台任务
 调入后台
	1.ctrl z (暂停）
	2.cmd & （运行）

 调入前台
 	fg %作业号  （作业号用jobs查看）
2.查看进程
	ps -aux
	
[root@localhost ~]# ps -aux | head
USER        PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND
root          1  0.1  0.5 244780  4164 ?        Ss   03:13   0:01 /usr/lib/systemd/systemd --switched-root 
root          2  0.0  0.0      0     0 ?        S    03:13   0:00 [kthreadd]

解释
USER：用户
PID：进程号
%CPU：cpu占用率
%MEM：mem占用率
VSZ：申请地址空间   
RSS：实际使用空间
TTY：终端，pts/0本地终端，pts/2远程终端
STAT：状态
START：时间
TIME：使用cpu时间
COMMAND：命令

3.杀死进程
	kill -9 %作业号
	kill -9  进程号
```

#### 网络管理

三种模式

```bash
1.仅主机模式(vmnet1)：只能和内网（vm开头）进行通信，不能上外网。外网：百度、淘宝、本地连接、WiFi
2.nat模式（vmnet8）：能够上外网，进行地址转换
2.桥接模式（vmnet0）：直接桥到本地连接

192.168.1.1/24  ---- ping 百度  （nat）  ----202.202.200.200
192.168.1.1/24  ---- ping 百度  （桥接） 
```

##### 网络分类

```bash
A类（掩码：8）
	地址范围：1-126
	第一位为网络位，后三位为主机位
	网段：网络位照抄，主机位归零
	eg：10.1.1.1/8  网段：10.0.0.0/8
B类（掩码：16）
	地址范围：128-191
	前两位为网络位，后两位为主机位
	网段：网络位照抄，主机位归零
	eg：191.10.1.1/16  网段：191.10.0.0/16
C类（掩码：24）
	地址范围：192-223
	前三位为网络位，后一位为主机位
	网段：网络位照抄，主机位归零
	eg：192.168.1.1/24  网段：192.168.1.0/24
D类
	用于科研
E类
	保留
```

##### 网络互通

```bash
1.查看IP
ip a = ip address show
ifconfig  （linux）/ipconfig（windows）

2.查看网关
	ip r = ip route
	
3.查看DNS
	[root@localhost ~]# cat /etc/resolv.conf
```

#####  配置ip

```bash
ip:192.168.1.10/24
网关：192.168.1.254
DNS：8.8.8.8

（一条命令）
[root@localhost ~]# 
	nmcli connection modify "ens33"   //连接修改ens33网卡
	ipv4.method  manual				  //手动配置ipv4
    ipv4.addresses "192.168.1.10/24"  //ipv4的地址、掩码
    ipv4.gateway "192.168.1.254" 	  //ipv4的网关
    ipv4.dns "8.8.8.8"				  //ipv4的DNS
    connection.autoconnect yes		  //使用时自动连接

样例
[root@localhost ~]# nmcli connection modify "ens33" ipv4.method  manual ipv4.addresses "192.168.1.10/24" ipv4.gateway "192.168.1.254" ipv4.dns "8.8.8.8" connection.autoconnect yes

[root@localhost ~]# nmcli connection down ens33   //关闭ens33网卡
[root@localhost ~]# nmcli connection up ens33 	  //开启ens33网卡
```

##### 仅主机模式

```
1.编辑----虚拟网络编辑器---仅主机----不勾dhcp
2.设置---网络适配器---仅主机模式
3.配置linux地址
	ip:192.168.1.10/24
	网关：192.168.1.254
	DNS：8.8.8.8
	
网段：192.168.1.0/24
4.配置windows中vmnet1的网卡ip
	ip:192.168.1.20/24
	网关：192.168.1.254
	DNS：192.168.1.10
	注意：windows和linux要保持同一网段，同一网关
5.测试互通
	windows ping linux
	linux ping windows
	
注意：如果单方面不通，95%是防火墙的原因，关闭防火墙即可。
```

##### 桥接模式

```bash
vmnet0---本地连接
1.编辑----虚拟网络编辑器---桥接模式----自动/指定具体网卡
2.设置---网络适配器---桥接模式
3.查看windows地址	
	ip:10.80.1.50/24
	网关：10.80.1.254
	DNS：8.8.8.8
	
网段：10.80.1.0/24
4.配置linux的地址
	ip:10.80.1.250/24
	网关：10.80.1.254
	DNS：8.8.8.8
[root@localhost ~]# nmcli connection modify "ens33" ipv4.method manual ipv4.addresses "10.80.1.250/24" ipv4.gateway "10.80.1.254" ipv4.dns "8.8.8.8" connection.autoconnect yes

检查：ip、掩码、网关、dns

5.测试互通
	windows ping linux
	linux ping windows
	ping dns
	ping baidu
```

##### nat模式

```bash
1.编辑----虚拟网络编辑器---nat模式
2.设置---网络适配器---nat模式
3.自动获取linux地址
	[root@localhost ~]# nmcli connection modify "ens33" ipv4.method auto connection.autoconnect yes
4.自动获取windows地址
5.互ping
6.ping 百度
```

#### 文件系统

分区、格式化、挂载

```bash
1.一块硬盘只能有4个主分区
如果你想分7个分区：
	1.分3个主分区
	2.分1个扩展分区（不能做格式化挂载）
	3.分3个逻辑分区
2.硬盘存放在/dev/目录下
	第一块硬盘：/dev/sda
		第一块硬盘的第一个分区：/dev/sda1
		第一块硬盘的第二个分区：/dev/sda2
	第二块硬盘：/dev/sdb
		第二块硬盘的第一个分区：/dev/sdb1
		第二块硬盘的第二个分区：/dev/sdb2
hd 表示IDE设备
sd 表示SCSI/SATA/PATA设备

SCSI:/dev/sda---/dev/sdzz
```

##### 分区

```bash
[root@localhost ~]# fdisk -l
命令(输入 m 获取帮助)：m

帮助：
  常规
   d   删除分区
   F   列出未分区的空闲区
   l   列出已知分区类型
   n   添加新分区
   p   打印分区表
   t   更改分区类型
  保存并退出
   w   将分区表写入磁盘并退出
   q   退出而不保存更改
   
[root@localhost ~]# fdisk /dev/sdb  
```

##### 格式化

```bash
[root@localhost ~]# mkfs.xfs /dev/sdb1
[root@localhost ~]# blkid  //查看格式化类型和UUID
```

##### 挂载

```bash
mkdir /mnt/dev
1.挂载文件系统
	mount /dev/sdb1 /mnt/dev
2.挂载UUID
	mount UUID="eeaefbac-354d-49a6-8ed3-c15c55b71f01" /mnt/dev
	
df -h查看挂载情况                
```

##### 取消挂载

```
1.取消文件系统
	[root@localhost ~]# umount /dev/sdb1
2.取消挂载点
	[root@localhost ~]# umount /mnt/dev
```

作业

```
1.添加一块40G硬盘
2.创建一个3G的主分区，分区号默认
3.创建一个5G的主分区
4.创建一个20G扩展分区
5.创建一个10G的逻辑分区
6.将2号分区类型更改为swap分区
7.将5号分区类型更改为LVM分区
8.格式化1号分区为xfs
9.创建挂载点/test1
10.用文件系统进行挂载
11.用文件系统进行卸载
12.用UUID挂载
13.用挂载点卸载
```

##### 模拟错误

```bash
1.先做永久挂载
vim /etc/fstab
/dev/sdb1               /mnt/dev                xfs     defaults        0 0

2.临时验证
mount -a 

3.模拟错误
vim /etc/fstab
/dev/sdb1               /mnt/dev                xfs     defaul        0 0

4.重启机器
reboot
```

##### swap：虚拟，交换分区

```bash
[root@localhost ~]# mkswap /dev/sdb2   //格式化swap分区

[root@localhost ~]# swapon  -a    //重新加载交换分区
[root@localhost ~]# swapon  -s    //查看swap分区的使用情况
文件名				类型		大小	已用	权限
/dev/dm-1                              	partition	2097148	562324	-2
/dev/sdb2                              	partition	5242876	0	-3

[root@localhost ~]#  swapon /dev/sdb2    //开启swap分区
[root@localhost ~]#  swapoff /dev/sdb2    //关闭swap分区
```

##### LVM

```bash
pvcreate /dev/sdc1
vgcreate  vg01 /dev/sdc1 
lvcreate -n lv01 -L +3G /dev/vg01
mkfs.ext4 /dev/vg01/lv01
mount /dev/vg01/lv01 /opt/
df -h
lvextend -L +2G /dev/mapper/vg01-lv01
df -h
//格式化类型为ext3、ext4等使用resize2fs刷新
resize2fs /dev/mapper/vg01-lv01   

//格式化类型为xfs等使用xfs_growfs刷新
xfs_growfs /dev/mapper/vg01-lv01   
df -h
```

#### RPM 

```bash
使用RPM进行软件包的安装，需要注意以下2两点
1.进入完整的包路径
2.安装时保证软件包名称完整

1.导入光盘并连接
2.挂载光盘(/dev/cdrom)
[root@localhost Packages]# mount /dev/cdrom /mnt

3.进入光盘路径
[root@localhost Packages]# cd /mnt/Packages
[root@localhost Packages]# ls

rpm -ivh
-i install  安装
-v verbose 详细信息
-h hash 显示带#的进度条

[root@localhost Packages]# rpm -ivh zsh-5.5.1-6.el8.x86_64.rpm 
警告：zsh-5.5.1-6.el8.x86_64.rpm: 头V3 RSA/SHA256 Signature, 密钥 ID 8483c65d: NOKEY
Verifying...                          ################################# [100%]
准备中...                          ################################# [100%]
正在升级/安装...
   1:zsh-5.5.1-6.el8                  ################################# [100%]


[root@localhost Packages]# ls | grep samba
--force --nodeps  强制安装
[root@localhost Packages]# rpm -ivh samba-4.9.1-8.el8.i686.rpm --force --nodeps
警告：samba-4.9.1-8.el8.i686.rpm: 头V3 RSA/SHA256 Signature, 密钥 ID 8483c65d: NOKEY
Verifying...                          ################################# [100%]
准备中...                          ################################# [100%]
正在升级/安装...
   1:samba-0:4.9.1-8.el8              ################################# [100%]
  
 
-q 查询软件包是否安装
[root@localhost Packages]# rpm -q samba
samba-4.9.1-8.el8.i686
[root@localhost Packages]# rpm -q httpd
未安装软件包 httpd 

-ql 查询软件包是相关文件
[root@localhost Packages]# rpm -ql samba

-qc 查询软件包的主配置文件
[root@localhost Packages]# rpm -qc samba 
/etc/openldap/schema/samba.schema
/etc/pam.d/samba

-qf 查询路径来自哪个软件包
[root@localhost Packages]# rpm -qf /etc/pam.d/samba
samba-4.9.1-8.el8.i686

-qa 查询已安装的软件
[root@localhost Packages]# rpm -qa | wc -l
1332

-i 详细信息
[root@localhost Packages]# rpm -qi samba

-e 卸载
[root@localhost Packages]# rpm -e samba
```

#### YUM

```bash
1.挂载光盘
//进入仓库路径
[root@localhost ~]# cd /etc/yum.repos.d/    
[root@localhost ~]# ls

//做备份
[root@localhost yum.repos.d]# #cp CentOS-Base.repo CentOS-Base.repo.bak
[root@localhost yum.repos.d]# cp CentOS-Base.repo{,.bak}

//编写yum仓库
[root@localhost yum.repos.d]# vim CentOS-Base.repo
	:set nu
	:1,12d
	:3d
	x
	ww
	D
	a
	添加file:///mnt
	
//更改之后的详见下文
```

##### 7版本仓库

```bash
[BaseOS]
name=CentOS-$releasever - Base
baseurl=file:///mnt
gpgcheck=0
enabled=1
```

##### 8版本仓库

```bash
  1 [BaseOS]
  2 name=CentOS-$releasever - Base
  3 baseurl=file:///mnt/BaseOS
  4 gpgcheck=0
  5 enabled=1
  6 
  7 [AppStream]
  8 name=CentOS-$releasever - AppStream
  9 baseurl=file:///mnt/AppStream
 10 gpgcheck=0
 11 enabled=1

```

##### 清理缓存、安装软件

```bash
[root@localhost yum.repos.d]# yum clean all 
Repository AppStream is listed more than once in the configuration
0 文件已删除
[root@localhost yum.repos.d]# yum makecache 

//安装软件
[root@localhost yum.repos.d]# yum install -y httpd
//卸载软件
[root@localhost yum.repos.d]# yum erase  httpd
```

