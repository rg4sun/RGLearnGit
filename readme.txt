Git is a distributed version control system.
Git is free software distributed under the GPL.
Git has a mutable index called stage.
Presented By R.G.
brabaraaaaaa--some nonsense words
加入中文字符
理解暂存区stage/index的作用
git diff只能在更改完后,还没commit之前使用,commit之后使用不会显示更改状况
Git tracks changes,now we do a test to see how it tracks changes instead of fileGit tracks changes of files.
那怎么提交第二次修改呢？你可以继续git add再git commit，也可以别着急提交第一次修改，先git add第二次修改，再git commit，就相当于把两次修改合并后一块提交了：

第一次修改 -> git add -> 第二次修改 -> git add -> git commit
如果不用git add到暂存区，那就不会加入到commit中
关于撤销修改，使用 git checkout -- filename 用于撤销工作区的最近一次的修改
如果已经使用git add添加到暂存区了，仍想撤销修改则需要两步：
先使用git reset HEAD filename撤回暂存区中的filename文件，在使用git checkout -- filename来撤销更改
注意：git checkout -- file命令中的--很重要，没有--，就变成了“切换到另一个分支”的命令，我们在后面的分支管理中会再次遇到git checkout命令。

