> git checkout 一般用的最多的就是切换分支
>
> 其实不然，git后面出了git switch 命令专门用来切换分支
>
> 本文先讲常规的操作后面主要讲述检出的意思

##### 基础操作

- `git checkout xxx` 从当前分支上切换到名为xxx的分支上
- `git checkout -b xxx`    从当前分支上切换到一个新建一个名为xxx的分支，它其实是`git branch xxx gitcheckout xxx`2条命令的缩写

##### 高级用法

- `git checkout -b xxx commitid`   从历史提交中的某次commit分离出一个新的分支名叫xxx（`git checkout commitid  -b xxx`）一样的可以
- git checkout -- <file>



