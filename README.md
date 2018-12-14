# DOCS #

## DistroWatch ##

[DistroWatch](https://distrowatch.com/)

## GitLab ##

### GitLab ###

[GitLab](https://about.gitlab.com/)

服务器上的 Git - [GitLab](https://git-scm.com/book/zh/v2/%E6%9C%8D%E5%8A%A1%E5%99%A8%E4%B8%8A%E7%9A%84-Git-GitLab)

GitLab 社区版的 [readme](https://gitlab.com/gitlab-org/gitlab-ce/tree/master) 文件

GitLab [compared](https://about.gitlab.com/devops-tools/) to other DevOps tools

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

## Linux Shell Command ##

[Cheatsheet of less's Keyboard](http://sheet.shiar.nl/less)

[Introduction to Regular Expressions](http://codular.com/regex)

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

	cat /etc/apt/sources.list