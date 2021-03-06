﻿+++
title = "发送设置"
weight = 1
description = "配置不同触发类型的发送规则"
+++

# 发送设置

发送设置用来选择某一个触发点对应选择的邮件模板、短信模板、站内信模板以及发送模式。用户可以根据需要，通过此功能，可以在忘记密码、添加/导入新用户、系统添加新功能、修改密码等过程中向不同成员发送邮件提醒。同时可以设置不同的邮件通知模式。


- **菜单层次**：全局层
- **菜单路径**：消息中心 > 发送设置
- **默认角色**：平台管理员

## 触发类型列表

列表字段：

- **触发类型**：由接收方的某些行为触发邮件发送的触发点类型。比如忘记密码、添加/导入新用户、系统添加新功能、修改密码等。
- **编码**：触发类型编码，具有唯一性，是触发类型的标识。
- 描述：对触发类型的触发情景、适用场景的描述。
- 默认邮件模板：接收方触发此类型触发点发送的邮件模板。
- 默认站内信模板：接收方触发此类型触发点发送的站内信模板。

下面是邮件模板发送可选择的触发条件。当触发相应条件后，对应邮箱会收到相应的邮件。

| 触发类型 | 编码 | 描述 |
| --- | --- | --- |
忘记密码 | forgetpassword | 用户触发忘记密码，发送验证邮件。(LDAP用户不允许重置密码)
添加/导入新用户 | adduser | 管理员添加或导入新用户时，新用户收到自己的账户信息
添加新功能 | addfunction | 系统添加新功能时，给用户发送新功能的介绍和操作指南
修改密码 | modifypassword | 用户在平台修改密码后反馈密码修改成功的通知，确认是否是用户的操作
注册组织 | registerOrganization | 新用户注册组织，发送邮箱验证进行验证
停用组织 | disableOrganization | 管理员停用组织，向成员发送通知
启用组织 | enableOrganization | 管理员启用组织，向成员发送通知
停用项目 | disableProject | 管理员停用项目，向成员发送通知
启用项目 | enableProject | 管理员启用项目，向成员发送通知
管理员添加/导入新用户 | addUser | 管理员添加或导入新用户时，管理员收到添加用户结果的反馈
问题创建 | issueCreate | 问题创建，给相关用户发送通知
问题分配 | issueAssignee | 问题分配，给相关用户发送通知
问题已解决 | issueSolve | 问题已解决，给相关用户发送通知
事务实例失败通知 | sagaInstanceFail | 当事务实例失败时，向触发者发送消息提醒



## 触发类型查询

可查询字段：

- 触发类型：触发类型的名称，可以模糊搜索。
- **编码**：触发类型的编码，是触发类型的标识，可以模糊搜索。

## 修改发送设置

1.点击`修改`→![修改发送设置](/docs/user-guide/system-configuration/message/image/update.png) 对该触发类型的发送设置进行修改。

2.选择对应的`默认邮件模板`；您可以在[邮件模板](../email-template)编写邮件模板。

3.选择`重发次数`、是否`及时发送`、是否`允许手动重发`。默认重发次数为3次，及时发送，允许手动重发。

4.选择对应的`默认站内信模板`；您可以在[站内信模板](../stationletter-template)编写站内信模板。

5.选择`站内信类型`,如果是`消息`类型，则显示在消息通知的消息页面。如果是`通知`类型，则显示在通知页面。

6.选择是否`允许配置接收`。如果允许，那么用户可以在`接收设置`页面配置接收此触发类型下的消息。

7.点击`保存`完成修改发送设置。

![修改发送设置](/docs/user-guide/system-configuration/message/image/update-send.png)


## 删除触发类型

- 点击`删除`按钮，删除不需要的触发类型。

<blockquote class="note">
       触发类型删除后，除非重新部署，否则不能恢复或者添加，请谨慎删除。
      </blockquote>

