##  git的基本上传下载操作

###  1.克隆

~~~yaml
# 克隆项目，不需要初始化git仓库，默认选择master分支
git clone origin

# 克隆项目，不需要初始化git仓库，选择develop分支克隆
git clone -b develop origin 
~~~

###  2.分支

```yaml
#查看当前所具有的分支
git branch

#查看当前所具有的分支（包含上一次push的记录）
git branch -v  

#将分支与master合并
git merge
```

###  3.add 、commit

```yaml
#将文件或者文件夹添加到暂存区
git add 文件夹/文件名.后缀 

#将修改的文件全部提交到暂存区
git add .

#撤销上一次的add
git reset HEAD

#撤销上一次的commit，不撤销git add . 不修改空间代码
git reset --soft HEAD^

#撤销上一次的commit，撤销git add . 不修改空间代码
git reset --mixed HEAD^

#撤销上一次的commit，撤销git add . 修改空间代码
git reset --hard HEAD^

#修改commit的备注
git commit --amend

#将文件提交到本地仓库
git commit -m "操作；备注" 


```

###  4.远程仓库

~~~yaml

#查看有无远程仓库地址
git remote -v 

#给本地仓库添加远程仓库地址并且取别名  
git remote add 地址别名 远程仓库地址 

#删除远程仓库地址
git remote rm 地址别名

#提交代码
git push 地址别名 分支名 

#出现fatal: refusing to merge unrelated histories错误
git pull origin master --allow-unrelated-histories

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



