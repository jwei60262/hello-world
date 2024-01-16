# Desktop clean
1. .ssh
2. ss
3. chrome logout
4. chrome clean syn item
5. chrome 自动填充、密码管理
6. local git file
7. /download
8. 我的文档
9. /weixin
10. QQ
11. 桌面文档
12. C:\Users\wj\AppData\Roaming\Typora\typora-user-images\
13. resilio
14. BaiduNetdiskDownload

# Tools

## Install google play

方法一：

“谷歌服务下载器”App

方法二：

https://www.apkmirror.com/

方法三：

1. Google 服务框架
2. Google Play Services
3. Play Store

## Axure RP Key

Axure rp 9.0.0.3727

Licensee:
Freecrackdownload.com

Key:
5vYpJgQZ431X/G5kp6jpOO8Vi3TySCBnAslTcNcKkszfPH7jaM4eKM8CrALBcEC1

## OBS Studio

录屏

# 设计原则

- 多考虑一个量级
- 面向抽象，依赖倒置
- 设计模式 == 词牌：菩萨蛮、满江红
- 复用组件，对抗冗余
- 模仿 spring boot 的做法，工具替代手工
- 差异化就是大同小异
- 可扩展性多使用多态

# 开源

**哪种协议**

看软件作者的诉求， Apache v2/BSD/MIT/GPL/LGPL等都是常见的选择。一般来说，商业友好的License是Apache V2；学术界用的比较多的是BSD和MIT， 硬件或者内核相关用的是GPL和LGPL。

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
	
	yum install -y man man-pages
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
	
	ps aux
	ps -elf
	top
	pstree -aup

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

JIT(Just In Time Compiler)

HotSpot

## WebAssembly

https://www.zhihu.com/question/304577684

# DOCS #

