浅谈Git  
==========
> - Git 完整命令手册地址：http://git-scm.com/docs  
> - PDF 版命令手册：https://www.runoob.com/manual/github-git-cheat-sheet.pdf
***
- Git 是一个开源的分布式版本控制系统，用于敏捷高效地处理任何或小或大的项目。
- Git 是 Linus Torvalds 为了帮助管理 Linux 内核开发而开发的一个开放源码的版本控制软件。
- Git 与常用的版本控制工具 CVS, Subversion 等不同，它采用了分布式版本库的方式，不必服务器端软件支持。
***
1. Git 与 SVN 区别
    - Git 不仅仅是个版本控制系统，它也是个内容管理系统(CMS)，工作管理系统等。
    - 如果你是一个具有使用 SVN 背景的人，你需要做一定的思想转换，来适应 Git 提供的一些概念和特征。
    - Git 与 SVN 区别点：
        > - 1、Git 是分布式的，SVN 不是：这是 Git 和其它非分布式的版本控制系统，例如 SVN，CVS 等，最核心的区别。
        > - 2、Git 把内容按元数据方式存储，而 SVN 是按文件：所有的资源控制系统都是把文件的元信息隐藏在一个类似 .svn、.cvs 等的文件夹里。
        > - 3、Git 分支和 SVN 的分支不同：分支在 SVN 中一点都不特别，其实它就是版本库中的另外一个目录。
        > - 4、Git 没有一个全局的版本号，而 SVN 有：目前为止这是跟 SVN 相比 Git 缺少的最大的一个特征。
        > - 5、Git 的内容完整性要优于 SVN：Git 的内容存储使用的是 SHA-1 哈希算法。这能确保代码内容的完整性，确保在遇到磁盘故障和网络问题时降低对版本库的破坏。
        > ![git相关](img\git1.jpg) 
***
2. Git安装配置
    - 在这里我就不详细说明安装配置了呢，git安装配置可参考：https://www.runoob.com/git/git-install-setup.html
    - Git 各平台安装包下载地址为：http://git-scm.com/downloads
***
3.  Git工作流程
    > - 一般工作流程如下：
    > > - 在克隆的资源上添加或修改文件。
    > > - 如果其他人修改了，你可以更新资源。
    > > - 在提交前查看修改。
    > > - 提交修改。
    > > - 在修改完成后，如果发现错误，可以撤回提交并再次修改并提交。  

    >下图展示了 Git 的工作流程：：
    > > ![git相关](img\git2.png) 
***
4. Git 工作区、暂存区和版本库
    - 工作区：就是你在电脑里能看到的目录。
    - 暂存区：英文叫stage, 或index。一般存放在 ".git目录下" 下的index文件（.git/index）中，所以我们把暂存区有时也叫作索引（index）。
    - 版本库：工作区有一个隐藏目录.git，这个不算工作区，而是Git的版本库。
    >下面这个图展示了工作区、版本库中的暂存区和版本库之间的关系：
    > > ![git相关](img\git3.jpg) 
    > > 图中左侧为工作区，右侧为版本库。在版本库中标记为 "index" 的区域是暂存区（stage, index），标记为 "master" 的是 master 分支所代表的目录树。  
    > > 图中我们可以看出此时 "HEAD" 实际是指向 master 分支的一个"游标"。所以图示的命令中出现 HEAD 的地方可以用 master 来替换。  
    > > 图中的 objects 标识的区域为 Git 的对象库，实际位于 ".git/objects" 目录下，里面包含了创建的各种对象及内容。  
    > > 当对工作区修改（或新增）的文件执行 "git add" 命令时，暂存区的目录树被更新，同时工作区修改（或新增）的文件内容被写入到对象库中的一个新的对象中，而该对象的ID被记录在暂存区的文件索引中。  
    > > 当执行提交操作（git commit）时，暂存区的目录树写到版本库（对象库）中，master 分支会做相应的更新。即 master 指向的目录树就是提交时暂存区的目录树。  
    > > 当执行 "git reset HEAD" 命令时，暂存区的目录树会被重写，被 master 分支指向的目录树所替换，但是工作区不受影响。  
    > > 当执行 "git rm --cached `<file>`" 命令时，会直接从暂存区删除文件，工作区则不做出改变。  
    > > 当执行 "git checkout ." 或者 "git checkout -- `<file>`" 命令时，会用暂存区全部或指定的文件替换工作区的文件。这个操作很危险，会清除工作区中未添加到暂存区的改动。  
    > > 当执行 "git checkout HEAD ." 或者 "git checkout HEAD `<file>`" 命令时，会用 HEAD 指向的 master 分支中的全部或者部分文件替换暂存区和以及工作区中的文件。这个命令也是极具危险性的，因为不但会清除工作区中未提交的改动，也会清除暂存区中未提交的改动。
