## Git tag

`tag，意为标签，我们给当前本地分支打一个标签，标签常常用来标记发布结点（v1.0，v2.0），这样看下来比较直观，如果我们要看1.0的代码就直接切换到1.0的tag上就行了，如果要在1.0的基础上开发新的功能就在1.0检出分支就行了`

##### 	查看标签

- git tag 列出本地仓库的所有tag，这个命令以字母顺序列出，如果我们要看v1.0系列下的所有标签，可用git  tag -l "v1.0*"

> **Note**  
>
> *按照通配符列出标签需要 `-l` 或 `--list` 选项*
>
> *如果你只想要完整的标签列表，那么运行 `git tag` 就会默认假定你想要一个列表，它会直接给你列出来， 此时的 `-l` 或 `--list` 是可选的。*
>
> *然而，如果你提供了一个匹配标签名的通配模式，那么 `-l` 或 `--list` 就是强制使用的。*

这里截图拿Arouter为例

![git tag -l](E:\fanjiaowork\文档\learngit\pic\git tag.png)
![git tag list](E:\fanjiaowork\文档\learngit\pic\git tag list.png)
##### 创建标签
- git tag v1.10.2 创建名为v1.10.2的轻量标签，图中最后一个
![image-20210416150141570](E:\fanjiaowork\文档\learngit\pic\git tag name.png)
  
>Git 支持两种标签：轻量标签（lightweight）与附注标签（annotated）。

>轻量标签很像一个不会改变的分支——它只是某个特定提交的引用。

>而附注标签是存储在 Git 数据库中的一个完整对象， 它们是可以被校验的，其中包含打标签者的名字、电子邮件地址、日期时间， 此外还有一个标签信息，并且可以使用 GNU Privacy Guard （GPG）签名并验证。 通常会建议创建附注标签，这样你可以拥有以上所有信息。但是如果你只是想用一个临时的标签， 或者因为某些原因不想要保存这些信息，那么也可以用轻量标签。
在 Git 中创建附注标签十分简单。 最简单的方式是当你在运行 tag 命令时指定 -a 选项：

-  git tag -a v1.10.1 -m "my version 1.10.1"
   -m 选项指定了一条将会存储在标签中的信息。 如果没有为附注标签指定一条信息，Git 会启动编辑器要求你输入信息,通过使用 `git show` 命令可以看到标签信息和与之对应的提交信息：

![image-20210416145728092](E:\fanjiaowork\文档\learngit\pic\git tag -a.png)
#####后期打标签
如果之前搞忘了，现在在打一个，也是可以的，我们要理解我们打标签就是在分支上基于某个commitid打，所以我们常常是在git commit 完了再打，既然之前搞忘了那一个我们就找到那一次的commitid。

![image-20210416150630703](E:\fanjiaowork\文档\learngit\pic\git tag before.png)

git tag -a v1.1.1 c46ca438475781400a4f3e620d5319a70c599ff7  -m "之前搞忘记了" 

![image-20210416152101307](E:\fanjiaowork\文档\learngit\pic\git tag -a 之前的打tag.png)

##### 共享标签
 共享的意思是，我在本地创建了标签推到远程仓库中，大家pull后都能看到了
 git push origin v1.1.1.1
 git push origin --tags
#### 删除标签
一般我们是删除本地的，然后再删除远程的

- git tag -d v1.1.1.1

```git
PS E:\androidworkspace\arouter> git tag -d v1.1.1.1
Deleted tag 'v1.1.1.1' (was 7073c97)
PS E:\androidworkspace\arouter>
```

注意上述命令并不会从任何远程仓库中移除这个标签，你必须用 `git push <remote> :refs/tags/<tagname>` 来更新你的远程仓库：

第一种变体是 `git push <remote> :refs/tags/<tagname>` ：

```console
$ git push origin :refs/tags/v1.1.1.1
```

上面这种操作的含义是，将冒号前面的空值推送到远程标签名，从而高效地删除它。

第二种更直观的删除远程标签的方式是：

```console
$ git push origin --delete <tagname>
```

#####  检出标签

这就回到了上面说过由某次的tag检出分支来新增功能

git  checkout -b newbranch v1.1.1

![image-20210416183618827](E:\fanjiaowork\文档\learngit\pic\git 从tagcheckout.png)

