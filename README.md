### 初始化仓库
    git init : 把当前目录变成Git可以管理的仓库

### git 提交操作流程

    git add <fileName> ;将文件修改添加到暂存区
    git commit -m <message> :将暂存区文件提交到当前分支

### 修改全局仓库名和邮箱 

    git config --global user.name ""(or email) name后面要加一个空格

### 查看git仓库状态 

    git status 

### git查看历史记录

    git log : 查看提交历史
    git reflog : 查看命令历史

### git 版本 回退

    git reset --hard HEAD^(回退到上一个版本)
    git reset --hard 039d (穿越到指定的版本)

### git 撤销修改

    git checkout -- file ：丢弃工作区的修改

1. 一种是文件自修改后还没有被放到暂存区，现在，撤销修改就回到和版本库一模一样的状态；
2. 一种是文件已经添加到暂存区后，又作了修改，现在，撤销修改就回到添加到暂存区后的状态。

### git 分支

1. 创建分支

    git branch <name>

2. 查看分支

    git branch

3. 切换分支

    git checkout <name> or git switch <name> (name = 分支名称)

4. 创建+切换分支

    git checkout -b <name> or git switch -c <name>
    
### git 存储

    git stash save "save message"  : 执行存储时，添加备注，方便查找，只有git stash 也要可以的，但查找时不方便识别。
    
    git stash list  ：查看stash了哪些存储  
    
    git stash pop ：命令恢复之前缓存的工作目录，将缓存堆栈中的对应stash删除，并将对应修改应用到当前的工作目录下,
    默认为第一个stash,即stash@{0}，如果要应用并删除其他stash，命令：git stash pop stash@{$num} ，比如应用并删除第二个：git stash pop stash@{1}  

    git stash apply :应用某个存储,但不会把存储从存储列表中删除，默认使用第一个存储,即stash@{0}，
    如果要使用其他个，git stash apply stash@{$num} ， 比如第二个：git stash apply stash@{1} 
    
    git stash clear ：删除所有缓存的stash
    
    git stash drop stash@{$num} ：丢弃stash@{$num}存储，从列表中删除这个存储
    
    git stash show ：显示做了哪些改动，默认show第一个存储,如果要显示其他存贮，后面加stash@{$num}，比如第二个 git stash show stash@{1}

    git stash show -p : 显示第一个存储的改动，如果想显示其他存存储，命令：git stash show  stash@{$num}  -p ，比如第二个：git stash show  stash@{1}  -p