***
5. Git 创建仓库
    - 这里就不在这里详细说明怎么创建仓库；可以利用指令（`git init、git init newrepo、$ git add *.c、$ git add README、$ git commit -m '初始化项目版本'`）创建，也可以通过github官网界面操作创建;
***
6. Git 基本操作
    - 获取与创建项目命令
        > - `git init` 
        > > 用 git init 在目录中创建新的 Git 仓库。 你可以在任何时候、任何目录中这么做，完全是本地化的。  
        > > 在目录中执行 git init，就可以创建一个 Git 仓库了。
        > - `git clone`
        > > 使用 git clone 拷贝一个 Git 仓库到本地，让自己能够查看该项目，或者进行修改。
        > > 如果你需要与他人合作一个项目，或者想要复制一个项目，看看代码，你就可以克隆那个项目。 执行命令：
    - 基本快照
        - Git 的工作就是创建和保存你的项目的快照及与之后的快照进行对比。本章将对有关创建与提交你的项目的快照的命令作介绍。
        > - `git add` 
        > > git add 命令可将该文件添加到缓存
        > - `git status` 
        > > git status 以查看在你上次提交之后是否有修改。  
        > > 使用该命令的时候加了 -s 参数，以获得简短的结果输出。如果没加该参数会详细输出内容：
        > - `git diff` 
        > > 执行 git diff 来查看执行 git status 的结果的详细信息。  
        > > git diff 命令显示已写入缓存与已修改但尚未写入缓存的改动的区别。git diff 有两个主要的应用场景。
        > > - 尚未缓存的改动：git diff
        > > - 查看已缓存的改动： git diff --cached
        > > - 查看已缓存的与未缓存的所有改动：git diff HEAD
        > > - 显示摘要而非整个 diff：git diff --stat
        > - `git commit`
        > > 使用 git add 命令将想要快照的内容写入缓存区， 而执行 git commit 将缓存区内容添加到仓库中。
        > > Git 为你的每一个提交都记录你的名字与电子邮箱地址，所以第一步需要配置用户名和邮箱地址。
        ```javascript
        $ git config --global user.name 'ruxiang.wang'
        $ git config --global user.email ruxiang.wang@tcl.com
        ```
        > - `git reset HEAD`
        > > git reset HEAD 命令用于取消已缓存的内容。
        > - `git rm`
        > > 如果只是简单地从工作目录中手工删除文件，运行 git status 时就会在 Changes not staged for commit 的提示。
        > > 要从 Git 中移除某个文件，就必须要从已跟踪文件清单中移除，然后提交。可以用以下命令完成此项工作
        > - `git mv`
        > > git mv 命令用于移动或重命名一个文件、目录、软连接。 
