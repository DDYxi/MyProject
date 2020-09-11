//创建一个空的Git存储库或重新初始化现有的存储库
git init xxx(库名)

//将所有文件内容添加到暂存区中
git add .
//指定文件
git add git笔记.md

//提交版本以及描述
git commit -m "描述"

//显示工作树状态
git status

//显示提交日志
git log
//详细版：以每行的修改情况显示已提交的文件日志
git log -p
//简略版：只显示节点id和节点名称
git log --oneline / git log --oneline --all
//以图形数方式显示日志
git log --graph / git log --oneline --graph / git log --graph --all / git log --oneline --graph --all


//穿越到指定的历史节点
git checkout xxx
//返回上一次保存的节点
git checkout -

//对于一个重要的节点，我们可以打一个标签（tag会打在仓库内的最近一次文件内，一个文件可以打多个tag标签）
git tag -a 标签名 -m '备注'

//给以往的节点添加tag标签名
git tag -a 标签名 -m '备注' 节点ID

//回溯到标签所在的节点
git checkout 标签名

//查看某个标签的详细信息
git show 标签名

//列出所有tag标签
git tag

//创建分支
git branch 分支名
//切换分支
git checkout 分支名
//创建并且切换到分支
git checkout -b 分支名

//合并分支
git merge 分支名

//添加远程仓库
git remote add 远程名称 远程地址
//列出所有远程仓库
gitremote / git remote -v

//上传代码
git push -u 远程名 分支名

//克隆github上的库  （clone下来的资源默认远程仓库就是clone的仓库地址，github远程名称默认叫做origin）
git clone 仓库地址

//获取远程更新
git pull

//三种状态：    modified    stage     committed
                已修改      已暂存      已提交
<!-- 1.git的本地、暂存区、仓库的文件自动对比：
     当保存本地工作文件时，git会将其同时于暂存区和已提交的仓库内的文件对比。
     当git add xxx 上传到暂存区后，暂存区于仓库的对比。
     仓库每次保存的是暂存区的文件。

     2.git的提交：
     如果没有对文件修改，多次使用 git add xxx 暂存区的文件还是一样的。
                       没有git add xxx 将文件放入暂存区，直接 git commit -m '备注' 提交文件时会报错。
                       多次使用 git commit -m '备注' 会报和上面一样的错，因为暂存区已经没有可提交文件了。

     3.回溯到指定节点：
     使用git checkout xxx 在去指定节点前一定要先保存当前本地的版本并上传到仓库，不然无法跳跃到指定节点。
     使用git checkout - 回到最近一次保存的节点，如果来回执行命令，就是在当前和最近两个文件不断切换。
                        使用git log --oneline --all可以准去看出HEAD在哪里。
            
 -->

 