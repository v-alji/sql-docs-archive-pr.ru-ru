---
title: Определение измерений базы данных | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- dimensions [Analysis Services], defining
ms.assetid: fe84588b-66a3-4100-a1cf-59b21b7adf01
author: minewiskan
ms.author: owend
ms.openlocfilehash: ad5334e71b0f133f80933a7d1702d8ada7565501
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728886"
---
# <a name="define-database-dimensions"></a><span data-ttu-id="44ce1-102">Определение измерений базы данных</span><span class="sxs-lookup"><span data-stu-id="44ce1-102">Define Database Dimensions</span></span>
  <span data-ttu-id="44ce1-103">Используйте конструктор измерений в [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] для настройки существующего измерения базы данных в [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] проекте или базе данных.</span><span class="sxs-lookup"><span data-stu-id="44ce1-103">Use Dimension Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] to configure an existing database dimension in a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project or database.</span></span> <span data-ttu-id="44ce1-104">Конструктор измерений позволяет выполнять следующие функции.</span><span class="sxs-lookup"><span data-stu-id="44ce1-104">You can use Dimension Designer to do the following:</span></span>  
  
-   <span data-ttu-id="44ce1-105">Настройка свойств уровня измерений.</span><span class="sxs-lookup"><span data-stu-id="44ce1-105">Configure the dimension-level properties.</span></span>  
  
-   <span data-ttu-id="44ce1-106">Добавление и настройка атрибутов измерений.</span><span class="sxs-lookup"><span data-stu-id="44ce1-106">Add and configure dimension attributes.</span></span>  
  
-   <span data-ttu-id="44ce1-107">Определение и настройка пользовательских иерархий.</span><span class="sxs-lookup"><span data-stu-id="44ce1-107">Define and configure user-defined hierarchies.</span></span>  
  
-   <span data-ttu-id="44ce1-108">Определение и настройка связей между атрибутами.</span><span class="sxs-lookup"><span data-stu-id="44ce1-108">Define and configure relationships between attributes.</span></span>  
  
-   <span data-ttu-id="44ce1-109">Определение переводов измерений.</span><span class="sxs-lookup"><span data-stu-id="44ce1-109">Define dimension translations.</span></span>  
  
-   <span data-ttu-id="44ce1-110">Можно просматривать структуру и данные обработанных измерений.</span><span class="sxs-lookup"><span data-stu-id="44ce1-110">For processed dimensions, you can browse the dimension structure and view data.</span></span>  
  
 <span data-ttu-id="44ce1-111">Чтобы после изменения атрибута, измерения или иерархии увидеть изменения, необходимо обработать измерение.</span><span class="sxs-lookup"><span data-stu-id="44ce1-111">After you modify a dimension, attribute, or hierarchy, you must process that dimension to view the changes.</span></span> <span data-ttu-id="44ce1-112">В режиме проекта перед обработкой необходимо выполнить развертывание изменений в экземпляр служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="44ce1-112">When working in project mode, you deploy the changes to the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance before processing.</span></span>  
  
 <span data-ttu-id="44ce1-113">Дополнительные сведения об открытии измерения в конструкторе измерений см. в разделе [Изменение или удаление измерения базы данных в обозревателе решений](database-dimensions-modify-or-delete-a-database-dimension-in-solution-explorer.md).</span><span class="sxs-lookup"><span data-stu-id="44ce1-113">For more information about how to open a dimension in Dimension Designer, see [Modify or Delete a Database Dimension in Solution Explorer](database-dimensions-modify-or-delete-a-database-dimension-in-solution-explorer.md).</span></span>  
  
 <span data-ttu-id="44ce1-114">В конструкторе измерений есть три различные вкладки, каждая из которых описывается в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="44ce1-114">Dimension Designer has three different tabs, which are described in the following table.</span></span>  
  