***
7. Git 分支管理
    - 几乎每一种版本控制系统都以某种形式支持分支。使用分支意味着你可以从开发主线上分离开来，然后在不影响主线的同时继续工作。
    - 有人把 Git 的分支模型称为必杀技特性，而正是因为它，将 Git 从版本控制系统家族里区分出来。
    > - 创建分支命令：
    > > `git branch (branchname)`
    > - 切换分支命令:
    > > `git checkout (branchname)`
    - 当你切换分支的时候，Git 会用该分支的最后提交的快照替换你的工作目录的内容， 所以多个分支不需要多个目录。
    > - 合并分支命令:
    > > `git merge `
    - 你可以多次合并到统一分支， 也可以选择在合并之后直接删除被并入的分支。
    - 开始前我们先创建一个测试目录：
        ```javascript
        $ mkdir gitdemo
        $ cd gitdemo/
        $ git init
        Initialized empty Git repository...
        $ touch README
        $ git add README
        $ git commit -m '第一次版本提交'
        [master (root-commit) 3b58100] 第一次版本提交
        1 file changed, 0 insertions(+), 0 deletions(-)
        create mode 100644 README
        ```
    > - 列出分支基本命令：
    > > `git branch`
    > - 没有参数时，git branch 会列出你在本地的分支。
    ```javascript
        $ git branch 
        * master
    ``` 
    > > 此例的意思就是，我们有一个叫做 master 的分支，并且该分支是当前分支。  
    > > 当你执行 git init 的时候，默认情况下 Git 就会为你创建 master 分支。  
    > > 如果我们要手动创建一个分支。执行 git branch (branchname) 即可。
    ```javascript
        $ git branch testing
        $ git branch
        * master
        testing
    ``` 
    > > 现在我们可以看到，有了一个新分支 testing。  
    > > 当你以此方式在上次提交更新之后创建了新分支，如果后来又有更新提交， 然后又切换到了 testing 分支，Git 将还原你的工作目录到你创建分支时候的样子。
    - 接下来我们将演示如何切换分支，我们用 git checkout (branch) 切换到我们要修改的分支。
    ```javascript
        $ ls
        README
        $ echo 'runoob.com' > test.txt
        $ git add .
        $ git commit -m 'add test.txt'
        [master 3e92c19] add test.txt
        1 file changed, 1 insertion(+)
        create mode 100644 test.txt
        $ ls
        README        test.txt
        $ git checkout testing
        Switched to branch 'testing'
        $ ls
        README
    ``` 
    - 我们也可以使用 git checkout -b (branchname) 命令来创建新分支并立即切换到该分支下，从而在该分支中操作。
    ```javascript
        $ git checkout -b newtest
        Switched to a new branch 'newtest'
        $ git rm test.txt 
        rm 'test.txt'
        $ ls
        README
        $ touch runoob.php
        $ git add .
        $ git commit -am 'removed test.txt、add runoob.php'
        [newtest c1501a2] removed test.txt、add runoob.php
        2 files changed, 1 deletion(-)
        create mode 100644 runoob.php
        delete mode 100644 test.txt
        $ ls
        README        runoob.php
        $ git checkout master
        Switched to branch 'master'
        $ ls
        README        test.txt
    ```
    > - 删除分支命令：
    > > `git branch -d (branchname)`
    > - 分支合并：
    > > `git merge`
    ```javascript
        $ git branch
        * master
        newtest
        $ ls
        README        test.txt
        $ git merge newtest
        Updating 3e92c19..c1501a2
        Fast-forward
        runoob.php | 0
        test.txt   | 1 -
        2 files changed, 1 deletion(-)
        create mode 100644 runoob.php
        delete mode 100644 test.txt
        $ ls
        README        runoob.php
    ```
    > - 合并冲突：合并并不仅仅是简单的文件添加、移除的操作，Git 也会合并修改。(需要手动修改解决冲突)，具体操作可上网百度，哈哈哈哈
    ```javascript
        $ git branch
        * master
        $ cat runoob.php
    ```
