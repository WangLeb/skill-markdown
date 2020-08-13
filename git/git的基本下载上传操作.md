##  git的基本上传下载操作

~~~java
git clone 远程仓库地址  //克隆项目，不需要初始化git仓库
git clone -b 分支名 地址别名 
git push 地址别名 分支名 //从远程仓库拉取项目，需要初始化git仓库
git branch -v  //查看是否有分支
git branch 分支名 //创建分支
git merge 分支名 //将分支与master合并
git add 文件夹/文件名.后缀  //将文件或者文件夹添加到暂存区
git commit -m "操作；备注" //将文件提交到本地仓库
git remote -v   //查看有无远程仓库地址
git add remote 地址别名 远程仓库地址 //给本地仓库添加远程仓库地址并且取别名
git push -u 地址别名 分支名
git push 地址名 分支名

---以下为冲突操作（尽量不要产生冲突）
cat 文件名.后缀 //查看文件
rm 文件名.后缀 //删除文件，只是系统删除，git的暂存区以及本地仓库仍然存在
git rm --cached 文件名.后缀 //将文件撤出暂存区
git rm --cached -f 文件名.后缀 //强行车粗暂存区
git update-index --assume-unchanged PATH  //在本地仓库移除已经提交的文件 然后git add . git commit -m "init"
rm -f .git/index.lock //在无法删除文件的时候可以使用
//删除文件后记得commit,往往不能提交是因为本地仓库的内容与暂存区的内容混乱
//要记得有问题直接git status，查看git三层结构里面的内容
~~~



