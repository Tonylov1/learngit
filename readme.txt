Git is a distributed version control system.
Git is free software distributed under the GPL.

Git is a distributed version control system.
Git is a free software.

Git has a mutable index called stage.

Git tracks changes of files.

Git 用法总结：
1、如果修改了工作区的文件，尚未add，则可以使用
     git checkout -- file
	来恢复修改之前的文件。注意 -- 一定要带上，否则就是创建新分支。
	这个命令实际上是用版本库里的版本替换工作区的版本，同样适用于删除文件的情况。
2、如果已经 git add 了文件，但是还没有commit， 可以使用
	git reset HEAD file
	来回复到第1步的场景。
3、如果已经commit了文件，但是还没有推送到远程库，可以使用版本回退的方法回退到上一个版本。
	git reset --hard HEAD^
4、如果已经推送到远程服务器，呃，木有办法了。。。
	
push到远程服务器：
1、关联一个远程库
		git remote add origin https://github.com/path/repo-name.git
	使用上述的命令，以后每次提交的时候都需要输入用户名和密码，比较麻烦，可以换成下面的命令：
		git remote add origin git@github.com/path/repo-name.git
	如果已经使用了第一条命令，想切换到第二条命令的模式，可以用下面的命令修改：
		git remote set-url origin git@github.com/path/repo-name.git
	这样，以后push就不用输入用户名和密码了。
2、关联后，使用
		git push -u origin master
	第一次推送master分支的所有内容
3、以后每次提交，使用
		git push origin master
		
设置了ssh，但是每次push都要输入用户名和密码，正在寻求解决方案。。。