---
title: "EF Core 和 EF6 逐个功能比较"
author: rowanmiller
ms.author: divega
ms.date: 10/27/2016
ms.assetid: f22f29ef-efc0-475d-b0b2-12a054f80f95
uid: efcore-and-ef6/features
ms.openlocfilehash: 696ff2c8ec788c08880ecb3b07e10dc081b0323b
ms.sourcegitcommit: 01a75cd483c1943ddd6f82af971f07abde20912e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2017
---
# <a name="ef-core-and-ef6-feature-by-feature-comparison"></a>EF Core 和 EF6 逐个功能比较

下表比较了 EF Core 和 EF6 中可用的功能。 该表仅在高级别进行比较，并没有列出每个功能，也没有提供相同功能之间可能的差异详细信息。

EF Core 列包含功能首次出现的产品版本号。

| 创建模型 |EF 6 |EF Core |
|-|-|-|
| 基本类映射                         | 是 | 1.0 |
| 约定                                 | 是 | 1.0 |
| 自定义约定                          | 是 | 1.0（部分） |
| 数据注释                            | 是 | 1.0 |
| Fluent API                                  | 是 | 1.0 |
| 继承：每个层次结构一张表 (TPH)      | 是 | 1.0 |
| 继承：每个类型一张表 (TPT)           | 是 |     |
| 继承：每个具体类一张表 (TPC) | 是 |     |
| 阴影状态属性                     |     | 1.0 |
| 备用键                              |     | 1.0 |
| 多对多，无联接实体            | 是 |     |
| 密钥生成：数据库                    | 是 | 1.0 |
| 密钥生成：客户端                      |     | 1.0 |
| 复杂/已拥有类型                         | 是 | 2.0 |
| 空间数据                                | 是 |     |
| 模型的图形可视化效果            | 是 |     |
| 图形模型编辑器                      | 是 |     |
| 模型格式：代码                          | 是 | 1.0 |
| 模型格式：EDMX (XML)                    | 是 |     |
| 从数据库创建模型：命令行    | 是 | 1.0 |
| 从数据库创建模型：VS 向导       | 是 |     |
| 从数据库更新模型                  | 部分 | |
| 全局查询筛选器                        |     | 2.0 |
| 表拆分                             | 是 | 2.0 |
| 实体拆分                            | 是 |     |
| 数据库标量函数映射            | 较差 | 2.0 |
| 字段映射                               |     | 1.1 |
| | | |
| 查询数据 |EF6 |EF Core |
| LINQ 查询                                | 是 | 1.0（进行中，针对复杂查询） |
| 可读内容生成的 SQL                      | 较差 | 1.0 |
| 混合客户端/服务器评估              |     | 1.0 |
| 加载相关数据：预先加载                 | 是 | 1.0 |
| 加载相关数据：延迟加载                  | 是 |     |
| 加载相关数据：显式加载              | 是 | 1.1 |
| 原始 SQL 查询：模型类型                | 是 | 1.0 |
| 原始 SQL 查询：非模型类型            | 是 |     |
| 原始 SQL 查询：使用 LINQ 编写        |     | 1.0 |
| 显式编译的查询                 | 较差 | 2.0 |
| | | |
| **保存数据** |EF6 |EF Core |
| 更改跟踪：快照                   | 是 | 1.0 |
| 更改追踪：通知               | 是 | 1.0 |
| 访问跟踪的状态                     | 是 | 1.0 |
| 开放式并发                      | 是 | 1.0 |
| 事务                                | 是 | 1.0 |
| 批处理语句                      |     | 1.0 |
| 存储过程                            | 是 |     |
| 断开连接低级别 API 图形           | 较差 | 1.0 |
| 断开连接端到端图形               |     | 1.0（部分） |
| | | |
| 其他功能 |EF6 |EF Core |
| 迁移                                  | 是 | 1.0 |
| 数据库创建/删除 API             | 是 | 1.0 |
| 种子数据                                   | 是 |     |
| 连接复原                       | 是 | 1.1 |
| 生命周期挂钩（事件、截取）      | 是 |     |
| DbContext 池                           |     | 2.0 |
| | | |
| 数据库提供程序 |EF6|EF Core |
| SQL Server                                  | 是 | 1.0 |
| MySQL                                       | 是 | 1.0 |
| postgresql                                  | 是 | 1.0 |
| Oracle                                      | 是 | 1.0（仅限付费版本<sup>(1)</sup>） |
| SQLite                                      | 是 | 1.0 |
| SQL Compact                                 | 是 | 1.0 <sup>(2)</sup> |
| DB2                                         | 是 |     |
| 内存中（用于测试）                      |     | 1.0 |
| | | |
| 平台 |EF6 |EF Core |
| .NET framework（控制台、WinForms、WPF、ASP.NET） | 是 | 1.0 |
| .NET Core（控制台、ASP.NET Core）           |     | 1.0 |
| Mono 和 Xamarin                              |     | 1.0（进行中） |
| UWP                                         |     | 1.0（进行中） |

<sup>1</sup>适用于 Oracle 的免费官方提供程序目前正在开发中。
<sup>2</sup>SQL Server Compact 提供程序仅适用于 .NET Framework（而不是 .NET Core）。