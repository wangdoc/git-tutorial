# git log

`git log`命令按照提交时间从最晚到最早的顺序，列出所有 commit。

```bash
# 列出当前分支的版本历史
$ git log

# 列出某个文件的版本历史，包括文件改名
$ git log --follow [file]
```

查看远程分支的变动情况。

```bash
$ git log remote/branch
```

查找log，即搜索commit信息。

```bash
$ git log --author=Andy
$ git log -i --grep="Something in the message"
```

上面代码中，`-i`参数表示搜索时忽略大小写。

查看某个范围内的commit

```bash
$ git log origin/master..new
# [old]..[new] - everything you haven't pushed yet
```

美化输出。

```bash
git log --graph --decorate --pretty=oneline --abbrev-commit
```

- --graph commit之间将展示连线
- --decorate 显示commit里面的分支
- --pretty=oneline 只显示commit信息的标题
- --abbrev-commit 只显示commit SHA1的前7位

## 命令行参数

### --oneline

`git log`默认输出每个 commit 的详细信息，为了节省空间，`--oneline`参数让输出时，每个 commit 只占用一行。

```bash
$ git log --oneline --decorate
ccc3333 (HEAD, my-feature-branch) A third commit
bbb2222 A second commit
aaa1111 A first commit
9999999 (master) Old stuff on master
```
