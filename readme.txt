Git is a distributed version control system.
Git is free software distributed under the GPL.

Git is a distributed version control system.
Git is a free software.

Git has a mutable index called stage.

Git tracks changes of files.

--------------------------------------------------------------------------------
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

删除文件：
1、删除工作区文件
	rm file
直接在工作区删除，对暂存区和版本库没有任何影响。
2、删除动作加入暂存区
	git rm file
	git commit -m "delete file..."
此时，文件在最新的提交中被删除了，但是在历史提交中还在
更简洁的方法：
	git add -u
	git commit -m 

------------------------------------server---------------------------------------	
push到远程服务器：
1、关联一个远程库
		git remote add origin https://github.com/path/repo-name.git
	使用上述的命令，以后每次提交的时候都需要输入用户名和密码，比较麻烦，可以换成下面的命令：
		git remote add origin git@github.com/path/repo-name.git
	如果已经使用了第一条命令，想切换到第二条命令的模式，可以用下面的命令修改：
		git remote set-url origin git@github.com/path/repo-name.git
	这样，以后push就不用输入用户名和密码了。（需要在repo页面，右下角选择clone with ssh）。
2、关联后，使用
		git push -u origin master
	第一次推送master分支的所有内容
3、以后每次提交，使用
		git push origin master
		
clone到本地：
		git clone git@github.com/path/repo-name.git

更新至本地：
		git fetch origin master #update local file from server
		git log -p master..origin/master	#compare diff
		git merge origin/master		#merge
	或者
		git fetch origin master:tmp
		git diff tmp	#compare difference
		git merge tmp	#merge to master
	或者
		git pull origin master   #直接从服务器同步并合并到本地，不执行diff检查
		
		

-------------------------------------branch----------------------------------------		
creating a new branch:
		git branch new_branch_name
	or:
		git checkout -b new_branch_name
	the latter one wiil switch to the new branch automatically	
switching to a branch:
		git checkout new_branch_name
merge a branch to master:
		git merge new_branch_name
delete a branch:
		git branch -d new_branch_name


		
