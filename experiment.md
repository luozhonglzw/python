# 实验一 Git和MarkDown基础
班级：21计科04
学号：20210302424
姓名：罗中威
Gitee地址：https://gitee.com/luo-zhongwei
GitHub地址：https://github.com/luozhonglzw   

---

## 实验目的
1. Git基础，使用Git进行版本控制
2. Markdown基础，使用Markdown进行文档编辑
   ## 实验目的

1. Git基础，使用Git进行版本控制
2. Markdown基础，使用Markdown进行文档编辑

## 实验环境

1. Git
2. VSCode
3. VSCode插件

## 实验内容和步骤

### 第一部分 实验环境的安装

1. 安装git，从git官网下载后直接点击可以安装：[git官网地址](https://git-scm.com/)
2. 从Github克隆课程的仓库：[课程的仓库地址](https://github.com/zhoujing204/python_course)，运行git bash应用（该应用包含在git安装包内），在命令行输入下面的命令（命令运行成功后，课程仓库会默认存放在Windows的用户文件夹下）

```bash
git clone https://github.com/zhoujing204/python_course.git
```

如果你在使用`git clone`命令时遇到SSL错误，请运行下面的git命令(这里假设你的Git使用了默认安装目录)：

```bash
git config --global http.sslCAInfo "C:/Program Files/Git/mingw64/ssl/certs/ca-bundle.crt"
```

或者运行下面的命令:

```bash
git config --global http.sslVerify false
```

如果遇到错误：`error setting certificate file`，请运行下面的命令重新指定git的安全证书：

```bash
git config --global --unset http.sslCAInfo
git config --global http.sslCAInfo "C:/Program Files/Git/mingw64/ssl/certs/ca-bundle.crt"
```

该仓库的课程材料后续会有更新，如果需要更新课程材料，可以在本地课程仓库的目录下运行下面的命令：

```bash
git pull
```

在本地的仓库内容有更新后，可以运行下面的命令，将本地仓库的内容和远程仓库的内容同步：

```bash
git push origin main
```

3. 注册Github账号或者Gitee帐号，创建一个新的仓库，使用上面同样的方法将该仓库clone到本地，用于存放实验报告和实验代码，使用`git pull`和`git push`命令保持远程仓库和本地仓库的同步。
4. 安装VScode，下载地址：[Visual Studio Code](https://code.visualstudio.com/)
5. 安装下列VScode插件
   - GitLens
   - Git Graph
   - Git History
   - Markdown All in One
   - Markdown Preview Enhanced
   - Markdown PDF
   - Auto-Open Markdown Preview
   - Paste Image
   - markdownlint

### 第二部分 Git基础

教材《Python编程从入门到实践》P440附录D：使用Git进行版本控制，按照教材的步骤，完成Git基础的学习。

### 第三部分 learngitbranching.js.org
####使用git commit命令
创建一个新的提交记录
```bat
git commit
```
创建一个新的分支并将其交替
```bat
git branch bugFix
git checkout bugFix
git commit
```
合并分支
```bat
git branch bugFix //创建新分支
git checkout bugFix //切换带该分支
git commit//运行一次
git checkout main//切换回main
git commit//再提交一次
git merge bugFix//合并
```
另一种合并方法
```bat
git branch bugFix
git checkout bugFix
git commit
git checkout main
git commit
git checkout bugFix
git rebase main
```
# 高级篇
### 1. 分离head
```
git checkout c4 //head指向c4
```
### 2. 相对引用
- 使用 ^ 向上移动 1 个提交记录
- 使用 ~<num> 向上移动多个提交记录，如 ~3
```
git checkout bugFix^
```
### 3. 相对引用2
```
git branch -f main C6
git checkout C1
git branch -f bugFiX HEAD^
```
### 4. 撤销变更 
两种方法用来撤销变更:
1.git reset(本地)，2.git revert(远程)
pushed 是远程分支，local 是本地分支 
```
git reset HEAD
git checkout pushed
git revert HEAD
```
```
显示效果如下：
```bat
git init
git add .
git status
git commit -m "first commit"
```
### 第四部分 Markdown基础

查看[Markdown cheat-sheet](http://www.markdownguide.org/cheat-sheet)，学习Markdown的基础语法

使用Markdown编辑器（例如VScode）编写本次实验的实验报告，包括[实验过程与结果](#实验过程与结果)、[实验考查](#实验考查)和[实验总结](#实验总结)，并将其导出为 **PDF格式** 来提交。

如何将markdown文件转换为pdf格式的文件？

- 安装vscode插件Markdown PDF，安装后重启vscode，打开markdown文件，按下`Ctrl+Shift+P`，输入`Markdown PDF: Export (pdf)`，回车即可导出pdf文件。
- 使用Google Chrome浏览器，在Github网站或者Gitee网站打开你的仓库，浏览你的markdown文件，按下`Ctrl+P`，选择`打印`，选择`目标打印机`为`另存为PDF`，点击`保存`即可导出pdf文件。

## 实验过程与结果

请将实验过程中编写的代码和运行结果放在这里，注意代码需要使用markdown的代码块格式化，例如Git命令行语句应该使用下面的格式：

![Git命令](/Experiments/img/2023-07-26-22-48.png)

显示效果如下：

```bash
git init
git add .
git status
git commit -m "first commit"
```

代码运行结果的文本可以直接粘贴在这里。

**注意：不要使用截图，Markdown文档转换为Pdf格式后，截图可能会无法显示。**

## 实验考查

请使用自己的语言回答下面的问题，这些问题将在实验检查时用于提问和答辩，并要求进行实际的操作。

1. 什么是版本控制？使用Git作为版本控制软件有什么优点？
2. 
2. 1.版本库本地化，版本库的完整克隆，包括标签、分支、版本记录等。 2.支持离线提交，适合跨地域协同开发。 3.分支切换快速高效，创建和销毁分支廉价。
2. 
3. 如何使用Git撤销还没有Commit的修改？如何使用Git检出（Checkout）已经以前的Commit？（实际操作）
4. 
3. mkdir git-tmp cd git-tmp git init echo '第1次输入的内容' >> file1.log git add. git commit -m '第1次提交' echo '第2次输入的内容' >> file1.log git add. git status 这种情况，比场景三仅多了步暂存，那我们可以先取消暂存、然后再检出： git reset git checkout.
3. 
4. Git中的HEAD是什么？如何让HEAD处于detached HEAD状态？（实际操作）
5. 
5. HEAD严格来说不是指向提交，而是指向master，master才是指向提交的，所以，HEAD指向的就是当前分支
6. $ git reflog -2 HEAD # or $ git log -g -2 HEAD git submodule head detached 是指子模块的 HEAD 指针处于分离状态，需要切换回 分支 与父仓库保持一致，以避免潜在的问题。
4. 
5. 什么是分支（Branch）？如何创建分支？如何切换分支？（实际操作）
6. 
6. 一、创建并切换分支 1、创建分支 git branch dev 2、切换分支 git checkout dev 3、创建并切换分支 git checkout -b dev 二、查看分支 git branch 三、合并分支 git merge dev 四、删除分支 git branch -d dev
6. 
5. 如何合并分支？git merge和git rebase的区别在哪里？（实际操作）
6. 
6. 合并分支 git merge dev
7. git版本控制中，git rebase 和 git merge 这两个命令都可以用来集成从一个分支和另一个分支的更改。它们是两种不同的合并方法，本文将介绍它们的差异。
7. 
6. 如何在Markdown格式的文本中使用标题、数字列表、无序列表和超链接？（实际操作）
7. 标题：
在Markdown中，可以使用 "#" 符号来表示标题。一个 "#" 表示一级标题，"##" 表示二级标题，以此类推，最多可以使用六个 "#" 表示六级标题。例如：

数字列表：
使用数字和点来创建有序列表.

无序列表：
使用连字符、加号或星号来创建无序列表。

超链接：
使用方括号和圆括号创建超链接。方括号用于显示链接文本，圆括号用于指定链接的URL地址。

## 实验总结

总结一下这次实验你学习和使用到的知识，例如：编程工具的使用、数据结构、程序语言的语法、算法、编程技巧、编程思想。

这节课让我了解了 类似树形结构的操作 对数据结构的更加的熟练 对命令行的按键和操作也更加的熟悉 对git命令更加的熟悉
