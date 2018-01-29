# git commit

`git commit`命令用于将暂存区中的变化提交到仓库区。

`-m`参数用于指定 commit 信息，是必需的。如果省略`-m`参数，`git commit`会自动打开文本编辑器，要求输入。

```bash
$ git commit -m "message"
```

`git commit`命令可以跳过暂存区，直接将文件从工作区提交到仓库区。

```bash
$ git commit <filename>  -m "message"
```

上面命令会将工作区中指定文件的变化，先添加到暂存区，然后再将暂存区提交到仓库区。

## 命令行参数

### -a

`-a`参数用于先将所有工作区的变动文件，提交到暂存区，再运行`git commit`。用了`-a`参数，就不用执行`git add .`命令了。

```bash
$ git commit -am "message"
```

如果没有指定提交说明，运行下面的命令会直接打开默认的文本编辑器，让用户撰写提交说明。

```bash
$ git commit -a
```

### --allow-empty

`--allow-empty`参数用于没有提交信息的 commit。

```bash
$ git commit --allow-empty
```

### --amend

`--amend`参数用于撤销上一次 commit，然后生成一个新的 commit。

```bash
$ git commit --amend - m "new commit message"
```

### --fixup

`--fixup`参数的含义是，当前添加的 commit 是以前某一个 commit 的修正。以后执行互动式的`git rebase`的时候，这两个 commit 将会合并成一个。

```bash
$ git commit --fixup <commit>
```

执行上面的命令，提交说明将自动生成，即在目标 commit 的提交说明的最前面，添加“fixup! ”这个词。

### -m

`-m`参数用于添加提交说明。

```bash
$ git commit -m "message"
```

### --squash

`--squash`参数的作用与`--fixup`类似，表示当前添加的 commit 应该与以前某一个 commit 合并成一个，以后执行互动式的`git rebase`的时候，这两个 commit 将会合并成一个。

```bash
$ git commit --squash <commit>
```
