## **以Issues为导向的管理流程**



[GitLab Issues](https://docs.gitlab.com/ce/user/project/issues/index.html) are the fundamental medium for collaborating on ideas and planning work in GitLab.

### 1、团队创建Issues

Issues议题，管理需求、缺陷或要讨论的想法。项目的所有成员都可以创建新的 issue，其他成员可以在 issue 下进行相关的讨论。

1. Milestones：里程碑。
2. Labels：标记。
3. Assignee：受理人。
4. Due date：截止日期。
5. Confidentiality：私密议题，至少有Reporter以上权限的团队成员才能查看并且评论当前议题。
6. Issue Boards：看板。结合Labels，组织工作流。
7. issue Description，议题描述，支持markdown语法。“~”字符插入一个Labels
8. 评论Issues：在讨论过程中，可以通过 @USERNAME 的方式通知其他人关注当前 Issues。
9. weight权重：GitLab EE才有的功能。

### 2、项目的owner对Issues进行Review，并标记。

Labels 标记，可用于议题和合并请求。标记加上星标，变为优先标记。在议题列表页面可根据“标记优先”排序Issues。

优先级（priority）标记。它直接影响 bug 需要被响应的速度、或需求的具体排期。 

1. priority/P1：十分紧急
2. priority/P2：较为紧急
3. priority/P3：普通
4. priority/P4：不紧急

类别（kind）标记。

1. kind/bug：缺陷
2. kind/feature：新功能
3. kind/enhancement：改进项，模块代码重构等不影响项目功能但是改善工程质量的 Issues可归入此类
4. kind/research：技术调研类，一般以输出某类结论或报告视为结束

说明：根据项目特点，由管理者自由创建和调整标记。

### 3、Issues纳入里程碑，并认领或分配Issues

Milestones，里程碑追踪议题和合并请求。

Milestones in GitLab are a way to track issues and merge requests created to achieve a broader goal in a certain period of time.

1. 基于要发布的版本号：比如 v1.0.0、v2.0.1
2. 基于敏捷开发中的一个 sprint： 比如 Y2020-M5、Y2020-M5W1

Assignee表示当前Issues的处理人。

### 4、使用看板组织Issues。

IssueBoard看板，计划、组织和可视化工作流。

1. 可增加多个IssueBoard
2. 可增加IssueBoard泳道

### 5、使用Wiki管理文档。

GitLab wiki，是一个Git repo，文件格式为.md。如需转换为pdf、doc格式，可以用pandoc之类的软件。

1. 主页：第一个页面，必须创建一个Home页，点击项目的wiki功能，打开的就是home页。
2. 标题：标题使用全路径，可以按路径的级次生成页面。例如docs/my-page 将在路径 /wikis/docs/my-page创建页面。
3. 格式：支持Markdown, RDoc and AsciiDoc. 
4. 内容Content：编辑内容使用Markdown语法。GitLab uses "GitLab Flavored Markdown" (GFM).
5. 附件：支持上传附件。

### 6、使用代码片段实现代码复用。

Snippet代码片段，用来保存的小段代码或笔记，解决在不同的项目以及文件中使用一些相同的代码段和模版。可以把它们设置成公开的，内部的（仅为 GitLab 注册用户提供），或者私有的。