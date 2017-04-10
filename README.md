Git 
1.安装，默认提示即可：https://git-for-windows.github.io
2.安装后运行Git Bash命令窗
3.设置名字和邮箱： git config --global user.name "Your Name"
				   git config --global user.email "email@example.com"
4.初始化版本库：到某处新建空文件夹，打开后右键：Git Bash Here，输入 $ git init
5.添加项目文件，如新建readme.txt后，输入 git add readme.txt，先提交到暂缓区，最后同一 git commit -m "注释说明" 
6. git status 查看仓库当前的状态，文件是否有修改或提交
7. git diff 查看上次修改过的内容
8. git log 查看所有提交日志，git log --pretty=oneline（简洁模式）
9. git reset --hard HEAD^（HEAD^^/HEAD^^^/HEAD~10）,退回到上一次提交的版本
10. git reset --hard 3628164，还原到指定版本，版本号可以在git reflog查
11. cat 文件名，查看文档
12.撤销修改--add前，git checkout --文件名
13.撤销add，git reset HEAD readme.txt
14.删除文件，git rm test.txt（工作区文件同步删除，注意是不可恢复的）后 git commit -m "remove test.txt"
15.工作区删除了文件后可以从版本库中恢复，git checkout -- test.txt
16.远程仓库：注册github账号后，本地 ssh-keygen -t rsa -C "youremail@example.com"，计算机主用户文件夹会新增.ssh，里面有id_rsa和id_rsa.pub两个文件
	id_rsa是私钥，不能泄露出去，id_rsa.pub是公钥，可以放心地告诉任何人。
17.登陆GitHub，打开“Account settings”，“SSH Keys”页面,点“Add SSH Key”，填上任意Title，在Key文本框里粘贴id_rsa.pub文件的内容
18.本地库同步到远程库：github上新建一个库，本地运行 git remote add origin git@github.com:chenyueqin1010/gitTest.git,origin为默认，已作默认关联的不能再用，另取
19.关联后，使用命令git push -u 远程库名 分支名，第一次推送master分支的所有内容
20.此后，每次本地提交后，只要有必要，就可以使用命令git push 远程库名 分支名，推送最新修改
21.远程库克隆到本地：git clone git@github.com:chenyueqin1010/gitTest.git
22.Git鼓励大量使用分支：
	查看分支：git branch
	创建分支：git branch <name>
	切换分支：git checkout <name>
	创建+切换分支：git checkout -b <name>
	合并某分支到当前分支：git merge <name> 									fast forward 模式
						  git merge --no-ff -m "merge with no-ff" 分支名	非fast forward模式
	删除分支：git branch -D <name>
23.当Git无法自动合并分支时，就必须首先解决冲突，再提交合并
	用git log --graph命令可以看到分支合并图
24. git remote查看远程库，git remote -v 详细信息
25. 多人协作：·查看远程库信息，使用git remote -v；
	·本地新建的分支如果不推送到远程，对其他人就是不可见的；
	·从本地推送分支，使用git push origin branch-name，如果推送失败，先用git pull抓取远程的新提交；
	·在本地创建和远程分支对应的分支，使用git checkout -b branch-name origin/branch-name，本地和远程分支的名称最好一致；
	·建立本地分支和远程分支的关联，使用git branch --set-upstream branch-name origin/branch-name；
	·从远程抓取分支，使用git pull，如果有冲突，要先处理冲突。


GitPages远程部署：
1.新建一个库，选初始化（包含一个readme）
2.进入库，settings
3.source那选master branch
4.电脑某处复制项目到本地，右键git bash here：git clone git@github.com:chenyueqin1010/库名.git
5.复制本地项目到该目录
6.关联远程库：git remote add 起个名 git@github.com:chenyueqin1010/库名.git
7.本地添加所有文件：git add .
8.提交：git commit -m "修改信息"
9.git pull
10.git push




