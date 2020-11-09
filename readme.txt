**git学习记录**

创建空文件夹作为git仓库

​		--git init 	//初始化git仓库

把文件添加到git仓库

​		--git add <文件>

​				--git add readme.txt	(例子)

​		--git commit -m <message>

​				--git add -m “这是第一次提交”

掌握工作区的状态

​		--git status	//查看文件是否被修改过

​		--git diff	//查看修改的内容

版本回退

​		查看commit的记录

​				--git log	//显示最近到最远的提交日志

​				--git log --pretty=oneline	//简化输出的信息

​		HEAD指向的版本是当前的版本

​				--git reset --hard  commit_id	//跳到指定版本，commit_id指的是每次提交的记录的编码，不用写全

​					--git reset --hard HEAD^	//退回上一个版本

​					--git reset --hard HEAD^^	//退两个版本

​					HEAD后的" ^ "符号，每退一个版本就加一个，如果是100个就写HEAD~100

​				--cat <文件名>	//查看文件的内容

​					--cat readme.txt	(例子)

​				退回版本后，想恢复到最新版本，找不到commt_id

​					--git reflog	//查看每次操作的命令，找到commit_id，恢复到想要的版本

​		 