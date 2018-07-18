---
title: 创建模型 - EF6
author: divega
ms.date: 2018-07-05
ms.prod: entity-framework
ms.author: divega
ms.manager: avickers
ms.technology: entity-framework-6
ms.topic: article
ms.assetid: 4890228E-CEA1-4595-B8AD-CA81253F8767
caps.latest.revision: 3
ms.openlocfilehash: e1eb4077a1fd77c66bb3e992e1d25a5de4fcc64c
ms.sourcegitcommit: 45494121254ad4fdcec613d1dd22d850068d6f39
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/08/2018
ms.locfileid: "37913507"
---
# <a name="creating-a-model"></a><span data-ttu-id="90a05-102">创建模型</span><span class="sxs-lookup"><span data-stu-id="90a05-102">Creating a Model</span></span>

<span data-ttu-id="90a05-103">EF 模型可存储有关应用程序类和属性如何映射到数据库表和列的详细信息。</span><span class="sxs-lookup"><span data-stu-id="90a05-103">An EF model stores the details about how application classes and properties map to database tables and columns.</span></span> <span data-ttu-id="90a05-104">创建 EF 模型有两种主要方式：</span><span class="sxs-lookup"><span data-stu-id="90a05-104">There are two main ways to create an EF model:</span></span>

- <span data-ttu-id="90a05-105">**使用 Code First**：开发者编写代码来指定模型。</span><span class="sxs-lookup"><span data-stu-id="90a05-105">**Using Code First**: The developer writes code to specify the model.</span></span> <span data-ttu-id="90a05-106">EF 基于实体类和开发者提供的其他模型配置，在运行时生成模型和映射。</span><span class="sxs-lookup"><span data-stu-id="90a05-106">EF generates the models and mappings at runtime based on entity classes and additional model configuration provided by the developer.</span></span>

- <span data-ttu-id="90a05-107">**使用 EF 设计器**：开发者使用 EF 设计器进行绘制以指定模型。</span><span class="sxs-lookup"><span data-stu-id="90a05-107">**Using the EF Designer**: The developer draws boxes and lines to specify the model using the EF Designer.</span></span> <span data-ttu-id="90a05-108">生成的模型以 XML 格式存储在具有 EDMX 扩展名的文件中。</span><span class="sxs-lookup"><span data-stu-id="90a05-108">The resulting model is stored as XML in a file with the EDMX extension.</span></span> <span data-ttu-id="90a05-109">应用程序域对象通常从概念模型中自动生成。</span><span class="sxs-lookup"><span data-stu-id="90a05-109">The application's domain objects are typically generated automatically from the conceptual model.</span></span>

## <a name="ef-workflows"></a><span data-ttu-id="90a05-110">EF 工作流</span><span class="sxs-lookup"><span data-stu-id="90a05-110">EF workflows</span></span>

<span data-ttu-id="90a05-111">这两种方式都可用于定位现有数据库或创建新数据库，最终会产生 4 种不同的工作流。</span><span class="sxs-lookup"><span data-stu-id="90a05-111">Both of these approaches can be used to target an existing database or create a new database, resulting in 4 different workflows.</span></span>
<span data-ttu-id="90a05-112">了解哪一种最适合：</span><span class="sxs-lookup"><span data-stu-id="90a05-112">Find out about which one is best for you:</span></span>  

