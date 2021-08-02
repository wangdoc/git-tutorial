# git restore

`git restore`是 Git 2.23 版本新增的命令，用于恢复文件，可以替代`git checkout`的部分功能。

```bash
$ git restore -- test.txt
```

上面命令将从暂存区恢复`test.txt`文件，该文件的本地修改将全部丢失。

