# Action-jd-scripts

我用了一个方法，似乎不用去大佬的库下载脚本

首先在gitee里面fork大佬的jd_scripts库，在自己fork的库新建一个分支，在新建分支里面上传大佬的yml执行文件。
2.在github新建一个库，把大佬的repo_sync.yml文件上传
3.在gitee你新建分支里把yml执行文件的checkout的仓库地址全部换成你自己github新建库的地址：
name: Checkout
uses: actions/checkout@v2
with:
repository: 你自己的GitHub新建库
4.在GitHub新库和gitee你的分支里面，把repo_sync.yml文件的 下面三个参数修改一下：
source_repo: "https://gitee.com/你自己的名字/jd_scripts.git"
source_branch: "gitee里面你新建的分支"
destination_branch: "GitHub里你的新库（main或者master）"
5.回到github在action里运行sync-lxk0301-scripts，不出意外所有文件就都过来了，接下来就没啥问题了。
6.这样大佬更新代码，我们可以在gitee同步，然后合并自己的分支，GitHub可以自动同步自己的gitee分支。
