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

场景1：当你改乱了工作区某个文件的内容，想直接丢弃工作区的修改时，用命令git checkout -- file。

场景2：当你不但改乱了工作区某个文件的内容，还添加到了暂存区时，想丢弃修改，分两步，第一步用命令git reset HEAD <file>，就回到了场景1，第二步按场景1操作。

场景3：已经提交了不合适的修改到版本库时，想要撤销本次提交，参考版本回退一节，不过前提是没有推送到远程库。

git checkout其实使用版本库里的版本替换工 作区的版本，无论工作区是修改还是删除，都可以从原版本库恢复；但是从来没有被添加到版本库就被删除的文件，是无法checkout恢复的"

2019.7.16 使用GitHub建立了R.G.的第一个仓库RGLearnGit，此行在建完后测试本地修改push到GitHub的成功性

要关联一个远程库，使用命令git remote add origin git@server-name:path/repo-name.git；

关联后，使用命令git push -u origin master第一次推送master分支的所有内容；

此后，每次本地提交后，只要有必要，就可以使用命令git push origin master推送最新修改；



