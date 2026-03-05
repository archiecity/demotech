# Github在vscode中的连接指南

在左侧使用代码源管理器->连接到你在GitHub上创造的仓库
通用流程：
暂存——>写消息——>提交——>写消息——>同步更改
## 使用时

1. 先暂存更改

2. 再讲更改提交上去（！！！注意，一定要写消息，GitHub不允许空的更改提交上去，否则你会卡住）

3. 提交之后要同步更改，这样就可以直接影响到仓库了（只提交，影响的只是本地仓库）（同步更改也需要写消息，否则也会卡住）#我第一次学的时候在这里卡了很久 -_-

## 权限方面
没有特殊需求（敏感信息，涉密信息），一般使用public，别人无法直接修改你仓库里的东西，放心设置成public（一般设置了也没人看QAQ）

方法一：先进入目标目录，再执行克隆（最常用）
你可以使用 cd (Change Directory) 命令，先在终端里“走”到你期望存放代码的父级目录中，然后再执行克隆命令。默认情况下，Git 会在你当前所在的目录下，自动创建一个与仓库同名的新文件夹。

Bash
## 1. 进入你用来写代码的专用目录（例如 D盘的 Workspace）
```
cd D:/Workspace
```
## 2. 执行克隆命令
```
git clone https://github.com/pytorch/tutorials.git
```
## 结果：代码会被完整存放在 D:/Workspace/tutorials/ 文件夹下
方法二：直接在命令末尾指定目标路径或自定义名称
如果你不想用原仓库的名字，或者不想使用 cd 命令切换路径，可以直接在 git clone 的命令末尾加上你想要的文件夹名称或绝对路径。

Bash
## 用法 A：克隆到当前目录，但把文件夹重命名为 "my_ai_project"
```
git clone https://github.com/pytorch/tutorials.git my_ai_project
```
## 用法 B：无视当前所在目录，直接克隆到指定的绝对路径下
```
git clone https://github.com/pytorch/tutorials.git D:/Workspace/my_ai_project
```


## 三大卡住病因
1. 没写消息
2. 网卡了
3. 验证弹窗被隐藏了