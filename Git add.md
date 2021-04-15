#### Git add

git add有诸多命令，下面我们一个一个介绍它的使用场景

1. ` git add <file> ` 添加文件到缓存区  eg: git add a.txt

2. `git add <files>/` 添加文件夹 eg: git add a/ 注意这个斜杠要加上，还有空文件夹是加不起的

3. ` git add <files>/file`添加一个文件夹下的一个文件 eg: git add a/a.txt 
4. `git add .` 将新文件和修改过的文件暂存到暂存区，不包括已删除的文件
5. `git add -u` (git add -update的缩写),仅提交已被add过的文件（即tracked file，该文件可能被修改或删除）,新文件是不会被提交的.
6. `git add -A`（git add -All的缩写），上面4,5功能的合集