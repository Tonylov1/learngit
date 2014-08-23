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
2、如果已经 git add 了文件，但是还没有commit， 可以使用
	git reset HEAD file
	来回复到第1步的场景。
3、如果已经commit了文件，但是还没有推送到远程库，可以使用版本回退的方法回退到上一个版本。
	git reset --hard HEAD^
4、如果已经推送到远程服务器，呃，木有办法了。。。
	