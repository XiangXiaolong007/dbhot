版本控制--git管理文件夹(dbhot)
1. 进入要管理的文件夹
2. 初始化 git init(提名)
3. 管理文件夹
4. 生成版本

## 文档
### 第一阶段 单枪匹马开始干
1. git init 初始化
2. git status 检测当前文件夹的状态
  红色  新增的文件/修改了的文件  git add .
  绿色 git已经管理起来 git commit -m '信息'
  生成版本
3. git add xxx 管理某个文件了
4. git commit -m '提交信息' 生成一个版本
5. git log 查看提交的版本

>> 1. git config --global user.email 'you@example.com'
>> 2. git config --global user.name 'your name'

### 第二阶段 功能迭代

### 第三阶段 约饭


1. git reset --hard commitid 回滚
2. git reflog 查看回滚之后的log记录
3. git branch 查看分支
4. git branch 分支名称  创建分支
5. git checkout 分支名称  切换分支
6. 分支合并  git merge 要合并的分支
>> 切换分支注意
7. git branch -d 要删除的分支
8. 给远程仓库起别名 git remote add origin 远程仓库地址
9. 向远程提交推送代码 git push -u origin master(要推送的代码)
10. 克隆远程仓库的代码 git clone 远程仓库地址
11. git pull origin dev 从线上dev分支拉代码到本地
   相当于 git fetch origin dev  &&  git merge origin/dev
12. git rebase 使提交记录变得简洁(如果代码已经提交到远程库，不建议执行rebase)
    git rebase -i HEAD~3 最后三条commit合并

    场景二：把dev分支的记录合并到master 不产生分叉
    git checkout dev
    git rebase master
    git checkout master
    git merge dev
    场景三：避免产生分叉
    git fetch origin dev
    git rebase origin/dev

    注意事项：
    git rebase 产生冲突的时候怎么办
    解决冲突 
    git add .
    git rebase --continue
13. git log --graph图形化展示日志
    git log --graph --pretty=format:"%h %s"  其中h表示hash值 s表示日志记录