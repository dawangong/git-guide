#### git-test
##### git命令

1.本地项目关联到远程仓库
```git
git init
git remote add origin git@github.com:<UserName>/<RepositoriesName>.git
```

2.建立分支
```git
git branch <BranchName>
```

3.切换分支
```git
git checkout <BranchName>
```

4.新建并切换分支
```git
git checkout -b <BranchName>
```

5.查看本地分支
```git
git branch
```

6.查看远程分支
```git
git branch -r
```

7.查看所有分支
```git
git branch -a
```

8.放弃本次修改
```git
git checkout <FileName>
```

9.删除本地分支
```git
git branch -d <BranchName>
```

10.删除远程分支
```git
git push origin --delete <BranchName>
```

11.新建分支添加关联（push）
```git
git push --set-upstream origin <BranchName>    远程会自动创建同名分支
```

12.新建分支主动push并添加关联
```git
git push -u origin <BranchName>    远程会自动创建同名分支
```

13.新建本地分支添加关联（pull）
```
git branch --set-upstream-to=origin/<BranchName>   远程已存在同名分支时
```

14.推送及拉取指定分支
```git
git push origin <BranchName>
git pull origin <BranchName>
```

15.注释说明写错需要修改时
```git
git commit --amend
```

16.上面指令会进入vm编辑器模式
```git
命令模式下按i进入插入模式修改
ESC键返回命令模式
英文状态下输入 :wq 保存并退出
```

17.英文状态下 按q退出git log

18.合并某分支到当前分支
```git
git merge <BranchName>
git rebase <BranchName> // 不会产生无效的commit message
```

19.版本回退
```git
git reset --hard HEAD^     回退到上一版本
git reset --hard HEAD^^    回退到上上一版本
git reset --hard HEAD~100  回退到上100版本
git reset --hard <commit id>  回退到某版本
```

20.强制推送
```git
git push -f
git push -f origin <BranchName>
```

21.查看所有分支的所有操作记录（包括（包括commit和reset的操作），包括已经被删除的commit记录
```git
git reflog
```

22.不小心将代码改到了master，想保存改动到qa分支并恢复master
```git
master: git stash
master: git checkout qa
qa: git stash apply
```

23.基本
```git
git add .            添加所有改动文件到缓存区
git commit -m "xxx"  提交修改
git push             当前分支只有一个远程分支时
git clone <https> | <ssh>
```

24.git commit -am "xxx"
```git
效果等同于:
git add .
git commit -m "xxx"
```

25.commit很多次但只想要一个commit
```git
假设在此之前已经commit过一次,之后的commit如下操作:
git commit -a --amend -m "xxx"
```

26.合并commit（例如合并1-3条）
```git
git rebase -i HEAD~3

执行后如下:
pick  '注释**********'

pick  '注释*********'

pick  '注释**********'
修改如下:

pick  '注释**********'

s     '注释*********'

s     '注释**********'

如果有冲突，需要修改,完成后要输入保存指令:
git add .  
git rebase --continue

放弃合并:
git rebase --abort

没有冲突则保存退出即可。

合并之后commit message也会被合并，如果需要修改可以使用修改commit的命令，同15:
git commit --amend
```


