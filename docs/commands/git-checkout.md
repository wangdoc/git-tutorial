# git checkout

`git checkout`命令有多种用途。

（1）用来切换分支。

```bash
$ git checkout
```

上面命令表示回到先前所在的分支。

```bash
$ git checkout develop
```

上面命令表示切换到`develop`分支。

（2）切换到指定快照（commit）

```bash
$ git checkout <commitID>
```

（3）将工作区指定的文件恢复到上次提交的状态。

```bash
$ git checkout -- <filename>
```

上面命令将指定文件从暂存区复制到工作区，同时丢弃工作区对该文件的修改。所以，使用的时候必须小心，它会丢失对当前文件的修改，回到上一次保存到暂存区的状态。

```bash
$ git checkout HEAD~ -- <filename>
```

它还可以从其他分支或提交恢复指定文件，上例是`HEAD~`，这会同时改变暂存区和工作区。

`-p`参数表示进入交互模式，手动选择恢复哪些文件。

```bash
$ git checkout -p
```

（4）切换到某个tag

```bash
$ git checkout tags/1.1.4
# 或者
$ git checkout 1.1.4
```

上面第二种用法的前提是，本地不能有叫做1.1.4的分支。

（5）生成新的分支。

`-b`参数用于生成一个新的分支，并切换到该分支。

```bash
$ git checkout -b new_branch
```
