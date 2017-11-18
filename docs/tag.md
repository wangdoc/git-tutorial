# 标签

## 推送

标签必须单独推送。也就是说，`git push`命令默认不会推送标签，必须使用`--tags`参数。

```bash
$ git push && git push --tags
```

上面的命令先推送新的 commit，成功后再单独推送标签。

`--follow-tags`参数会使得 commit 以及与之相关的标签（注意，不是所有的标签）一起推送。

```bash
$ git push --follow-tags
```

Git 有一个对应于`--follow-tags`的配置项，默认是关闭的。如果将它打开，以后执行`git push`的时候，默认就会带上`--follow-tags`。

```
$ git config --global push.followTags true
```
