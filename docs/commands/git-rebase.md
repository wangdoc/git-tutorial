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

### -i，--interactive

`-i`参数会打开互动模式，让用户选择定制`rebase`的行为。

```bash
$ git rebase -i develop
```

###
