1、将HEAD移到需要更改的commit上

`git rebase -i xxx_id`

2、找到需要更改的commit, 将行首的pick改成edit, 保存

3、更改文件，并添加到暂存区

`git add .`

4、追加改动到第一步中指定的commit上 

`git commit –amend`

5、移动HEAD到最新的commit处

`git rebase –continue`
