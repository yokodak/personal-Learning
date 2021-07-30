# git学习笔记

> 📅创建时间：2021-03-09 Tuesday 15：08
>
> 📍深圳奥哲
>
> ⌚ 2021年7月13日 11点27分  Tuesday 重写
>
> 📄：📌/🔗表示该段引用自外部链接

## 基本介绍

这里要用通俗易懂的语句描述git的作用

📌git是一种源码管理系统（source code management，缩写为SCM）。它对当前文件提供版本管理功能，核心思想是对当前文件建立一个**对象数据库**（object database），将历史版本信息存放在这个数据库中。[🔗来源](https://www.bookstack.cn/read/git-tutorial/docs-basic.md)

git快的原因

在 Git 中的绝大多数操作都只需要访问本地文件和资源，一般不需要来自网络上其它计算机的信息。因为你在本地磁盘上就有项目的完整历史，所以大部分操作看起来瞬间完成。

📍 git采用分布式存储,每台电脑都可以从服务器克隆完整的代码仓库( **[github](https://github.com/)** 为开源项目免费提供代码托管),这样代码仓库能分布在不同的电脑上,即使服务器的代码仓库损坏,也能从其他电脑获取代码

## 基础使用

### 版本管理

- “ [] ”表示可选选项
- git会对用户进行操作指引,有对应需要则按照提示操作即可，如👇

> <img src="https://gitee.com/yaorunhua/runbed/raw/master/img/LX_work/image-20210713191828548.png" alt="image-20210713191828548" style="zoom: 150%;" />

#### 1.创建版本库

```bash
git init #在本地文件目录(工作区)下执行该命令,创建本地版本库
```

创建后文件目录下会出现一个**.git文件夹**，即git的版本库，.git文件夹下的objects文件夹即git的**对象数据库**

.git文件夹下的index文件通常被称为**暂存区**

创建版本库后，我们就可以借助git来管理项目中的文件了，不过，一般我们会有一些文件不需要纳入git的管理（通常都是些自动生成的文件，比如日志文件，或者编译过程中创建的临时文件等。）

在这种情况下，我们可以创建一个名为 `.gitignore` 的文件，列出要忽略的文件的模式。 [🔗pro-git](https://git-scm.com/book/zh/v2/Git-%E5%9F%BA%E7%A1%80-%E8%AE%B0%E5%BD%95%E6%AF%8F%E6%AC%A1%E6%9B%B4%E6%96%B0%E5%88%B0%E4%BB%93%E5%BA%93)

关于 `.gitignore` 的格式规范可以查看上面的链接👆

GitHub 有一个十分详细的针对数十种项目及语言的 `.gitignore` 文件列表， 你可以在 https://github.com/github/gitignore 找到它。

#### **2.添加文件到暂存区**

电脑上的目录即**工作区**(working Directory) ，工作区下的.git文件夹是git的**版本库**(Repository)，版本库中有**暂存区**（staging Area）即`.git/index`，在工作区新建一个文件`readme.txt` , 之后使用命令

```bash
git add readme.txt  #将readme.txt文件添加到暂存区
```

> 📌The staging area is a **file**, generally contained in your Git directory, that stores **information** about what will go **into your next commit.**  [链接🔗](https://git-scm.com/book/en/v2/Getting-Started-What-is-Git%3F)
>
> 暂存区通常是在.git目录下的一个文件(.git/index),保存了下次将要提交的文件信息，使用命令
>
> `git ls-files --stage`  可以查看暂存区内容， 如：👇
>
> ```bash
> git ls-files --stage 
> //输出
> $ git ls-files --stage
> 100644 c4f182ebec79c1bd1eddf7e2f336ed297f79820f 0       readme.txt
> #可以看到，暂存区里 记录了文件的内容 所对应的数据对象，以及文件的路径 
> #100644表示普通文件
> ```



![img](https://gitee.com/yaorunhua/runbed/raw/master/img/LX_work/areas.png)

图片来源  [链接🔗](https://git-scm.com/book/en/v2/Getting-Started-What-is-Git%3F)

📍使用 `git commit` 命令可以**一次性**提交**所有暂存区的文件**到版本库

> Question：为何需要暂存区？为什么不直接将文件提交到版本库？却还要先进行add操作?
>
> 为了有选择性的提交文件到版本库。 吗🧐
>
> 如果没有暂存区，要么一次性提交就会提交所有工作区的文件，要么每次都需要找到要提交的文件，一个个添加到commit命令后，过于繁琐。现在有暂存区了，只需要将要提交的文件存到暂存区，然后`git commit` 一次性提交即可

#### **3.查看信息**

- **查看状态报告**

```bash
git status #查看当前版本库的文件状态，及所在分支
#文件状态：
		#1.Untracked 未追踪的文件（未add到暂存区的文件）
		#2.staged (new file) 已经追踪（已经add到暂存区）但未提交的文件
		#3.modified 已经追踪,并修改过,修改后未进行提交
		#4.commited 已经成功提交,存储到本地版本库中的文件
#如：
git status
On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   Note/Tools/git.md

no changes added to commit (use "git add" and/or "git commit -a")

```

还可以通过`git status -s `命令以更简洁的形式输出状态报告,文件名前有两栏，**左**栏表示**暂存**区的状态，**右**栏表示**工作**区的状态，`A` 表示该文件新添加到暂存区， `M` 表示该文件已修改，`??`表示新添加的未跟踪文件。[🔗](https://git-scm.com/book/zh/v2/Git-%E5%9F%BA%E7%A1%80-%E8%AE%B0%E5%BD%95%E6%AF%8F%E6%AC%A1%E6%9B%B4%E6%96%B0%E5%88%B0%E4%BB%93%E5%BA%93)

 ```bash
git status -s
 M README
MM Rakefile
A  lib/git.rb
M  lib/simplegit.rb
?? LICENSE.txt
 ```

上面的状态报告显示： `README` 文件在工作区已修改但尚未暂存，而 `lib/simplegit.rb` 文件已修改且已暂存。 `Rakefile` 文件已修改，暂存后又作了修改，因此该文件的修改中既有已暂存的部分，又有未暂存的部分。

- **查看修改** 

修改文件后 , 要查看文件更新了哪些部分，直接输入 `git diff` 如：

```bash
git diff 
#输出
diff --git a/test.txt b/test.txt #这一行表示对比两个文件的区别，a表示修改前，b表示修改后
index 4309ccc..6c77a27 100644    #4309ccc..6c77a27分别表示两个文件的SHA-1值 100644表示普通文件
--- a/test.txt   # --- 表示修改前
+++ b/test.txt   # +++ 表示修改后
@@ -1 +1,2 @@    # -1 表示修改前的文件只有一行， +1，2 表示修改后文件从第一行到第二行
 hello,git       #这一行是原文件内容
+我是已跟踪的文件，现在修改后还没有暂存  #这一行是修改后的内容（默认设置下绿色显示）
```

如果要查看已暂存文件与最新一次提交的差异，可以加上参数`--staged `或 `--cached` 

```bash
git diff --staged #显示暂存文件和最新一次提交的差异
```



#### 4.撤销修改

```bash
git restore file 
#或
git checkout -- file #注意命令有"--" 不然 git checkout命令会执行切换分支
```

丢弃工作区的修改,让文件回到最近一次 `git commit `(下 1  )或  `git add`  (下 2 )的状态

1. 如果文件修改后,还未添加到暂存区,撤销则恢复到版本库的状态

2. 文件已经添加到暂存区后再修改,执行撤销命令则恢复到添加到暂存区后的状态

如果文件已经被修改且添加到暂存区了,想要将文件重新放回工作区(撤销暂存)👇

之后想要放弃修改,按照上面👆的步骤1操作即可

```bash
git restore --staged <file>
#或者
git reset HEAD <file>
```



#### **5.提交文件到仓库**

```bash
git add [fileName1][fileName2][..] #将文件添加到暂存区
git commit [fileName1] [...] - m "message" #提交文件到本地版本库
git commit -m "message"#一次性提交所有暂存区的文件到版本库
```

📍 `git commit` 命令**只提交暂存区的内容** , 所以为了避免文件的修改丢失，每次修改后，如果需要更新到版本库，就要进行暂存操作

👉第一次修改 -> `git add` -> 第二次修改 -> `git add` -> `git commit`

如果觉得每次修改后都要`git add` 比较麻烦,可以使用 `git commit -a `命令,跳过暂存区,直接提交**已经跟踪过**的文件.(未跟踪的文件不会被提交)

虽然比较方便, 不过也需要注意,使用 `git commit -a `命令,那些修改了但是还不想提交的文件也会被无差别地提交到版本库.

在安装`git` 时，有一个设置 `git` 编辑器的步骤，当提交命令 `git commit ` 没有带上参数 `-m ` 来输入提交说明时，`git ` 会启动你设置的编辑器，要求你输入提交说明

>可以使用 `git config --global core.editor` 命令设置你喜欢的编辑器。

现在我们已经熟悉 `git` 的基本操作流程了，借助`git add `, `git commit` ，`git restore` ,`git status` 等命令，已经能实现基本的版本控制啦，恭喜🎉（这段应该写在切换版本后吧？包括下面段）

**💎git的基本操作流程**

> 📌 The basic Git workflow goes something like this:
>
> 1. You modify files in your working tree.
> 2. You selectively stage just those changes you want to be part of your next commit, which adds *only* those changes to the staging area.
> 3. You do a commit, which takes the files as they are in the staging area and stores that snapshot permanently to your Git directory. [🔗来源](https://git-scm.com/book/en/v2/Getting-Started-What-is-Git%3F)
>
> 基本的git流程如下
>
> 1. 在工作区内修改了文件
> 2. 有选择性的 将想要提交到版本库的修改 添加到暂存区
> 3. 进行提交操作后,会将暂存区的文件的快照永久的保存到版本库

- **查看提交日志** (这部分应该放到提交之后)

*待更新

```bash
git log [fileName] --pretty=oneline #查看提交记录--pretty=oneline选项表示简化输出信息
git reflog  #查看提交日志（可结合版本回退，回退到指定版本）
#输出
bf20850 (HEAD -> master) HEAD@{0}: commit: created new file readme.txt
b4bc514 HEAD@{1}: commit: modified and added
#前面的字符串就是版本号
```

#### **6.切换版本**

*待更新

- 回到上一个版本

  ```bash
  git reset --hard HEAD~1 #HEAD表示当前版本，HEAD~1表示上一个版本，HEAD~20表示前20个版本
  ```

- 切换到指定版本

  ```bash
  git reset --hard 1094adb #回到指定的版本 版本号不必写全
  ```

#### **7.删除文件**

如果不想要 `git` 继续跟踪管理某个文件，可以使用 `git rm` 命令 , 该命令同时也会删除工作目录下的对应文件。

```bash
git rm test.txt
rm 'test.txt'
```

如果没有使用 `git rm` 命令删除文件，而是手动到工作区删除了文件的话，使用 `git status` 命令查看状态报告时 , `git` 会提示哪些文件被删除了

```bash
Changes not staged for commit:
  (use "git add/rm <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        deleted:    test.txt
```

并且 `git` 也给出了说明，如果想要记录此次删除操作，可以使用命令 `git add` 或 `git rm`

如果想要撤销此次删除操作的话，可以使用命令`git restore`

#### 8.打标签

#### 9.别名

### 远程仓库

远程仓库是指保存在服务器上的代码库, 通常个人(或公司)的开源项目可以选择将代码托管到 **[github](https://github.com/)**,就无需自己搭建Git服务器啦。

通过将代码推送到远程仓库，就不同担心因为本地磁盘损坏而导致代码丢失了✌，如果是多人协作的项目，那只需要每个人都到远程仓库**克隆**一份到本地就可以,这样一来，项目的代码分布在各个电脑上，最坏的情况，即使服务器损坏了，也能从本地获取到代码的备份。

📍 本地仓库和远程仓库之间可以通过ssh协议进行通信,所以需要设置👉[SSH key](https://docs.github.com/cn/github/authenticating-to-github/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account) 

> 📌GitHub允许你添加多个Key。假定你有若干电脑，你一会儿在公司提交，一会儿在家里提交，只要把每台电脑的Key都添加到GitHub，就可以在每台电脑上往GitHub推送了。 [🔗来源](https://www.liaoxuefeng.com/wiki/896043488029600/896954117292416)

#### 1.添加远程仓库

在github上新建远程仓库后可以选择

- 将本地仓库与远程仓库关联

```bash
 git remote add origin <远程仓库地址>
 #如  git remote add origin git@github.com:michaelliao/learngit.git
 #origin是远程仓库名，也可以自己修改成喜欢的名字
```

- 克隆远程仓库到本地

```bash
git clone <远程仓库地址>
#如 git clone git@github.com:github/gitlib.git
```

#### 2.常用操作

📍 先确保已经添加SSH密钥到Git账户哦（ 如 [github](https://docs.github.com/cn/github/authenticating-to-github/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account) , gitlab )

- 查看远程库信息

```powershell
git remote -v 
```

- "删除"远程库

```bash
git remote rm origin #origin是远程仓库名
```

> 📌 此处的“删除”其实是**解除了**本地和远程的**绑定**关系，并不是物理上删除了远程库。远程库本身并没有任何改动。要真正删除远程库，需要登录到GitHub，在后台页面找到删除按钮再删除。[🔗来源](https://www.liaoxuefeng.com/wiki/896043488029600/898732864121440)

- 推送本地仓库内容到远程

```bash
git push <远程仓库名><本地分支名>:<远程分支名> # 本地分支推送到远程仓库的分支
#如 git push origin master:master 表示 推送本地分支master到远程仓库origin的master分支

git push origin master # 将本地的master分支推送到远程仓库origin的master分支，如果远程master分支不存在，则新建分支

git push origin #推送当前分支到远程仓库origin的对应分支

git push -u origin master #-u参数会指定origin为默认远程仓库，之后就可以使用简化的命令推送👇
 
git push # 📍 推送当前分支到默认仓库的对应分支
```

### 分支管理

#### 1.新建分支

#### 2.

## 保存原理

`git add` 和 `git commit`这两条简短的命令具体做了哪些事？🤷‍♂️

###### 1.计算校验和

`git add`

在我们进行暂存操时, git 会对暂存区的文件计算校验和👇

Git 用以计算校验和的机制叫做 SHA-1 散列（hash，哈希）。 这是一个由 40 个十六进制字符（0-9 和 a-f）组成的字符串，基于 Git 中文件的内容计算出来。 SHA-1 哈希看起来是这样

```bash
24b9da6552252987aa493b52f8696cd6d3b00373
```

###### **2.保存数据对象**

git在计算校验和之后会将文件内容压缩，并保存到**blob对象（数据对象）**中

(没有变化的文件就不会生成新的blob对象，因为相同内容的SHA-1值是唯一的)

> [链接🔗 从基本Git指令到背后原理，带你手把手实现一个简单的Git](https://zhuanlan.zhihu.com/p/340369222)
>
> 📌 文件内容的储存过程👇
>
> `git hash-object -w file.txt`
>
> 1. 首先生成一个**头部信息**，由对象类型、一个空格、数据内容的长度，一个空字节组成，
>
>    ​	 如`blob 35\u0000`
>
> 2. 然后将头部信息和**原始数据**拼接起来，计算出 **SHA-1 校验和** ，得到一个字符串
>
>      拼接后的数据如`blob 35\u0000this is a readme file `
>
>      校验和如`fbfbfde2454258a0370187a3cb2cb9bafae2b1f0`
>
> 3. 具体存储的内容则通过 **zlib** **压缩**，上面计算出的值**前两位做目录，**后**38位做文件名（键名）**生成文件保存
>
>      （因为文件内容经过压缩，所以直接查看文件内容是乱码）
>
>      如👇
>
>   ```bash
> cat ./fb/fbfde2454258a0370187a3cb2cb9bafae2b1f0
> xK▒▒OR02d(▒▒,V▒D▒▒▒Ĕ▒T▒▒̜T▒p     ▒  # 输出
>   ```
>
>   通过`git cat-file -p`命令可查看原内容
>
> ```bash
> git cat-file -p fbfbfde2454258a0370187a3cb2cb9bafae2b1f0
> this is a readme file #输出
> ```

###### **3.保存项目快照**

🔗**[对象数据库](https://git-scm.com/book/en/v2/Git-Internals-Git-Objects)**（.git/objects）

git的对象数据库里保存了以下3种对象

1. **[blob 对象](#2.保存数据对象)**（即数据对象，保存着文件内容）

2. **[树对象](#3.保存项目快照)** （ 保存了blob 对象索引）
3. **[提交对象](#4.保存提交对象)**(保存了提交时的信息及树对象的索引)

blob对象只保存了文件内容,并未保存文件名，而树对象则记录了blob对象及其对应的文件名。通常，Git首先会把要保存的内容放入暂存区，然后以tree对象的形式将暂存区的内容写入Git数据库

（可以通过 `git write-tree` 命令将暂存区内容写入一个树对象）

```bash
git write-tree
4bfa25dce3532386b8924ca569efbada55685794  #tree对象的唯一键
```

树对象允许嵌套子树，所以一个树对象的列表中也可以包含另一个树对象，如下👇的目录

```powershell
#工作区打开cmd输入命令 tree/ 以树形式查看目录结构
C:.
│  git-learning.md
│  readme.txt
│
└─folder
        hello.txt
        
        #hello.txt路径： 工作区/folder/hello.txt
```

对应的树对象👇

```bash
#bash
git cat-file -p master^{tree} #查看master分支上最新的提交所指向的树对象
040000 tree e5b2b26f6dbff59480aab8320779408330c2b335    folder
100644 blob 1e956728d334b2c80121d75759234e46f7dfcdc7    git-learning.md
100644 blob fbfbfde2454258a0370187a3cb2cb9bafae2b1f0    readme.txt
#040000表示目录  #tree表示该对象是树对象  #后面一串是计算出来的校验和  #之后是文件（夹）名

#再查看树对象中嵌套的e5b2树对象
git cat-file -p e5b2
100644 blob f09e9c379f5fe8f4ce718641c356df87906d87a6    hello.txt
```

以图片形式表示的话，git保存数据的形式如下

![img](https://gitee.com/yaorunhua/runbed/raw/master/img/LX_work/data-model-1.png)

图片来源：[🔗链接](https://git-scm.com/book/en/v2/Git-Internals-Git-Objects)

📍 通过树对象的嵌套，树对象也实现了对**目录结构**的保存。

📌利用tree对象，我们实际上为本地Git库保存了一份反映当前更改的**快照**，因为它包含了本次要提交的全部更改。[链接🔗](https://morningspace.github.io/tech/inside-git-2/)

###### 4.保存提交对象

**提交对象**（包含指向树对象的指针和所有提交信息）。

当使用 `git commit` 进行提交操作时，Git 会保存一个**提交对象（commit object）**.

该提交对象包含了作者的姓名和邮箱、提交时输入的信息，以及指向其对应的树对象和上一次提交对象（首次提交没有父提交对象）的指针。

这样一来，通过提交对象，我们就能知道何时，是谁，出于什么原因对文件进行了修改，并且可以通过它指向的树对象还原特定时刻的文件内容。

通过`commi tree `命令可以手动创建一个commit对象,如👇

```bash
echo 'commit test' | git commit-tree 2764 
#指定需要提交的tree对象，如果有要指定的父提交对象，使用选项-p
#如 git commit-tree 0155eb -p fdf4fc3

40046ca441c8c2ebdf75a1aff6bddc1429d27d54
#👆输出commit对象的校验和
```

一个提交对象的例子如下

```bash
git cat-file -p fdf4fc3
tree d8329fc1cc938780ffdd9f94e0d364e0ea74f579  #指向的树对象
author Scott Chacon <schacon@gmail.com> 1243040974 -0700 
committer Scott Chacon <schacon@gmail.com> 1243040974 -0700

first commit  #提交时的附加信息
```

多次提交后,产生的提交对象间的关系如下图

![img](https://gitee.com/yaorunhua/runbed/raw/master/img/LX_work/commits-and-parents.png)

>  📌这就是每次我们运行 `git add` 和 `git commit` 命令时，Git 所做的工作。
>
> 就是将被改写的文件保存为数据对象， 更新暂存区，记录树对象，最后创建一个包含了顶层树对象和父提交对象的引用的提交对象。[链接🔗](https://git-scm.com/book/zh/v2/Git-%E5%86%85%E9%83%A8%E5%8E%9F%E7%90%86-Git-%E5%AF%B9%E8%B1%A1)  
>
> 📍 通过将commit对象建立起前后关系，当我们需要查看某个版本的文件时，git通过跟踪引用，就能快速追溯到相应文件, 而当我们想要查看某次提交及其之前的所有提交历史时，只需要使`  git log <commit对象唯一键>`命令就能查看历史记录
>
> ```bash
> git log --stat 1a410e  # --stat 选项会列出文件的修改
> 
> commit 1a410efbd13591db07496601ebc7a059dd55cfe9
> Author: Scott Chacon <schacon@gmail.com>
> Date:   Fri May 22 18:15:24 2009 -0700
> 
> 	third commit
> 
>  bak/test.txt | 1 +
>  1 file changed, 1 insertion(+)
> 
> commit cac0cab538b970a37ea1e769cbbde608743bc96d
> Author: Scott Chacon <schacon@gmail.com>
> Date:   Fri May 22 18:14:29 2009 -0700
> 
> 	second commit
> 
>  new.txt  | 1 +
>  test.txt | 2 +-
>  2 files changed, 2 insertions(+), 1 deletion(-)
> 
> commit fdf4fc3344e67ab068f836878b6c4951e3b15f3d
> Author: Scott Chacon <schacon@gmail.com>
> Date:   Fri May 22 18:09:34 2009 -0700
> 
>     first commit
> 
>  test.txt | 1 +
>  1 file changed, 1 insertion(+)
> ```

###### 5.包文件 

📍既然我们已经知道在执行提交操作时，git会完整的保存提交文件的全部内容（在经过压缩后），那随着我们提交次数的不断增加，文件越来越多，岂不是很占用空间？而且我们比较常访问的通常是文件的最新版本或前个版本，如果将所有版本的文件都完整保存，那是不是浪费了一些空间呢👀

针对这样的问题，Git其实已经有解决方案啦🧚‍♂️

为了节省空间，git在保存数据对象时会进行压缩，除此之外，git**时常**👇会将这些数据对象**打包**成为一个称为**包文件**的二进制文件

> 📌 当版本库中有**太多**的松散对象，或者你手动执行 `git gc` 命令，Git 都会这样做
>
> 📌Git 最初向磁盘中存储对象时所使用的格式被称为“松散（loose）”对象格式

在打包对象的过程中，会保存文件最新版本的全部内容，而对文件的其他版本**只保存**他们与最新版本的**差异内容**，这样就能节省大量空间，并且也能快速访问到文件的最新版本

我们可以手动打包，来验证一下

我创建了一个新文件夹 `pack`，并将这篇笔记`git-learning`复制pack目录下

初始化仓库，并提交文件后，可以看到git的对象数据库中新增了3个对象（一个blob对象，一个树对象，一个提交对象）

```bash
#工作区pack文件夹下初始化git版本库
git init

git add .
#提交
git commit -m 'added file git-learning.md'
[master (root-commit) 6919688] added file git-learning.md
1 file changed, 648 insertions(+)
create mode 100644 git-learning.md

#切换到.git/objects目录下
cd ./.git/objects
find -type f
./42/02dae168cf7803ea64097dfdcccd912c2a2015
./69/19688d07e72e7df9c305c0538939540348b0dd
./e4/5e8f5b47474efd5d2b50c5cae0dc1014b0f928

#查看树对象
git cat-file -p master^{tree}
100644 blob 4202dae168cf7803ea64097dfdcccd912c2a2015    git-learning.md

#👆笔记已经被压缩为blob对象保存了
```

然后我们查看blob对象`4202`的大小👇，显示大小为 **24647**字节

```bash
#工作区切换到objects目录下
cd ./.git/objects

git cat-file -s 4202
24647

#大小为24647字节
```

现在我们再次修改文件,添加几个字,再次提交,又生成了3个对象,其中`cdd2`是这次生成的blob对象

```bash
git commit -m "modified"
[master 405711f] modified
 1 file changed, 28 insertions(+), 26 deletions(-)

git cat-file -p master^{tree}
100644 blob cdd23ecc1d7418ea23ef75215dc8bdff56dc634d    git-learning.md

```

经过上面的操作,在git版本库中,文件`git-learning`已经存在两个版本,`39c3`(第一版) 和 `2e9a` (第二版),

两个版本的文件的差别仅仅是几个字的内容,且git完整的保存了这两个版本的文件

现在我们执行 `git gc` 命令让git打包对象

```bash
git gc
Enumerating objects: 6, done.
Counting objects: 100% (6/6), done.
Delta compression using up to 8 threads
Compressing objects: 100% (4/4), done.
Writing objects: 100% (6/6), done.
Total 6 (delta 1), reused 0 (delta 0), pack-reused 0
```

然后我们查看`objects` 文件夹 , 会发现之前的6个对象都不见了(未提交过的对象不会被打包,所以打包后会出现只是大部分对象被打包的情况), 只剩下两个文件夹`info`和`pack`

> Question: info目录下的文件什么作用?

📌back文件夹下的两个文件是新创建的包文件(.pack)和一个索引(.idx)。 包文件包含了刚才从文件系统中移除的所有对象的**内容**。 索引文件包含了包文件的**偏移信息**，我们通过索引文件就可以快速定位任意一个指定对象 [链接🔗](https://git-scm.com/book/zh/v2/Git-%E5%86%85%E9%83%A8%E5%8E%9F%E7%90%86-%E5%8C%85%E6%96%87%E4%BB%B6)

```bash
find .git/objects -type f
.git/objects/info/commit-graph
.git/objects/info/packs
.git/objects/pack/pack-0476da2e835e854d847b212be9cc1c2ce97b8753.idx
.git/objects/pack/pack-0476da2e835e854d847b212be9cc1c2ce97b8753.pack
```

通过`git verify-pack -v`命令可以查看包文件和索引文件的内容



###### 6.数据传输

现在我们已经对git如何保存数据有了大致的了解，不过还有一个疑问 

当我们向远程推送文件，或者当我们从远程拉取文件时，git是怎么操作的呢？👀

 [pro-git-book](https://git-scm.com/book/en/v2) 的 10.6 章 [Git内部原理-传输协议](https://git-scm.com/book/zh/v2/Git-%E5%86%85%E9%83%A8%E5%8E%9F%E7%90%86-%E4%BC%A0%E8%BE%93%E5%8D%8F%E8%AE%AE)一节，对git如何在版本库之间传输数据进行了描述

- 上传数据
- 下载数据

## 分支原理

这里写分支的优点

📌使用分支意味着你可以从开发主线上分离开来，然后在不影响主线的同时继续工作

📌Git 的分支，其实本质上仅仅是指向提交对象的**可变指针**。[链接🔗](https://git-scm.com/book/zh/v2/Git-%E5%88%86%E6%94%AF-%E5%88%86%E6%94%AF%E7%AE%80%E4%BB%8B)

###### **1. 引用**

> 📌如果你对仓库中从一个提交（比如 `1a410e`）开始往前的历史感兴趣，那么可以运行 `git log 1a410e` 这样的命令来显示历史，不过你需要记得这个提交对象的SHA-1值，比如`1a410e` 。
>
> 但如果我们用一个文件来保存 SHA-1 值，而该文件有一个简单的名字， 然后用这个名字指针来替代原始的 SHA-1 值的话会更加简单。 [链接🔗](https://git-scm.com/book/zh/v2/Git-%E5%86%85%E9%83%A8%E5%8E%9F%E7%90%86-Git-%E5%BC%95%E7%94%A8)

Git就是这样做的，在Git中，这样的文件被称为“引用（references，或简写为 refs）”通过命令👇

```bash
 echo 1a410efbd13591db07496601ebc7a059dd55cfe9 > .git/refs/heads/master
```

将 `1a410e`这个提交对象的SHA-1值保存到`.git/refs/heads/master` 中，这样就创建了一个引用(master)

然后就可以用这个引用代替原来的SHA-1值，例如，想要查看上述的提交历史，只需要使用下面这条命令即可

```bash
git log --pretty=oneline master # --pretty=oneline 简化了输出
#输出
1a410efbd13591db07496601ebc7a059dd55cfe9 Third commit
cac0cab538b970a37ea1e769cbbde608743bc96d Second commit
fdf4fc3344e67ab068f836878b6c4951e3b15f3d First commit
```

如果想要更新某个引用，可以使用命令 `git update-ref` 来进行更新（git不建议直接对引用文件进行编辑）

如

```bash
 git update-ref refs/heads/master 1a410efbd13591db07496601ebc7a059dd55cfe9
```

基于引用的概念，git 实现了分支

比如我们现在想要在 `6f6422` 这次提交这里新建一个test分支，其实就是将`6f6422` 的SHA-1值保存到了 文件 `refs/heads/test ` 中，如下

```bash
git update-ref refs/heads/test 6f6422
 #这条命令其实就创建了一个test分支
 #查看 test 文件的内容(.git文件夹下)
cat ./refs/heads/test
6f64227f238815b003bdf9b398cfc71abd09a44c
```

然后运行 `git branch `命令分支👇，可以看到的确多了一个分支

```bash
$  git branch
npx: installed 17 in 1.909s
* master
  test

#使用 git log test 命令也能查看到对应的提交记录
```

📍 所以当我们执行**新建分支**的命令 `git branch <branch>` 时，Git 实际上会运行 `update-ref` 命令， 取得当前所在分支的**最新提交**所对应的 SHA-1 值，并将其加入到新建的引用中

所以 Git 的分支，其实本质上仅仅是指向提交对象的可变指针

###### **2. HEAD文件**

那git是怎么知道最新提交的SHA-1值的呢？---通过HEAD文件

📍 HEAD文件是一个符号引用，符号引用的意思就是说他并不直接指向某个对象，而是指向某个引用，再由该引用指向某个对象。即HEAD**间接的**指向了最新的提交对象的SHA-1值。

可以通过查看HEAD文件内容来验证： 

```bash
#(.git文件夹下)
cat ./HEAD
#输出
ref: refs/heads/master

```

如果我们执行切换分支命令 `git checkout test` 会发现此时HEAD文件的内容改变了，相应的，设置HEAD对应的引用就相当于执行了切换分支命令，不过git并不提倡我们手动修改HEAD文件，而是提供了一条命令*。（之后也会提到）

```bash
----------------------------（工作区下）
git checkout test
Switched to branch 'test'
 
git branch
npx: installed 17 in 8.665s
  dev
  master
* test
---------------------------- (.git目录下)
cat ./HEAD
ref: refs/heads/test
```

📍 而且，当我们执行`git commit `命令时，git会创建一个提交对象，并将HEAD间接指向的commit对象设置为新创建的提交对象的父对象，然后更新引用（将对应的refs文件所保存的SHA-1值更新为最新提交对象的SHA-1值）

如👇

```bash
----------------------------(工作区)
#修改文件后进行一次提交
git commit -m "added a new line after switching branch"
[test 9a0ab93] added a new line after switching branch
 1 file changed, 2 insertions(+), 1 deletion(-)

----------------------------（.git）目录下
#查看HEAD文件
cat ./HEAD
ref: refs/heads/test
#查看对应的引用文件 
cat ./refs/heads/test
9a0ab9321c100104ded2e3cf3f1e55c5284f8c56
#👆引用更新了

#👇切换到objects目录下查看该提交对象
cd ./objects

git cat-file -p 9a0a
tree 311ff361c3496c1f54c3279f25e02c053f92f882
parent 6f64227f238815b003bdf9b398cfc71abd09a44c
#👆 可以看到提交之前HEAD所指向的提交对象被作为了最新提交对象的父对象
```

如果我们想要查看HEAD所对应的引用，可以使用命令`git symbolic-ref HEAD`， 借助该命令也可以设置HEAD对应的引用，设置HEAD引用其实就相当于执行了切换分支命令*。

```bash
git symbolic-ref HEAD
refs/heads/test

#现在将HEAD对应额引用设置为refs/heads/dev
git symbolic-ref HEAD refs/heads/dev

#然后再执行git branch命令
git branch
npx: installed 17 in 2.24s
* dev
  master
  test
#👆可以看到已经切换到了dev分支
```

###### 3.远程引用

远程引用保存在 `.git\refs\remotes` 目录下，当我们向远程仓库推送代码时，会在对应的文件夹下生成一个远程引用，并保存当前分支的最近一次推送所对应的提交对的SHA-1值。

如当前在dev分支，提交代码后推送到远程仓库origin的dev分支

```bash
------------------------------ （工作区）
#提交代码
git commit -m "测试远程引用"
[dev e3f57a7] 测试远程引用  #注意提交对象的SHA-1值
1 file changed, 2 insertions(+), 1 deletion(-)

#推送到远程dev分支
git push origin dev

------------------------------ （.git目录下）
cd ./refs/remotes/origin

ls 
dev  master
#👆可以看到远程引用文件夹下新创建了一个远程引用文件dev

#查看dev远程引用
cat dev
e3f57a794cc17917b95373a53d42ce1f25e9b0ad
#👆dev引用里保存的的确是刚才的提交对象的SHA-1值
```

和分支不同，远程引用更像是书签作用，记录了**远程**服务器上各分支的最新推送

###### 4.标签引用

学完标签再写



## 名词解释：

###### 快进

在合并的时候，你应该注意到了“快进（fast-forward）”这个词。 由于你想要合并的分支 `hotfix` 所指向的提交 `C4` 是你所在的提交 `C2` 的直接后继， 因此 Git 会直接将指针向前移动。换句话说，当你试图合并两个分支时， 如果顺着一个分支走下去能够到达另一个分支，那么 Git 在合并两者的时候， 只会简单的将指针向前推进（指针右移），因为这种情况下的合并操作没有需要解决的分歧——这就叫做 “快进（fast-forward）”。 [🔗](https://git-scm.com/book/zh/v2/Git-%E5%88%86%E6%94%AF-%E5%88%86%E6%94%AF%E7%9A%84%E6%96%B0%E5%BB%BA%E4%B8%8E%E5%90%88%E5%B9%B6)

###### 合并操作git做了些啥
