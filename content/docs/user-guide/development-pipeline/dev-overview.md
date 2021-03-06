+++
title = "开发控制台"
description = "开发控制台是开发流水线整个模块的控制台，含有快捷全面的开发操作入口。"
weight = 3
+++

# 开发控制台

开发控制台以应用为中心，是开发流水线整个模块的控制台，其中包含了全面快捷的开发操作入口，便于开发人员对开发情况的整体把握。

  - **菜单层次**：项目层
  - **菜单路径**：开发流水线 > 开发控制台
  - **默认角色**：项目所有者、项目成员
  
   
    	  
## 开发控制台
![开发控制台](/docs/user-guide/development-pipeline/image/dev-overview1.jpg)
   

- 通过此界面能查看应用相关的详情信息，如应用编码、代码仓库地址；以及应用相关的一些快捷入口，如查看代码质量；
- 通过此界面可以进行创建分支、创建合并请求和创建标记等快捷操作；
- 通过此界面可以以分支为维度在流水线中进行开发与部署，并且能了解到某个分支的相关信息及具体开发进度；
- 可以查看某个应用的总分支数、总合并请求数以及总标记数，并能通过点击对应的数字快速地跳转至相应模块的详情界面。  

## 流水线  
对某个分支的整个生命周期进行管理与查看，能够具体的了解到某个分支当前的开发进度。  

- 分支管理：流水线的第一部分；在分支管理框内，能选择某个分支或是选择该应用下全部分支来查看对应的CI以及版本生成情况。同时，也可在此创建一个新的分支，并在此基础上进行开发。  

- 持续集成：流水线的第二部分；在持续集成框内，能查看所选分支最近的一条CI记录，包括CI的结果与各个阶段的情况。在框下，会展示出对应分支的最近10条CI记录。同时点击框中右上方的`查看构建报表按钮` → ![查看构建报表](/docs/user-guide/development-pipeline/image/build_report.jpg)，即可查看对应应用的构建报表。

- 应用版本：流水线的第三部分；在应用版本框内，能查看所选分支最近的一条版本生成记录及状态。点击此框，框下会显示出对应分支的最近10条应用版本记录。

## 分支
查看所选应用的最近五条分支相关的信息。  

- 显示每条分支的名称、关联的问题以及与其提交相关的详细信息。  
- 允许修改分支相关联问题，点击`修改分支`的图标可以更改、清空分支相关联的问题。  
- 支持创建合并请求，点击`创建合并请求`图标，系统会默认打开gitlab的创建合并请求的界面，其中源分支就是点击列的分支，目标分支默认是master，用户可以更改。  
- 可以进行删除分支的操作，点击`删除分支`图标，将会删除对应分支。

## 合并请求    
查看当前应用的最近五条合并请求。  

- 显示每条合并请求的编码、名称、状态以及分支合并的简要信息。  
- 允许查看界面中合并请求的详情，点击`查看详情`图标，便能跳转至GitLab对合并请求详情进行查看。  

## 标记
查看当前应用的最近五条标记以及相关的信息。   

- 显示标记名称、标记创建日期、创建人员以及标记内容。  
- 允许对标记进行编辑操作。

## 更多操作
- [标记管理](../tag)
- [分支管理](../branch)
- [合并请求](../merge-request)
- [持续集成](../continuous-integration)