|<span data-ttu-id="44ce1-115">Вкладка</span><span class="sxs-lookup"><span data-stu-id="44ce1-115">Tab</span></span>|<span data-ttu-id="44ce1-116">Описание</span><span class="sxs-lookup"><span data-stu-id="44ce1-116">Description</span></span>|  
|---------|-----------------|  
|<span data-ttu-id="44ce1-117">**Структура измерения**</span><span class="sxs-lookup"><span data-stu-id="44ce1-117">**Dimension Structure**</span></span>|<span data-ttu-id="44ce1-118">Эта вкладка используется для работы со структурой измерения — для проверки или создания схемы представления источников данных для измерения, работы с атрибутами и для организации атрибутов в пользовательских иерархиях.</span><span class="sxs-lookup"><span data-stu-id="44ce1-118">Use this tab to work with the structure of a dimension-to examine or create the data source view schema for a dimension, to work with attributes, and to organize attributes in user-defined hierarchies.</span></span>|  
|<span data-ttu-id="44ce1-119">**можно изменить расположение фигур на вкладке**</span><span class="sxs-lookup"><span data-stu-id="44ce1-119">**Attribute Relationships**</span></span>|<span data-ttu-id="44ce1-120">Эта вкладка используется для создания, изменения и удаления связей атрибутов в измерении.</span><span class="sxs-lookup"><span data-stu-id="44ce1-120">Use this tab to create, modify, or delete the attribute relationships of a dimension.</span></span>|  
|<span data-ttu-id="44ce1-121">**Translations**</span><span class="sxs-lookup"><span data-stu-id="44ce1-121">**Translations**</span></span>|<span data-ttu-id="44ce1-122">Эта вкладка предназначена для добавления переводов метаданных измерений на разных языках и их изменения.</span><span class="sxs-lookup"><span data-stu-id="44ce1-122">Use this tab to add and edit translations of dimension metadata in different languages.</span></span>|  
|<span data-ttu-id="44ce1-123">**Браузер**</span><span class="sxs-lookup"><span data-stu-id="44ce1-123">**Browser**</span></span>|<span data-ttu-id="44ce1-124">Эта вкладка предназначена для изучения элементов обработанного измерения и просмотра переводов метаданных измерений.</span><span class="sxs-lookup"><span data-stu-id="44ce1-124">Use this tab to examine the members of a processed dimension and to review translations of dimension metadata.</span></span>|  
  
 <span data-ttu-id="44ce1-125">В следующих подразделах описываются задачи, которые можно выполнять в конструкторе измерений.</span><span class="sxs-lookup"><span data-stu-id="44ce1-125">The following topics describe the tasks that you can perform in Dimension Designer.</span></span>  
  
 [<span data-ttu-id="44ce1-126">Справочник по свойствам атрибута измерения</span><span class="sxs-lookup"><span data-stu-id="44ce1-126">Dimension Attribute Properties Reference</span></span>](dimension-attribute-properties-reference.md)  
 <span data-ttu-id="44ce1-127">Описывает настройку и определение атрибутов измерения.</span><span class="sxs-lookup"><span data-stu-id="44ce1-127">Describes how to define and configure a dimension attribute.</span></span>  
  
 [<span data-ttu-id="44ce1-128">Создание пользовательских иерархий</span><span class="sxs-lookup"><span data-stu-id="44ce1-128">Create User-Defined Hierarchies</span></span>](user-defined-hierarchies-create.md)  
 <span data-ttu-id="44ce1-129">Описывает определение и настройку пользовательской иерархии.</span><span class="sxs-lookup"><span data-stu-id="44ce1-129">Describes how to define and configure a user-defined hierarchy.</span></span>  
  
 [<span data-ttu-id="44ce1-130">Определение связей атрибутов</span><span class="sxs-lookup"><span data-stu-id="44ce1-130">Define Attribute Relationships</span></span>](attribute-relationships-define.md)  
 <span data-ttu-id="44ce1-131">Описывает настройку и определение связи атрибутов.</span><span class="sxs-lookup"><span data-stu-id="44ce1-131">Describes how to define and configure an attribute relationship.</span></span>  
  
 [<span data-ttu-id="44ce1-132">Использование мастера бизнес-аналитики для улучшения измерений</span><span class="sxs-lookup"><span data-stu-id="44ce1-132">Use the Business Intelligence Wizard to Enhance Dimensions</span></span>](../use-the-business-intelligence-wizard-to-enhance-dimensions.md)  
 <span data-ttu-id="44ce1-133">Описывает использование мастера бизнес-аналитики для улучшения измерения.</span><span class="sxs-lookup"><span data-stu-id="44ce1-133">Describes how to use the Business Intelligence Wizard to enhance a dimension.</span></span>  
  
  
