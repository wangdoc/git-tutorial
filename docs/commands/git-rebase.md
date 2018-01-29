# git rebase

git rebase 将当前分支移植到指定分支或指定commit之上。

```bash
$ git rebase -i <commit>
```

互动的rebase。

```bash
$ git rebase -i master~3
```

## 命令行参数

### --autosquash

`--autosquash`参数用于互动模式，必须与`-i`参数配合使用。它会使得以前通过`git commit --fixup`和`git commit --squash`提交的 commit，按照指定的顺序排列（实质是选择提交说明以以`fixup!`或`squash!`开头的 commit），即`--fixup`的 commit 直接排在它所对应的 commit 的后面。

```bash
$ git rebase --interactive --autosquash <branch>
```

### --continue

`--continue`参数用于解决冲突以后，继续执行 rebase。

```bash
$ git rebase --continue
```

### -i，--interactive

`-i`参数会打开互动模式，让用户选择定制`rebase`的行为。

```bash
$ git rebase -i develop
```

## 参考链接

- [Auto-squashing Git Commits](https://robots.thoughtbot.com/autosquashing-git-commits), by George Brocklehurst

