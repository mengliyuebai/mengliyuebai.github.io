## 基于Merge Request的开发流程

[Merge requests](https://docs.gitlab.com/ee/user/project/merge_requests/) allow you to visualize and collaborate on the proposed changes to source code that exist as commits on a given Git branch.A Merge Request (MR) is the basis of GitLab as a code collaboration and version control platform. 

### 1、制定分支策略。

所有人都直接推送代码到master分支，像使用SVN一样的方式是不可取的。

1. Git flow
2. GitHub flow
3. GitLab flow (推荐)

### 2、创建Issues

功能分支或修复分支总是为了解决Issues，建议先创建Issues再创建分支。

说明：在Issue页面，可以直接“创建合并请求及分支”，分支默认名为 [序号]+[议题名字]，可自定义，但私密议题无法进行此操作。

### 3、拉取分支。

1. 拉取：GitLab flow/GitHub flow 由master分支拉取；Git flow由develop分支拉取。
2. 命名：分支名与Issues名字关联，管理更清晰。比如，分支名fix-#14

### 4、Push到远程GitLab服务器，或者直接在GitLab页面修改。

如果是协作开发的分支，先pull再push

### 5、发起合并请求

GitLab Merge Requests，在Github上称之为Pull Request。合并请求功能，提供了一个交流的平台，可以很方便的在MR页面，讨论、查看提交和变更，甚至解决冲突。

`增加一个新页面` 

`这个 MR 将会为这个项目创建一个包含该 app 概览的 readme.md。` 

`Closes #xxx and https://gitlab.com/<username>/<projectname>/issues/<xxx>`  

`预览： [预览新页面](#image-url) cc/ @Mary @Jane @John`  

MR可选项：

当MR被接受后，删除源分支。

当MR被接受后，Squash commits

### 7、将分支合并merge进master分支。

通过代码评审（Code Review），分支被合并。如果是WIP状态的合并请求，先移除WIP，再合并。

MR被合并后，可选操作

1. Cherry-pick [Cherry-pick changes](https://docs.gitlab.com/ee/user/project/merge_requests/cherry_pick_changes.html)
2. Revert [Reverting changes](https://docs.gitlab.com/ee/user/project/merge_requests/revert_changes.html) 

### 8、完成所有Issues后，创建标签Tag，进行发布。

### 9、在Issues和MR的描述中，可以使用的特殊符号

1. 输入 # 来触发一个已有Issues的下拉列表

2. 输入 ! 来触发一个已有 MR 的下拉列表

3. 输入 / 来触发Quick Actions命令

4. 输入 : 来出发 emoji 表情 (也支持行中评论)

5. 输入 > 进行引用

6. 任务列表

* [ ] task 1
* [x] task 2
* [ ] task 3

[Quick Actions](https://docs.gitlab.com/ee/user/project/quick_actions.html#gitlab-quick-actions)，支持议题、合并请求、评论和epics

1. /close ，关闭议题等。
2. /wip，Toggle the Work In Progress status。如果合并请求，还未准备好被合并，在标题添加**WIP:**标记，将不会被合并。
3. /reopen，重新打开
4. /award :emoji:，输入/award :后选择表情。Toggle emoji award
5. /assign me，Assign yourself
6. /assign @user，分配给某人

[Closing issues automatically](https://docs.gitlab.com/ee/user/project/issues/managing_issues.html#default-closing-pattern) 如果提交信息或合并请求的描述包含了 [defined pattern](https://docs.gitlab.com/ee/user/project/issues/managing_issues.html#default-closing-pattern) 议题将被自动关闭 

>  For example, if Closes #4, #6, Related to #5 is included in a Merge Request description, issues #4 and #6 will close automatically when the MR is merged, but not #5. Using Related to flags #5 as a related issue, but it will not close automatically.If the issue is in a different repository than the MR, add the full URL for the issue(s)。