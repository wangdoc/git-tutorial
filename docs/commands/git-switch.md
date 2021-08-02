# Git switch

`git switch`是 Git 2.23 版本新增的命名，用来切换分支，跟`git checkout`的作用类似，但有更好的语义。

```bash
$ git switch develop
```

上面命令切换到 develop 分支。

如果要切换到分离状态的（detached）的提交，需要使用`-d`参数。

```bash
$ git switch -d f8c540805b7e16753c65619ca3d7514178353f39
```

上面命令切换到指定提交。

`-c`参数（create）用于生成一个新的分支。

```bash
$ git switch -c new_branch
```

