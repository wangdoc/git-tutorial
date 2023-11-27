# git branch

`git branch`是分支操作命令。

```bash
# 列出所有本地分支
$ git branch

# 列出所有本地分支和远程分支
$ git branch -a
```

（1）新建一个分支

直接在`git branch`后面跟上分支名，就表示新建该分支。

```bash
$ git branch develop
```

新建一个分支，指向当前 commit。本质是在`refs/heads/`目录中生成一个文件，文件名为分支名，内容为当前 commit 的哈希值。

注意，创建后，还是停留在原来分支，需要用`git checkout`切换到新建分支。

```bash
$ git checkout develop
```

使用`-b`参数，可以新建的同时，切换到新分支。

```bash
$ git checkout -b NewBranch MyBranch
```

（2）删除分支

`-d`参数用来删除一个分支，前提是该分支没有未合并的变动。

```bash
$ git branch -d <分支名>
```

强制删除一个分支，不管有没有未合并变化。

```bash
$ git branch -D <分支名>
```

（3）分支改名

```bash
$ git checkout -b twitter-experiment feature132
$ git branch -d feature132
```

另一种写法

```bash
# 为当前分支改名
$ git branch -m twitter-experiment

# 为指定分支改名
$ git branch -m feature132 twitter-experiment

# 如果有重名分支，强制改名
$ git branch -m feature132 twitter-experiment
```

（4）查看 merge 情况

```bash
# Shows branches that are all merged in to your current branch
$ git branch --merged

# Shows branches that are not merged in to your current branch
$ git branch --no-merged
```

## 命令行参数

### -d

`-d`参数用于删除一个指定分支。

```bash
$ git branch -d <branchname>
```

### -m，-M

`-m`或`-M`用于分支改名。

```bash
$ git branch (-m | -M) <oldbranch> <newbranch>
```

上面命令将`oldbranch`改名为`newbranch`。

如果省略`oldbracn`，则将当前分支改名为`newbranch`。

```bash
$ git branch (-m | -M) <newbranch>
```

如果`newbranch`已经存在，则必须使用`-M`参数，进行强制改名。

