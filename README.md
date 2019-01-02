# DOCS #

[![stable](https://img.shields.io/badge/stable-stable-green.svg)](url)

## 菜鸟教程 ##

[Runoob](http://www.runoob.com/)

## DistroWatch ##

[DistroWatch](https://distrowatch.com/)

## GitLab ##

### GitLab ###

[GitLab](https://about.gitlab.com/)

服务器上的 Git - [GitLab](https://git-scm.com/book/zh/v2/%E6%9C%8D%E5%8A%A1%E5%99%A8%E4%B8%8A%E7%9A%84-Git-GitLab)

GitLab 社区版的 [readme](https://gitlab.com/gitlab-org/gitlab-ce/tree/master) 文件

GitLab [compared](https://about.gitlab.com/devops-tools/) to other DevOps tools

[Maintenance commands](https://docs.gitlab.com/omnibus/maintenance/README.html#get-service-status)

Omnibus GitLab [documentation](https://docs.gitlab.com/omnibus/)

### Bitnami GitLab ###

The Bitnami GitLab CE [Stack](https://bitnami.com/stack/gitlab)

Bitnami [gitlab docs](https://docs.bitnami.com/virtual-machine/apps/gitlab/)

To see the current IP address, execute the following command at the server console after logging in:

	sudo ifconfig

If no IP address is assigned,try reloading the IP address by executing the command below.

	sudo /etc/init.d/networking force-reload

## MOAC ##

[MOAC](http://www.moacchina.net/)

Github [MOACChain/moac-core](https://github.com/MOACChain/moac-core/wiki)

## Git ##

	git -c http.sslVerify=false clone 'url'
	
	git config --system --unset credential.helper
	
	git config --global user.name "wei"
	git config --global user.email "zxll760606@sina.com"
	
	git config --global http.sslVerify false  
	
	git push -u origin master

### Command line instructions ###

Git global setup

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

### SSH key ###

[Connecting to GitHub with SSH](https://help.github.com/articles/connecting-to-github-with-ssh/)

[Generating a new SSH key](https://help.github.com/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent/)

## Vagrant ##

[Vagrant](https://www.vagrantup.com/downloads.html)

	vagrant status
	vagrant suspend
	vagrant up
	vagrant ssh
	vagrant halt
	vagrant destroy

## VirtualBox ##

[VirtualBox](https://www.virtualbox.org/wiki/Downloads)

## Ubuntu ##

### Ubuntu packages ###

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

	mdkir
	mv
	rm
	rmdir
	cp

	echo
	echo $PATH

更新软件

	cat /etc/apt/sources.list
	sudo apt-get update
	sudo apt-get upgrade
	sudo apt-get autoremove

安装finger,查看用户信息

	sudo apt-get install finger
	finger
	finger vagrant
	cat /etc/passwd
	username:password:UID:GID:UID info:home directory:command/shell

创建新用户,为用户授权

	sudo adduser student
	ssh student@127.0.0.1 -p 2222
	sudo cat /etc/sudoers (查看哪些用户有root权限,可以执行sudo命令)
	sudo ls /etc/sudoers.d
	sudo cp /etc/sudoers.d/vagrant /etc/sudoers.d/student

SSH 远程登录

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

File permissions

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

Ports

	HTTP 80 HTTPS 443 SSH 22
	FTP 21 POP3 110 SMTP 25
	cat /etc/ssh/sshd_config 查看ssh端口

Firewalls

	sudo ufw status
	sudo ufw default deny incoming
	sudo ufw default allow outgoing
	sudo ufw allow ssh
	sudo ufw allow 22/tcp
	sudo ufw allow www
	sudo ufw enable