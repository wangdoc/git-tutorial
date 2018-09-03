# 内部实现

## .git 目录

版本管理的所有信息，保存在项目的`.git`目录之中。如果没有这个目录，Git 就会认为这个仓库没有建立版本管理，必须进行初始化。`git init`命令的主要作用，就是建立`.git`目录。

`.git/config`文件保存仓库的设置。

`.git/HEAD`文件保存当前工作分支的引用。

`.git/hooks`目录保存各种事件挂钩的脚本。

`.git/objects`目录保存文件的内容，格式是二进制`blob`。

## 哈希签名

每次提交的时候，每个文件、每个树节点（目录）和提交本身，都会生成一个40个字符长的 SHA-1 哈希。

哈希作为文件名，文件本身保留在`.git/objects`目录之中。

## git add 命令

`git add`会将变动的文件写入`.git/objects`目录。它内部调用的是`git hash-object`命令,该命令会计算 SHA-1 哈希，并将 blob 文件放入`.git/objects`目录。

```bash
$ git hash-object -w myfile.txt
```

`git cat-file`命令可以查看 blob 格式对应的原始文件内容。

```bash
$ git cat-file -p e69de29bb2d1d6434b8b29ae775ad8c2e48c5391
```

## git commit 命令

`git commit`命令用于有变动的、并已提交到`.git/objects`的文件写入历史。

`git write-tree`为当前仓库创建树节点。

```bash
$ git write-tree
```

`git commit-tree`命令将指定的树节点写入历史。

```bash
$ echo“first commit”| git commit-tree \ 6e9432aeedbad83fbffb7f8aae4a5d1ab50b7fdf
```
