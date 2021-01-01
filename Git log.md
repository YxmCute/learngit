- 查看首页删除文件的历史记录`git log --diff-filter=D --summary | grep delete`

  ![删除文件历史记录](pic/gitlog.png)

- git log --all --  filepath 查看该文件的提交记录(显示已删除文件的差异)

  ![文件的提交记录](pic/gitlog1.png)

- git show commitid --filepath 根据提交id显示文件

  ![git show commitid](pic/gitlog2.png)

- git show commitid --filepath > restorefilename

  ![恢复文件](pic/gitlog4.png)