# git 手册


创建版本库

	mkdir //文件夹名称
	git init  //生成.git
	git add 文件名 
	git commit -m "注释"


版本回退

	git log
	git log --pretty=oneline 
	git reset --hard HEAS^   //回到上一个版本
	git reset --hard 1094a   //1094a是ID号
	git reflog   //记录的每条命令
	git status  //查看状态

管理修改

	//第一次修改 -> git add -> 第二次修改 -> git commit
	git diff HEAD -- readme.txt   //第二次修改不会被提交
	//第一次修改 -> git add -> 第二次修改 -> git add -> git commit
	git diff HEAD -- readme.txt  //第二次修改被提交了
撤销修改

	git checkout -- readme.txt //意思就是，把readme.txt文件在工作区的修改全部撤销
	//一种是readme.txt自修改后还没有被放到暂存区，现在，撤销修改就回到和版本库一模一样的状态；
	//一种是readme.txt已经添加到暂存区后，又作了修改，现在，撤销修改就回到添加到暂存区后的状态。
	//总之，就是让这个文件回到最近一次git commit或git add时的状态。
	注意：git checkout -- file命令中的--很重要，没有--，就变成了“切换到另一个分支”的命令

删除文件

	git rm test.txt   //删除文件
	git commit -m ''  //提交一下
	git checkout -- test.txt  //误删的可以恢复最新版本

分支管理
创建分支

	git checkout -b dev   //创建dev分支并且切换到dev
	//下两句同git checkout -b dev
	git branch dev
	git checkout dev
	//
	git branch    //查看所有分支
	git merge dev  //合并dev分区到master上
	git merge --no-ff -m "merge with no-ff" dev //合并分支表示禁用Fast forward
	//合并分支时，加上--no-ff参数就可以用普通模式合并，合并后的历史有分支，能看出来曾经做过合并，而fast forward合并就看不出来曾经做过合并。
	git branch -d dev //删除dev分支
	git checkout master //完成工作后切换到master
	//几步
	查看分支：git branch
	创建分支：git branch <name>
	切换分支：git checkout <name>
	创建+切换分支：git checkout -b <name>
	合并某分支到当前分支：git merge <name>
	删除分支：git branch -d <name>

冲突

	git status    //查看冲突文件
	git log --graph --pretty=oneline --abbrev-commit
bug分支

	git stash  //可以把当前工作现场“储藏”起来，等以后恢复现场后继续工作
	确定要在哪个分支上修复bug，假定需要在master分支上修复，就从master创建临时分支

	git stash list  //查看储藏现场
	//恢复现场
	//一是用git stash apply恢复，但是恢复后，stash内容并不删除，你需要用git stash drop来删除；
	//另一种方式是用git stash pop，恢复的同时把stash内容也删了
	git stash apply stash@{0}  //恢复指定的stash

Feature分支

	//销毁没有（不能）合并的分支
	git branch -d feature-vulcan  //销毁分支的时候提示没有提交不能销毁
	git branch -D feature-vulcan  // -D 强制删除

分支管理策略

	git remote -v //显示更详细的远程库信息
	//显示了可以抓取和推送的origin的地址。如果没有推送权限，就看不到push的地址

	推送分支
	//就是把该分支上的所有本地提交推送到远程库。推送时，要指定本地分支，这样，Git就会把该分支推送到远程库对应的远程分支上
	git push origin master
	git push origin dev
	//master分支是主分支，因此要时刻与远程同步；
	//dev分支是开发分支，团队所有成员都需要在上面工作，所以也需要与远程同步；
	//bug分支只用于在本地修复bug，就没必要推到远程了，除非老板要看看你每周到底修复了几个bug；
	//feature分支是否推到远程，取决于你是否和你的小伙伴合作在上面开发。

	抓取分支
	git clone git@github.com:michaelliao/learngit.git
	git checkout -b dev origin/dev    //创建远程origin的dev分支到本地
	//另一个人对同样的文件作了修改
	git push origin dev //推送失败
	git pull  //也失败了,原因是没有指定本地dev分支与远程origin/dev分支的链接，根据提示，设置dev和origin/dev的链接
	git branch --set-upstream-to=origin/dev dev
	//再pull,git pull成功，但是合并有冲突，需要手动解决,解决后，提交，再push

多人协作的工作模式通常

	//首先，可以试图用git push origin <branch-name>推送自己的修改；
	//如果推送失败，则因为远程分支比你的本地更新，需要先用git pull试图合并；
	//如果合并有冲突，则解决冲突，并在本地提交；
	//没有冲突或者解决掉冲突后，再用git push origin <branch-name>推送就能成功！

rebase

	 git rebase //rebase操作的特点：把分叉的提交历史“整理”成一条直线，看上去更直观。缺点是本地的分叉提交已经被修改过了。
 忽略特殊文件
 
	 .gitignore文件  //把要忽略的文件名填进去，Git就会自动忽略这些文件
	 git add -f App.class //强制添加
	 git check-ignore -v App.class  //Git会告诉我们，.gitignore的第几行规则忽略了该文件

配置别名

	 git config --global alias.st status  //status变成st
	 git config --global alias.unstage 'reset HEAD'  //reset HEAD'变成unstage