|                                           | <span data-ttu-id="90a05-113">我只想编写代码...</span><span class="sxs-lookup"><span data-stu-id="90a05-113">I just want to write code...</span></span>                                                                                                                   | <span data-ttu-id="90a05-114">我想要使用设计器...</span><span class="sxs-lookup"><span data-stu-id="90a05-114">I want to use a designer...</span></span>                                                                                                                        |
|:------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------|:---------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="90a05-115">**我正在创建新数据库**</span><span class="sxs-lookup"><span data-stu-id="90a05-115">**I am creating a new database**</span></span>          | [<span data-ttu-id="90a05-116">使用 Code First 在代码中定义模型，然后生成数据库。</span><span class="sxs-lookup"><span data-stu-id="90a05-116">Use **Code First** to define your model in code and then generate a database.</span></span>](~/ef6/modeling/code-first/workflows/new-database.md)           | [<span data-ttu-id="90a05-117">通过 Model First 使用框和线定义模型，然后生成数据库。</span><span class="sxs-lookup"><span data-stu-id="90a05-117">Use **Model First** to define your model using boxes and lines and then generate a database.</span></span>](~/ef6/modeling/designer/workflows/model-first.md)   |
| <span data-ttu-id="90a05-118">**我需要访问现有数据库**</span><span class="sxs-lookup"><span data-stu-id="90a05-118">**I need to access an existing database**</span></span> | [<span data-ttu-id="90a05-119">使用 Code First 创建映射到现有数据库的基于代码的模型。</span><span class="sxs-lookup"><span data-stu-id="90a05-119">Use **Code First** to create a code based model that maps to an existing database.</span></span>](~/ef6/modeling/code-first/workflows/existing-database.md) | [<span data-ttu-id="90a05-120">使用 Database First 创建映射到现有数据库的框和线模型。</span><span class="sxs-lookup"><span data-stu-id="90a05-120">Use **Database First** to create a boxes and lines model that maps to an existing database.</span></span>](~/ef6/modeling/designer/workflows/database-first.md) |

### <a name="watch-the-video-what-ef-workflow-should-i-use"></a><span data-ttu-id="90a05-121">观看视频：我应该使用哪种 EF 工作流？</span><span class="sxs-lookup"><span data-stu-id="90a05-121">Watch the video: What EF workflow should I use?</span></span>

<span data-ttu-id="90a05-122">这段短片介绍了其中的差异，以及如何找到适合的工作流。</span><span class="sxs-lookup"><span data-stu-id="90a05-122">This short video explains the differences, and how to find the one that is right for you.</span></span>