***
8. Git 查看提交历史
    - 在使用 Git 提交了若干更新之后，又或者克隆了某个项目，想回顾下提交历史，我们可以使用 git log 命令查看。
    > - 使用 git log 命令列出历史提交记录如下：
    ```javascript
        $ git log
        commit d5e9fc2c811e0ca2b2d28506ef7dc14171a207d9 (HEAD -> master)
        Merge: c68142b 7774248
        Author: runoob <test@runoob.com>
        Date:   Fri May 3 15:55:58 2019 +0800

            Merge branch 'change_site'

        commit c68142b562c260c3071754623b08e2657b4c6d5b
        Author: runoob <test@runoob.com>
        Date:   Fri May 3 15:52:12 2019 +0800

            修改代码

        commit 777424832e714cf65d3be79b50a4717aea51ab69 (change_site)
        Author: runoob <test@runoob.com>
        Date:   Fri May 3 15:49:26 2019 +0800

            changed the runoob.php

        commit c1501a244676ff55e7cccac1ecac0e18cbf6cb00
        Author: runoob <test@runoob.com>
        Date:   Fri May 3 15:35:32 2019 +0800
    ```
    > - 我们可以用 --oneline 选项来查看历史记录的简洁的版本。
    ```javascript
        $ git log --oneline
        $ git log --oneline
        d5e9fc2 (HEAD -> master) Merge branch 'change_site'
        c68142b 修改代码
        7774248 (change_site) changed the runoob.php
        c1501a2 removed test.txt、add runoob.php
        3e92c19 add test.txt
        3b58100 第一次版本提交
    ```
    > - 我们还可以用 --graph 选项，查看历史中什么时候出现了分支、合并。以下为相同的命令，开启了拓扑图选项：
    ```javascript
        *   d5e9fc2 (HEAD -> master) Merge branch 'change_site'
        |\  
        | * 7774248 (change_site) changed the runoob.php
        * | c68142b 修改代码
        |/  
        * c1501a2 removed test.txt、add runoob.php
        * 3e92c19 add test.txt
        * 3b58100 第一次版本提交
    ```
    > - 你也可以用 --reverse 参数来逆向显示所有日志。
    ```javascript
        $ git log --reverse --oneline
        3b58100 第一次版本提交
        3e92c19 add test.txt
        c1501a2 removed test.txt、add runoob.php
        7774248 (change_site) changed the runoob.php
        c68142b 修改代码
        d5e9fc2 (HEAD -> master) Merge branch 'change_site'
    ```
    > - 如果只想查找指定用户的提交日志可以使用命令：git log --author , 例如，比方说我们要找 Git 源码中 Linus 提交的部分：
    ```javascript
        $ git log --author=Linus --oneline -5
        81b50f3 Move 'builtin-*' into a 'builtin/' subdirectory
        3bb7256 make "index-pack" a built-in
        377d027 make "git pack-redundant" a built-in
        b532581 make "git unpack-file" a built-in
        112dd51 make "mktag" a built-in
    ```
    > - 如果你要指定日期，可以执行几个选项：--since 和 --before，但是你也可以用 --until 和 --after。
    ```javascript
        $ git log --oneline --before={3.weeks.ago} --after={2010-04-18} --no-merges
        5469e2d Git 1.7.1-rc2
        d43427d Documentation/remote-helpers: Fix typos and improve language
        272a36b Fixup: Second argument may be any arbitrary string
        b6c8d2d Documentation/remote-helpers: Add invocation section
        5ce4f4e Documentation/urls: Rewrite to accomodate transport::address
        00b84e9 Documentation/remote-helpers: Rewrite description
        03aa87e Documentation: Describe other situations where -z affects git diff
        77bc694 rebase-interactive: silence warning when no commits rewritten
        636db2c t3301: add tests to use --format="%N"
    ```
    - 更多 git log 命令可查看：http://git-scm.com/docs/git-log
***
9. Git 标签
    - 如果你达到一个重要的阶段，并希望永远记住那个特别的提交快照，你可以使用 git tag 给它打上标签。
    - 比如说，我们想为我们的 runoob 项目发布一个"1.0"版本。 我们可以用 git tag -a v1.0 命令给最新一次提交打上（HEAD）"v1.0"的标签。
    - -a 选项意为"创建一个带注解的标签"。 不用 -a 选项也可以执行的，但它不会记录这标签是啥时候打的，谁打的，也不会让你添加个标签的注解。 我推荐一直创建带注解的标签。
    ```javascript
        $ git tag -a v1.0 
    ```
***
10. Git 远程仓库(Github)
***
11. Git Gitee
    - 大家都知道国内访问 Github 速度比较慢，很影响我们的使用。
    - 如果你希望体验到 Git 飞一般的速度，可以使用国内的 Git 托管服务——Gitee（gitee.com）。
    - Gitee 提供免费的 Git 仓库，还集成了代码质量检测、项目演示等功能。对于团队协作开发，Gitee 还提供了`项目管理、代码托管、文档管理的服务，5 人以下小团队免费`。
    - 接下来我们学习一下如何使用 Gitee。
    - 由于我们的本地 Git 仓库和 Gitee 仓库之间的传输是通过SSH加密的，所以我们需要配置验证信息。
    - 具体使用可参考：https://www.runoob.com/git/git-gitee.html
***
12. Git 服务器搭建
    - 我们远程仓库使用了 Github，Github 公开的项目是免费的，2019 年开始 Github 私有存储库也可以无限制使用。
    - 这当然我们也可以自己搭建一台 Git 服务器作为私有仓库使用。
    - 具体使用可参考：https://www.runoob.com/git/git-server.html