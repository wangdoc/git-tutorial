# 分支

分支是 Git 最重要的概念之一，也是最常用的操作之一。几乎所有 Git 操作流程都离不开分支。

`git branch`命令可以列出本地的所有分支。

```bash
$ git branch
```

创建一个名为`MyBranch`的新分支，但是依然停留在当前分支。

```bash
$ git branch MyBranch
```

在远程主机`origin`上创建一个`MyBranch`的分支，并与本地的同名分支建立追踪关系。

```bash
$ git push -u origin MyBranch
```

将当前分支改名为`MyBranch`。

```bash
$ git branch -m MyBranch
```

删除`MyBranch`分支，前提是该分支没有未合并的变动。

```bash
$ git branch -d MyBranch
```

强制删除`MyBranch`分支，不管有没有未合并变化。

```bash
$ git branch -D MyBranch
```

切换到`MyBranch`分支，当前的工作区会变为`MyBranch`分支的内容。

```bash
$ git checkout MyBranch
```

基于`MyBranch`分支创建一个新的`NewBranch`分支，新的`NewBranch`分支将成为当前的工作区。

```bash
$ git checkout -b NewBranch MyBranch
```
