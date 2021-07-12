> # 高阶知识
### 基本概念
> 你的本地仓库由 Git 维护的三棵「树」组成。第一个是你的工作目录（Working dir），它持有实际文件，即你所见的；第二个是缓存区（Stage or Index），它像个缓存区域，临时保存你的改动；第三个是提交历史（Commit history），包含的 HEAD 指针指向你最近一次 commit 的引用。

![](https://pic1.zhimg.com/80/v2-c46ec4a1d2742f0b36921f39844fd940_1440w.jpg)  

上面的四条命令在工作目录、stage 缓存（也叫做索引）和 commit 历史之间复制文件。
```
git add files 把工作目录中的文件加入 stage 缓存
git commit 把 stage 缓存生成一次 commit，并加入 commit 历史
git reset -- files 撤销最后一次 git add files，你也可以用 git reset 撤销所有 stage 缓存文件
git checkout -- files 把文件从 stage 缓存复制到工作目录，用来丢弃本地修改
```

### Merge

git merge 命令把不同分支合并起来。合并前，索引必须和当前提交相同。git merge other 用于将 other 分支上的提交合并到当前分支。

如果另一个分支是当前提交的祖父节点，那么合并命令将什么也不做。另一种情况是如果当前提交是另一个分支的祖父节点，就导致 fast-forward 合并，HEAD 指针只是简单的移动。

![](https://pic4.zhimg.com/80/v2-e487f1d1bd1bebf543aa1113a64d40d3_1440w.jpg)  

否则就是一次真正的合并。默认把当前提交（ed489 如下所示）和另一个提交（33104）以及他们的共同祖父节点（b325c）进行一次三方合并。结果是先保存当前目录和索引，然后和父节点 33104 一起做一次新提交。

![](https://pic2.zhimg.com/80/v2-2db6cd5e20b91afd3a4146c53175a509_1440w.jpg)