[![stable](https://img.shields.io/badge/stable-stable-green.svg)](url)

## DistroWatch ##

[DistroWatch](https://distrowatch.com/)

## GitLab ##

[GitLab](https://about.gitlab.com/)

安装 https://gitlab.cn/install/

docker 安装 https://docs.gitlab.com/ee/install/docker.html

服务器上的 Git - [GitLab](https://git-scm.com/book/zh/v2/%E6%9C%8D%E5%8A%A1%E5%99%A8%E4%B8%8A%E7%9A%84-Git-GitLab)

GitLab 社区版的 [readme](https://gitlab.com/gitlab-org/gitlab-ce/tree/master) 文件

GitLab [compared](https://about.gitlab.com/devops-tools/) to other DevOps tools

[Maintenance commands](https://docs.gitlab.com/omnibus/maintenance/README.html#get-service-status)

Omnibus GitLab [documentation](https://docs.gitlab.com/omnibus/)

**Bitnami GitLab**

If no IP address is assigned,try reloading the IP address by executing the command below.

	sudo /etc/init.d/networking force-reload

[Start Or Stop Services](https://docs.bitnami.com/virtual-machine/apps/mediawiki/administration/control-services/)

## CMS ##

## Mediawiki ##

https://bitnami.com/stack/mediawiki/installer

https://bitnami.com/stack/mediawiki/README.txt

## npm ##

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

## Remote API

RPC

- TCP
  - RMI
- HTTP
  - gRPC
  - JSON RPC

CORBA -- TCP

SOAP -- WebService -- HTTP

RESTFUL

## Gradle

https://scans.gradle.com/

# Docker

## CLI

```
# 停止所有的容器
docker stop `docker ps -q`
docker stop `docker ps -a | grep Up | awk '{print $1}'`

# 打印停止的容器ID
docker ps -a | grep Exit | awk '{print $1}'
# 删除停止的容器
docker rm `docker ps -a | grep Exit | awk '{print $1}'`
docker rm `docker ps -q -f status=exited`
# 强制删除所有容器
docker rm -f `docker ps -aq`
docker container prune
docker container prune --force --filter "until=5m"
docker container prune --force --filter "until=2017-01-04T13:10:00"
```

## Docker

**Manage Docker as a non-root user**

https://docs.docker.com/install/linux/linux-postinstall/#configure-docker-to-start-on-boot

如果希望 docker daemon 在系统启动的时候会自动启动的话，使用下边的命令

```
sudo systemctl enable docker
```

将你的用户添加到 docker 组

```
sudo usermod -a -G docker <username>
or
sudo usermod -aG docker $USER
```

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

**Install Docker Engine on CentOS**

https://docs.docker.com/install/linux/docker-ce/centos/

**Install using the repository on Ubuntu**

https://docs.docker.com/engine/install/ubuntu/#install-using-the-repository

**Install from a package  on Ubuntu**

https://docs.docker.com/engine/install/ubuntu/#install-from-a-package

**docker command**

```
docker images
docker logs peer0.org1.example.com
```

## Docker-Compose

**Install Compose on Linux systems**

安装docker-compose而非docker-compose-plugin最新版本

```
 sudo apt-get update
 sudo apt-get install docker-compose
```

或者参考下面的安装文档

https://docs.docker.com/compose/install/#install-compose

Apply executable permissions to the binary

```
sudo chmod +x /usr/local/bin/docker-compose
```

查看是否安装成功

```
docker-compose --version
```

## 问题

**问题描述：**

docker-compose segment fault

**解决方法：**

如果调用docker-compose的时候有segment fault错误，用sudo apt-get purge docker-compose卸载一下，同时清理/usr/local/bin 下面的docker-compose，然后重新安装sudo apt-get install docker-compose。

**问题描述：**

dial unix /var/run/docker.sock: connect: permission denied

**解决方法：**

https://stackoverflow.com/questions/51342810/how-to-fix-dial-unix-var-run-docker-sock-connect-permission-denied-when-gro

```
ls -last /var/run/docker.sock
cat /etc/group
cat /etc/group | grep docker

whoami //查看当前用户
echo $USER //打印当前用户
groups //查看所有群组
groups $USER //查看当前用户所在群组

sudo usermod -aG docker $USER //当前用户加入docker群组
sudo reboot //重启系统
```

# 软件版本

## standalone 

代码发布打包的时候，有很多种方式，其中一种方式在打包的时候可以将整个项目中所用到的依赖包全部一起打包。一般叫做`Standalone Application`.j即可独立运行的应用。

这种打包方式的优点是显而易见的，即打包之后一个Jar即可运行。迁移快，成本低。相反的，其缺点是如果依赖包升级，则需要重新发布打包。所以这种方式适用于小项目，依赖包少的项目。

## Java version

https://www.baeldung.com/oracle-jdk-vs-openjdk

## JEE version

https://www.baeldung.com/java-enterprise-evolution

# zentao

## 安装 Docker

https://docs.docker.com/engine/install/centos/

使用容器生成镜像

```
docker commit os_name image_name:version
```

## 安装 Docker Compose

https://docs.docker.com/compose/install/

## 查看版本

```
docker --version
docker-compose --version
```

## Docker方式部署禅道

https://www.zentao.net/book/zentaopmshelp/405.html

## 创建docker网络驱动

```
sudo docker network create --subnet=172.172.172.0/24 zentaonet
```

## 启动禅道容器

示例1

```
sudo docker run --name zentao -p 80:80 --network=zentaonet --ip 172.172.172.172 --mac-address 02:42:ac:11:00:00 -v /app/zentaopms:/app/zentaopms -v /app/mysqldata:/var/lib/mysql -e MYSQL_ROOT_PASSWORD=jdie34 -d easysoft/zentao:latest
```

示例2

```
sudo docker run --name zentaossl -p 443:443 --network=zentaonet --ip 172.172.172.173 --mac-address 02:42:ac:11:00:03 -v /zentaoapp/zentaopms:/app/zentaopms -v /zentaoapp/mysqldata:/var/lib/mysql -e MYSQL_ROOT_PASSWORD=jdie34 -d easysoft/zentao:latest
```

## 访问容器

```
docker exec -it zentao /bin/bash
```

## mysql配置

配置信息已经成功保存到 */app/zentaopms/config/my.php* 中。可继续修改此文件。

```
<?php
$config->installed       = true;
$config->debug           = false;
$config->requestType     = 'PATH_INFO';
$config->timezone        = 'Asia/Shanghai';
$config->db->host        = '127.0.0.1';
$config->db->port        = '3306';
$config->db->name        = 'zentao';
$config->db->user        = 'root';
$config->db->encoding    = 'UTF8';
$config->db->password    = 'jdie34';
$config->db->prefix      = 'zt_';
$config->webRoot         = getWebRoot();
$config->default->lang   = 'zh-cn';
```

## Linux一键安装开机启动

```
echo '/opt/zbox/zbox restart' >> /etc/rc.local
chmod +x /etc/rc.d/rc.local
reboot
```

## 禅道使用方法

https://www.zentao.net/book/zentaopmshelp/40.html

## HTTPS

**一、新建 docker 容器，映射 443 端口**

**二、获取证书文件 *.pem，*.key**

将证书文件保存到 docker volume 指定的 host 主机目录中，例如 /zentaoapp/zentaopms/ssl

**三、启用 ssl**

```
docker exec -it zentaossl /bin/bash
apt upgrade apache2
a2enmod ssl
a2ensite default-ssl
```

详情阅读 https://ubuntu.com/server/docs/web-servers-apache

**四、修改 ssl 配置文件**

ssl 配置文件路径：

```
/etc/apache2/sites-available/default-ssl
```

配置证书路径：

```
/app/zentaopms/ssl/certs/projects.xdlianrong.com.pem
/app/zentaopms/ssl/private/projects.xdlianrong.com.key
```

配置 DocumentRoot：

```
DocumentRoot /app/zentaopms/www
```

配置 Directory

```
<Directory />
    SSLOptions +StdEnvVars
    Options FollowSymLinks
    AllowOverride All
    Require all granted
</Directory>
```

重启 apache2 服务

```
service apache2 reload
```

参考：

- http://httpd.apache.org/docs/2.4/ssl/
- http://httpd.apache.org/docs/2.4/ssl/ssl_howto.html
- https://ubuntu.com/server/docs/web-servers-apache

## Nginx 反向代理实现 HTTPS

使用nginx配置反向代理,并且在nginx上配置证书即可.以下是详细步骤:

1. 使用[阿里云配置证书](https://common-buy.aliyun.com/?spm=5176.2020520163.0.0.89b656a7ufvvod&commodityCode=cas)(可以选择OV免费版,按照提示操作即可)

2. 在服务器上配置nginx:

   ```
   vim /etc/nginx/nginx.conf
   ```

   然后在打开的页面中找到server {}项,在里面配置:

   ```
   listen       443 ssl http2 default_server;
   #listen       [::]:443 ssl http2 default_server; //ipv6,可以不配置
   server_name  证书对应的域名;
   root         /usr/share/nginx/html;//此处无需改动
   ssl_certificate pem格式文件所在的目录;
   ssl_certificate_key key格式文件所在的目录;
   ssl_session_cache shared:SSL:1m;
   ssl_session_timeout  10m;//超时时间
   ssl_ciphers HIGH:!aNULL:!MD5;//加密组件,如有更安全或者更新的也可以使用
   ssl_prefer_server_ciphers on;
   ```

3. 启动nginx即可

```
nginx
```

## 数据备份

及时备份数据。

## 故障排除

**禅道容器启动失败**

首先考虑存储空间的问题(区块链节点会占用大量存储空间)

1. 使用docker logs name查看对应容器的日志，name为容器名称

2. 如出现 `/etc/init.d/mysql: ERROR: The partition with /var/lib/mysql is too full!`则为存储空间不足，需要使用 `df -h `命令查看存储空间剩余，使用 `du -sh`查看当前目录下的空间占用
