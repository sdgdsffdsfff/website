+++
title = "版本报告"
description = "显示您的团队在完成一个版本方面的进展，监控此版本是否按时发布，以便工作滞后时能采取行动。"
weight = 4
+++

# 版本报告

[版本](../../../agile/backlog/version/)报告显示您的团队在完成一个版本方面的进展，基于团队自版本开始以来的平均进度（速度），以及剩余工作量的估计量。这样有助于您监控此版本是否按时发布，以便工作滞后时能采取行动。

 {{< note >}} 此图表以`剩余预估时间`、`故事点`、`问题计数`作为统计单位，请在相应问题中提前设置好`剩余预估时间`和`故事点`。{{< /note >}}

## 操作步骤

* 选择报告
    1. 点击`报告`
    2. 选择`版本报告`
* 切换报告
    1. 点击`切换报表`按钮
    2. 选择`累积流量图`或其他报表

## 报告说明

选择版本，下拉框选择查看当前项目下所有的版本

### 图表
- 横坐标代表时间
- 左侧纵坐标代表故事点，右侧纵坐标代表百分比
- 图表中统计的数据：
    - `总计故事点`：版本下的问题故事点总和
    - `已完成故事点`：版本下的已完成问题故事点总和
    - `未预估问题的百分比`：版本下的未预估问题占问题总数的百分比

    ![image](/docs/user-guide/agile/report/img/version.png)

### 报告详情

- **报告详情模块**
    - `已完成的问题`:当版本中的问题已完成，则此问题将归类于此项。
    - `未完成的问题`:当版本中的问题未完成，并且已预估故事点（问题类型为故事）或时间（其他类型的问题），则此问题将归类于此项。
    - `未完成的未预估问题`:当版本中的问题未完成，并且未预估故事点（问题类型为故事）或时间（其他类型的问题），则此问题将归类于此项。

- **字段描述**
    - `关键字`：表示问题编号
    - `概要`：表示问题概要
    - `问题类型`：表示问题类型，包括史诗、故事、任务、缺陷
    - `优先级`：表示问题优先级，包括高、中、低
    - `状态`：表示问题关联的状态
    - `故事点`：如果问题类型是故事，将显示该问题的故事点。其他类型不显示该字段 

- **图表过程**
    - 当版本创建后，就可以在版本报告中查看该版本的报告信息。
    - 版本报告统计开始时间规则：若版本设置了开始时间，则报告从此时间开始统计；若版本未设置开始时间，则报告的统计开始时间   是此版本创建的时间。
    - issue是否完成是根据issue是否在看板中`设置为已完成`的状态来判定。
    - issue故事点或剩余时间发生变化、状态由已完成变为未完成或由未完成变为已完成、issue移入版本或移出版本都将会引起版本报告的变化，即当天的统计数据将发生改变。
    - 版本报告可以通过“单位“下拉选择框选择故事点、剩余时间、问题计数中的任一维度查看对应报告统计信息
    - 版本报告统计结束时间规则：若版本存在发布时间，则版本报告统计结束时间为版本发布时间；若版本不存在发布时间，则版本报告统计结束时间为当前时间                                                                           
{{< note >}}
若版本归档后，在版本报告中将找不到此版本的版本报告。
{{< /note >}}

## 其他报表

- [累积流量图](../cumulative-flow)
- [冲刺报告](../sprint)
- [燃尽图](../burn-down)
- [迭代速度图](../iterative-chart)
- [史诗报告](../epic-report)
- [统计图](../statistical)
- [史诗燃耗图](../epicburndown)
- [版本燃耗图](../versionburndown)