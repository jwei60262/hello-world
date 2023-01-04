# Desktop clean
1. .ssh
2. ss
3. chrome logout
4. chrome clean syn item
5. local git file
6. /download
7. 我的文档
8. /weixin
9. QQ
10. 桌面文档
11. C:\Users\wj\AppData\Roaming\Typora\typora-user-images\
12. resilio
13. BaiduNetdiskDownload

# Install google play

方法一：

“谷歌服务下载器”App

方法二：

https://www.apkmirror.com/

方法三：

1. Google 服务框架
2. Google Play Services
3. Play Store

# Linux

## Ubuntu

**Ubuntu packages**

[Ubuntu.com/](https://packages.ubuntu.com/)

[Sudoers](https://help.ubuntu.com/community/Sudoers)

## Linux Shell Command ##

[Cheatsheet of less's Keyboard](http://sheet.shiar.nl/less)

[Introduction to Regular Expressions](http://codular.com/regex)

	cat /etc/issue
	logout
	
	出现 > 时,用 ' 补全.也可以尝试 /
	ls *pp*
	ls p*png
	ls app.{css,html}
	ls app.css app.html
	ls *{jpg,JPG}
	
	ls be[ae]r.png
	bear.png beer.png
	
	ls bea?.png
	bean.png bear.png (A single question mark matches any one character.)
	
	history
	man ls
	man cowsay
	apropos
	man apropos
	curl http://udacity.github.io/ud595-shell/stuff.zip -o things.zip
	unzip things.zip
	expr 2 + 2
	hostname
	host udacity.com
	date
	
	cat test.txt
	diff
	less test.txt
	< (home)
	> (end)
	500 (page number)
	/ string or expressions (search)
	n (next occurrence)
	N (previous occurrence)
	
	ping 8.8.8.8
	ctrl + C
	
	sort
	bbb
	ccc
	aaa
	ctrl + D
	
	bc
	2+3*4
	ctrl + D
	
	vim
	emacs
	joe
	nano
	
	pwd
	cd /
	cd ..
	cd $HOME/.profile == cd ~/.profile
	
	mdkir
	mv
	rm
	rmdir
	cp
	
	echo
	echo $PATH
	
	sudo find / -iname LocalSettings.php -print

**安装finger,查看用户信息**

	sudo apt-get install finger
	finger
	finger vagrant
	cat /etc/passwd
	username:password:UID:GID:UID info:home directory:command/shell

**创建新用户,为用户授权**

	sudo adduser student
	ssh student@127.0.0.1 -p 2222
	sudo cat /etc/sudoers (查看哪些用户有root权限,可以执行sudo命令)
	sudo ls /etc/sudoers.d
	sudo cp /etc/sudoers.d/vagrant /etc/sudoers.d/student

[Sudoers](https://help.ubuntu.com/community/Sudoers)

**SSH 远程登录**

	sudo apt-get install openssh-server
	
	(client)
	ssh keygen
	
	(server)
	mkdir .ssh
	touch .ssh/authorized_keys
	nano .ssh/authorized_keys
	chmod 700 .ssh
	chmod 644 .ssh/authorized_keys
	
	(log with ssh)
	ssh student@127.0.0.1 -p 2222 -i ~/.ssh/id_rsa
	
	sudo nano /etc/ssh/sshd_config
	设置以禁止使用passwd登录
	sudo service ssh restart
	(or)
	/etc/init.d/ssh start

**File permissions**

<table>
  <tr>
    <td>Read</td>
	<td>Write</td>
	<td>Execute</td>
  </tr>
  <tr>
    <td>r = 4</td>
	<td>w = 2</td>
	<td>x = 1</td>
  </tr>
  <tr>
    <td>r = 0</td>
	<td>w = 0</td>
	<td>x = 0</td>
  </tr>
</table>


	chmod 641 .ssh/authorized_keys (更改文件权限)

<table>
  <tr>
    <td>Owner</td>
	<td>Group</td>
	<td>Everyone</td>
  </tr>
  <tr>
    <td>rw-</td>
	<td>r--</td>
	<td>--x</td>
  </tr>
  <tr>
    <td>4+2+0=6</td>
	<td>4+0+0=4</td>
	<td>0+0+1=1</td>
  </tr>
  <tr>
    <td>Octal 6</td>
	<td>Octal 4</td>
	<td>Octal 1</td>
  </tr>
</table>


**Ports**

	HTTP 80 HTTPS 443 SSH 22 DNS 53
	FTP 21 POP3 110 SMTP 25
	cat /etc/ssh/sshd_config 查看ssh端口

**Firewalls**

	sudo ufw status
	sudo ufw default deny incoming
	sudo ufw default allow outgoing
	sudo ufw allow ssh
	sudo ufw allow 22/tcp
	sudo ufw allow www
	sudo ufw enable

**Configure A Static IP Address**

[configure-static-address](https://docs.bitnami.com/virtual-machine/faq/configuration/configure-static-address/)

## Linux tools ##

**Webmin**

[webmin](http://www.webmin.com/)

[install-webmin](https://docs.bitnami.com/virtual-machine/faq/configuration/install-webmin/)

**wget**

	wget http://prdownloads.sourceforge.net/webadmin/webmin_1.900_all.deb

**scp**

```
git bash:
scp -r C:/Users/wj/Downloads/gerrit-2.15.1.war weijia@192.168.44.132:/home/weijia
scp -r root@149.28.209.204:/root/ d:/temp
scp -r -i ~/.ssh/linuxonekey.pem linux1@148.100.245.68:/home/linux1/fabric-samples/hyperledger-fabric-linux-amd64-1.4.2.tar.gz d:/temp
```

**git config**

```
git config --file $GERRIT_SITE/etc/gerrit.config httpd.listenUrl 'http://localhost:8080'
```

**Command-line completion**

```
https://docs.docker.com/compose/completion/
```

# Network

## TCP/IP

### Message

- HTTP -- Data
- TCP -- Segment
- UDP -- Datagram
- IP -- Pack

### FTP

**Server**

SERVER-U

**Client**

CuteFTP

FlashFXP

FTP Explorer

### IP

**分组交换技术**

- IP数据报：IP报文分组
- IP虚电路：IP报文分组

**信元交换技术**

- ATM：53字节的信元，核心路由器将IP报文切换为信元
  - 虚通路
  - 虚通道
- MPLS：ATM IP交换和标记交换
- MPLS-VPN

### IPv4 address space ###

[Here's a visualization of the entire IPv4 address space](http://lh3.googleusercontent.com/cFkfL3BjjIW6M4uaoBBaJqrCeyhtvivrJIPunhze7JFmUy5ezsaMEkoF2T1pspYRSYD-gMZzUBwKSf3yI73i=s0)

[Reserved IP addresses](https://classroom.udacity.com/courses/ud256/lessons/7118148621/concepts/72314704150923)

[test-ipv6](http://test-ipv6.com/)

	ip addr show

Find your default gateway

	ip route show default
	netstat -nr

Private address netblocks

	10.0.0.0/8
	172.16.0.0/12
	192.168.0.0/16

## Ubuntu

https://ubuntu.com/server/docs/network-configuration

## Telnet

```
telnet 47.240.166.195 22 
```

## Netcat ##

```
sudo apt-get install netcat-openbsd tcpdump traceroute mtr

man nc
CLIENT/SERVER MODEL
nc -l 1234
nc 192.168.10.1 1234

printf 'HEAD / HTTP/1.1\r\nHost: en.wikipedia.org\r\n\r\n' | nc en.wikipedia.org 80

sudo lsof -i
```

## Tcpdump

```
sudo tcpdump -n host 8.8.8.8
ping -c3 8.8.8.8
```

```
sudo tcpdump -n port 53
ping yahoo.com
```

```
sudo tcpdump -n port 80
printf 'HEAD / HTTP/1.1\r\nHost: example.net\r\n\r\n' |nc example.net 80
```

## 通信

WiFi 频率

```
2.4 GHz = 2 400 000 000 Hz
5 GHz = 5 000 000 000 Hz
```

5G通信频率

```
huawei 6000兆赫兹 = 6KMHz = 6GHz = 6 000 000 000 Hz
Qualcomm 28千兆赫兹 = 28KMHz = 28GHz = 28 000 000 000 Hz
```

带宽

```
频谱带宽 20MHz
数据容量带宽 1000Mb =  8 * 125M = 125MB
```

## 穿透技术

使用 github 开源项目 frp 进行内网穿透搭建

# Cloud

## 关键技术

**虚拟化**

- 发展
  - 大型机虚拟化
  - X86虚拟化
- 分类
  - 按对象
    - 操作系统虚拟化：将操作系统及系统调用抽象为资源
    - 平台虚拟化：将硬件组件抽象为逻辑资源
  - 按方案
    - 软件虚拟化：截获或模拟物理平台访问
    - 硬件虚拟化：硬件本身提供截获和重定向支持
  - 按方式
    - 全虚拟化
    - 准虚拟化
-  虚拟机监控器：核心的执行和管理层
  - 名称
    - Hypervisor或
    - VMM(Virtual Machine Monitor)
  - 作用
    - 管理虚拟机生命周期，创建、启动、关闭、销毁
    - 为虚拟机抽象出硬件环境，与硬件打交道
  - 类型
    - 运行在硬件上
      - VMM
      - ESX
      - HyperV
      - Xen
    - 运行在操作系统上
      - VMware
      - VirtualBox

**开源虚拟化方案**

- KVM
  - 虚拟机，也叫Guest、客户机
  - 表现为进程
  - 保存为文件
    - 配置文件
    - 虚拟磁盘文件：镜像
- Xen

**弹性计算**

## 虚拟化技术

将物理资源抽象为逻辑单元

- 服务器虚拟化
  - CPU
  - 内存
- 存储虚拟化
  - 固态硬盘
  - 机械硬盘
- 网络虚拟化
  - 虚拟网卡
  - 虚拟交换机
  - 网络IP地址
    - 隔离，多租户
    - 转换，访问外网
- GPU虚拟化

## 云服务名称

运行在Iaas层的服务

- 实例
- 虚拟机
- 含计算服务的名称
- 含弹性计算的名称

# Distributed systems

## Two basic tasks

There are two basic tasks that any computer system needs to accomplish:

- storage
- computation

## Scalability

[**Scalability**](http://en.wikipedia.org/wiki/Scalability) is the ability of a system, network, or process, to handle a growing amount of work in a capable manner or its ability to be enlarged to accommodate that growth.

- Size scalability
- Geographic scalability
- Administrative scalability

### Performance (and latency)

is characterized by the amount of useful work accomplished by a computer system compared to the time and resources used.

Depending on the context, this may involve achieving one or more of the following:

- Short response time/low latency for a given piece of work 短时间
- High throughput (rate of processing work) 高通量
- Low utilization of computing resource(s) 少资源

**Latency**

The state of being latent; delay, a period between the initiation of something and the occurrence.

For example, imagine that you are infected with an airborne virus that turns people into zombies. The latent period is the time between when you became infected, and when you turn into a zombie. That's latency: the time during which something that has already happened is concealed from view.

### Availability (and fault tolerance)

the proportion of time a system is in a functioning condition. If a user cannot access the system, it is said to be unavailable.

Formulaically, availability is: `Availability = uptime / (uptime + downtime)`.

For example:

| Availability %         | How much downtime is allowed per year? |
| ---------------------- | -------------------------------------- |
| 90% ("one nine")       | More than a month                      |
| 99% ("two nines")      | Less than 4 days                       |
| 99.9% ("three nines")  | Less than 9 hours                      |
| 99.99% ("four nines")  | Less than an hour                      |
| 99.999% ("five nines") | ~ 5 minutes                            |
| 99.9999% ("six nines") | ~ 31 seconds                           |

**Fault tolerance**

ability of a system to behave in a well-defined manner once faults occur

## Abstractions and models

- System model (asynchronous / synchronous)
- Failure model (crash-fail, partitions, Byzantine)
- Consistency model (strong, eventual)

## Design techniques: partition and replicate

There are two basic techniques that can be applied to a data set. It can be split over multiple nodes (partitioning) to allow for more parallel processing. It can also be copied or cached on different nodes to reduce the distance between the client and the server and for greater fault tolerance (replication).

## Reference

http://book.mixu.net/distsys/intro.html

# 编程语言

## JIT

Just In Time Compiler，一般翻译为即时编译器，这是是针对解释型语言而言的，而且并非虚拟机必须，是一种优化手段，Java的商用虚拟机HotSpot就有这种技术手段，Java虚拟机标准对JIT的存在没有作出任何规范，所以这是虚拟机实现的自定义优化技术。

HotSpot虚拟机的执行引擎在执行Java代码是可以采用【解释执行】和【编译执行】两种方式的，如果采用的是编译执行方式，那么就会使用到JIT，而解释执行就不会使用到JIT，所以，早期说Java是解释型语言，是没有任何问题的，而在拥有JIT的Java虚拟机环境下，说Java是解释型语言严格意义上已经不正确了。

HotSpot中的编译器是javac，他的工作是将源代码编译成字节码，这部分工作是完全独立的，完全不需要运行时参与，所以Java程序的编译是半独立的实现。有了字节码，就有解释器来进行解释执行，这是早期虚拟机的工作流程，后来，虚拟机会将执行频率高的方法或语句块通过JIT编译成本地机器码，提高了代码执行的效率，至此你已经了解了JIT在Java虚拟机中所处的地位和工作的主要内容。

当JIT编译启用时（默认是启用的），JVM读入.class文件解释后，将其发给JIT编译器。JIT编译器将字节码编译成本机机器代码。 

通常javac将程序源码编译，转换成java字节码，JVM通过解释字节码将其翻译成相应的机器指令，逐条读入，逐条解释翻译。非常显然，经过解释运行，其运行速度必定会比可运行的二进制字节码程序慢。为了提高运行速度，引入了JIT技术。 

在执行时JIT会把翻译过的机器码保存起来，已备下次使用，因此从理论上来说，採用该JIT技术能够，能够接近曾经纯编译技术。   

## WebAssembly

https://www.zhihu.com/question/304577684

# DOCS #

[![stable](https://img.shields.io/badge/stable-stable-green.svg)](url)

## Docker

https://docs.docker.com/install/linux/docker-ce/centos/

https://docs.docker.com/install/linux/linux-postinstall/#configure-docker-to-start-on-boot

**Configure Docker to start on boot**

```
sudo systemctl enable docker 
sudo systemctl disable docker
```

**Start Docker**

```
sudo systemctl start docker
sudo systemctl status docker
```

## DistroWatch ##

[DistroWatch](https://distrowatch.com/)

## GitLab ##

[GitLab](https://about.gitlab.com/)

服务器上的 Git - [GitLab](https://git-scm.com/book/zh/v2/%E6%9C%8D%E5%8A%A1%E5%99%A8%E4%B8%8A%E7%9A%84-Git-GitLab)

GitLab 社区版的 [readme](https://gitlab.com/gitlab-org/gitlab-ce/tree/master) 文件

GitLab [compared](https://about.gitlab.com/devops-tools/) to other DevOps tools

[Maintenance commands](https://docs.gitlab.com/omnibus/maintenance/README.html#get-service-status)

Omnibus GitLab [documentation](https://docs.gitlab.com/omnibus/)

## Bitnami GitLab ##

If no IP address is assigned,try reloading the IP address by executing the command below.

	sudo /etc/init.d/networking force-reload

[Start Or Stop Services](https://docs.bitnami.com/virtual-machine/apps/mediawiki/administration/control-services/)

## CMS ##

## Mediawiki ##

https://bitnami.com/stack/mediawiki/installer

https://bitnami.com/stack/mediawiki/README.txt

## npm 中文文档 ##

<https://www.npmjs.cn/>

[Use Windows Build Tools npm module ](https://github.com/Microsoft/vscode/wiki/How-to-Contribute#build-and-run)

```
 npm install --global windows-build-tools --vs2015
```

## Git ##

**Git SCM**

Source code management

**快照 **

Snapshot: 某一时刻数据的状态

快照流

**book**

https://git-scm.com/book/en/v2

**对象**：commit，tree，blob

https://git-scm.com/book/en/v2/Git-Internals-Git-Objects

**引用**：refs

https://git-scm.com/book/en/v2/Git-Internals-Git-References

**删除敏感信息**

https://docs.github.com/cn/github/authenticating-to-github/keeping-your-account-and-data-secure/removing-sensitive-data-from-a-repository

### Command line instructions ###

Git global setup

	git -c http.sslVerify=false clone 'url'
	
	git config --system --unset credential.helper
	git config --global http.sslVerify false  
	
	git push -u origin master
	
	git config --global user.name "0714weijia"
	git config --global user.email "zxll760606@sina.com"

Create a new repository

	git clone https://gitlab.com/0714weijia/test.git
	cd test
	touch README.md
	git add README.md
	git commit -m "add README"
	git push -u origin master

Existing folder

	cd existing_folder
	git init
	git remote add origin https://gitlab.com/0714weijia/test.git
	git add .
	git commit -m "Initial commit"
	git push -u origin master

Existing Git repository

	cd existing_repo
	git remote rename origin old-origin
	git remote add origin https://gitlab.com/0714weijia/test.git
	git push -u origin --all
	git push -u origin --tags

Status

```
git status --ignored
git add -f <pathspec>
```

## Github ##

**SSH key**

[Connecting to GitHub with SSH](https://help.github.com/articles/connecting-to-github-with-ssh/)

[Generating a new SSH key](https://help.github.com/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent/)

## Vagrant ##

1. Install VirtualBox . [You can download it from virtualbox.org, here.](https://www.virtualbox.org/wiki/Downloads)
2. Install Vagrant. [You can download it from vagrantup.com.](https://www.vagrantup.com/downloads.html)
3. Get started with Vagrant https://www.vagrantup.com/intro/getting-started/index.html

## zentao ##

安装 Docker 

https://docs.docker.com/engine/install/centos/

安装 Docker Compose

https://docs.docker.com/compose/install/

查看版本

```
docker --version
docker-compose --version
```

Docker方式部署禅道

https://www.zentao.net/book/zentaopmshelp/405.html

创建docker网络驱动

```
sudo docker network create --subnet=172.172.172.0/24 zentaonet
```

启动禅道容器

```
sudo docker run --name zentao -p 80:80 --network=zentaonet --ip 172.172.172.172 --mac-address 02:42:ac:11:00:00 -v /app/zentaopms:/app/zentaopms -v /app/mysqldata:/var/lib/mysql -e MYSQL_ROOT_PASSWORD=123456 -d easysoft/zentao:latest
```

禅道开机启动

```
echo '/opt/zbox/zbox restart' >> /etc/rc.local
chmod +x /etc/rc.d/rc.local
reboot
```

## Linuxone

```
ssh linux1@148.100.245.68 -p 22 -i ~/.ssh/mykey.pem
```

## SMTP

发送电子邮件的协议：SMTP

接收电子邮件的协议：IMAP、POP

IMAP：电子邮件存储在服务器上，发送的消息存储在服务器上，消息可以在多个设备上同步和访问。

POP：电子邮件存储在一个设备上，发送的消息存储在单个设备上，电子邮件只能从单个设备访问。

## 远程通信

RPC

- TCP
  - RMI
- HTTP
  - gRPC
  - JSON RPC

CORBA -- TCP

SOAP -- WebService -- HTTP

RESTFUL
