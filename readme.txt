**git学习记录**

**创建空文件夹作为git仓库**

​		--git init 	//初始化git仓库

**把文件添加到git仓库**

​		--git add <文件>	//把工作区要提交的修改添加到暂存区（stage）

​				--git add readme.txt	(例子)

​				--git add .	//简化

​		--git commit -m <message>	//把暂存区的所有内容提交当前分支（master）

​				--git add -m “这是第一次提交”

**掌握工作区的状态**

​		--git status	//查看文件是否被修改过

​		--git diff	//查看修改的内容

**版本回退**

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

**在进行git操作，如git log，如果不正常退出（CTRL+C），会出现看不到输入，只看见光标闪烁的情况**

​	git操作中正常退出是q

​		reset重置Git Bash

​		关闭Git Bash重新打开

**工作区和暂存区**

​		工作区-->当前文件夹看到的目录

​		.git文件夹-->git版本库

​				版本库中最重要的是暂存区（Stage或者叫Index）和git自动创建的第一个分支master，以及指向master的一个指针HEAD

​		{工作区} ---add---> {{stage}---commit--->{master}}

​		工作区修改的内容用git add .指令提交到stage(暂存区)

​		stage(暂存区)的所有内容用git commit -m <message>指令提交到当前分支master

**管理修改**

​		第一次修改 -->git add -->git commit -->修改成功提交

​		第一次修改 --> git add --> 第二次修改 --> git commit --> 第一次修改成功提交，第二次修改提交失败

​				-- 没有把修改提交到暂存区的内容是不会提交到当前分支master的

​		第一次修改 --> git add --> 第二次修改 --> git add --> git commit -->两次修改成功提交

**撤销修改**

​		修改了工作区的内容，想要取消修改时

​				--git restore <file>	//丢弃工作区的改动

​		修改了工作区的内容，并提交到stage（暂存区），想要取消暂存

​				--git restore -- staged <file>	//取消暂存

**删除文件**

​		如果在文件管理器中删除了文件，或者用rem删除

​				--rem <file>

​		git会知道哪些文件被删除，现在有两个选择

​				从版本库中删除这个文件，并且commit

​						--git rm <file>

​						--git commit -m <message>

​				恢复删除了的文件

​						--git restore <file>

​				