<span data-ttu-id="90a05-123">**主讲人**：[Rowan Miller](http://romiller.com/)</span><span class="sxs-lookup"><span data-stu-id="90a05-123">**Presented By**: [Rowan Miller](http://romiller.com/)</span></span>

<span data-ttu-id="90a05-124">![WhichWorkflow_Thumb](../media/whichworkflow-thumb.png) [WMV](http://download.microsoft.com/download/8/F/8/8F81F4CD-3678-4229-8D79-0C63FFA3C595/HDI_ITPro_Technet_winvideo_ChoseYourWorkflow.wmv) | [MP4](http://download.microsoft.com/download/8/F/8/8F81F4CD-3678-4229-8D79-0C63FFA3C595/HDI_ITPro_Technet_mp4video_ChoseYourWorkflow.m4v) | [WMV (ZIP)](http://download.microsoft.com/download/8/F/8/8F81F4CD-3678-4229-8D79-0C63FFA3C595/HDI_ITPro_Technet_winvideo_ChoseYourWorkflow.zip)</span><span class="sxs-lookup"><span data-stu-id="90a05-124">![WhichWorkflow_Thumb](../media/whichworkflow-thumb.png) [WMV](http://download.microsoft.com/download/8/F/8/8F81F4CD-3678-4229-8D79-0C63FFA3C595/HDI_ITPro_Technet_winvideo_ChoseYourWorkflow.wmv) | [MP4](http://download.microsoft.com/download/8/F/8/8F81F4CD-3678-4229-8D79-0C63FFA3C595/HDI_ITPro_Technet_mp4video_ChoseYourWorkflow.m4v) | [WMV (ZIP)](http://download.microsoft.com/download/8/F/8/8F81F4CD-3678-4229-8D79-0C63FFA3C595/HDI_ITPro_Technet_winvideo_ChoseYourWorkflow.zip)</span></span>

<span data-ttu-id="90a05-125">如果在观看视频后仍无法顺利决定使用 EF 设计器还是 Code First，那么分别请了解两者！</span><span class="sxs-lookup"><span data-stu-id="90a05-125">If after watching the video you still don't feel comfortable deciding if you want to use the EF Designer or Code First, learn both!</span></span>

## <a name="a-look-under-the-hood"></a><span data-ttu-id="90a05-126">查看二者的本质区别</span><span class="sxs-lookup"><span data-stu-id="90a05-126">A look under the hood</span></span>

<span data-ttu-id="90a05-127">无论是使用 Code First 还是 EF 设计器，EF 模型始终具有以下几个组件：</span><span class="sxs-lookup"><span data-stu-id="90a05-127">Regardless of whether you use Code First or the EF Designer, an EF model always has several components:</span></span>

- <span data-ttu-id="90a05-128">应用程序域对象或实体类型本身。</span><span class="sxs-lookup"><span data-stu-id="90a05-128">The application's domain objects or entity types themselves.</span></span> <span data-ttu-id="90a05-129">这通常称为对象层</span><span class="sxs-lookup"><span data-stu-id="90a05-129">This is often referred to as the object layer</span></span>

- <span data-ttu-id="90a05-130">使用[实体数据模型](~/ef6/resources/glossary.md#entity-data-model)描述的，由特定于域的实体类型和关系组成的概念模型。</span><span class="sxs-lookup"><span data-stu-id="90a05-130">A conceptual model consisting of domain-specific entity types and relationships, described using the [Entity Data Model](~/ef6/resources/glossary.md#entity-data-model).</span></span> <span data-ttu-id="90a05-131">该层通常用字母“C”表示概念。</span><span class="sxs-lookup"><span data-stu-id="90a05-131">This layer is often referred to with the letter "C", for _conceptual_.</span></span>

- <span data-ttu-id="90a05-132">表示数据库中定义的表、列和关系的存储模型。</span><span class="sxs-lookup"><span data-stu-id="90a05-132">A storage model representing tables, columns and relationships as defined in the database.</span></span> <span data-ttu-id="90a05-133">该层通常用字母“S”表示存储。</span><span class="sxs-lookup"><span data-stu-id="90a05-133">This layer is often referred to with the later "S", for _storage_.</span></span>  

- <span data-ttu-id="90a05-134">概念模型和数据库架构之间的映射。</span><span class="sxs-lookup"><span data-stu-id="90a05-134">A mapping between the conceptual model and the database schema.</span></span> <span data-ttu-id="90a05-135">该映射通常称为“C-S”映射。</span><span class="sxs-lookup"><span data-stu-id="90a05-135">This mapping is often referred to as "C-S" mapping.</span></span>

<span data-ttu-id="90a05-136">EF 的映射引擎利用“C-S”映射将针对实体的操作（例如创建、读取、更新和删除）转换为针对数据库中的表的等效操作。</span><span class="sxs-lookup"><span data-stu-id="90a05-136">EF's mapping engine leverages the "C-S" mapping to transform operations against entities - such as create, read, update, and delete - into equivalent operations against tables in the database.</span></span>

<span data-ttu-id="90a05-137">概念模型和应用程序的对象之间的映射通常称为“O-C”映射。</span><span class="sxs-lookup"><span data-stu-id="90a05-137">The mapping between the conceptual model and the application's objects is often referred to as "O-C" mapping.</span></span> <span data-ttu-id="90a05-138">与“C-S”映射相比，“O-C”映射是一对一的隐式映射：概念模型中定义的实体、属性和关系需要与 .NET 对象的形状和类型相匹配。</span><span class="sxs-lookup"><span data-stu-id="90a05-138">Compared to the "C-S" mapping, "O-C" mapping is implicit and one-to-one: entities, properties and relationships defined in the conceptual model are required to match the shapes and types of the .NET objects.</span></span> <span data-ttu-id="90a05-139">从 EF4 及更高版本开始，对象层可以由具有属性的简单对象组成，无需任何 EF 依赖关系。</span><span class="sxs-lookup"><span data-stu-id="90a05-139">From EF4 and beyond, the objects layer can be composed of simple objects with properties without any dependencies on EF.</span></span> <span data-ttu-id="90a05-140">这些通常称为简单传统 CLR 对象 (POCO)，同时类型和属性映射以名称匹配约定为基础进行。</span><span class="sxs-lookup"><span data-stu-id="90a05-140">These are usually referred to as Plain-Old CLR Objects (POCO) and mapping of types and properties is performed base on name matching conventions.</span></span> <span data-ttu-id="90a05-141">以前，在 EF 3.5 中，对象层存在特定限制，例如实体必须派生自 EntityObject 类，并且必须带有 EF 属性以实现“O-C”映射。</span><span class="sxs-lookup"><span data-stu-id="90a05-141">Previously, in EF 3.5 there were specific restrictions for the object layer, like entities having to derive from the EntityObject class and having to carry EF attributes to implement the "O-C" mapping.</span></span>