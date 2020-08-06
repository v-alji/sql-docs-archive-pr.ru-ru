---
title: Задача "Реорганизация индекса" | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.reorganizeindextask.f1
helpviewer_keywords:
- reorganizing indexes
- Reorganize Index task [Integration Services]
- indexes [Integration Services]
ms.assetid: 9ed87861-e5c3-4fcd-8760-d112f4c0af0c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 3f910391bd3a5a35770bb677bc17c91a00ace457
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665476"
---
# <a name="reorganize-index-task"></a><span data-ttu-id="86c99-102">Задача «Реорганизация индекса»</span><span class="sxs-lookup"><span data-stu-id="86c99-102">Reorganize Index Task</span></span>
  <span data-ttu-id="86c99-103">Задача «Реорганизация индекса» перестраивает индексы в таблицах и представлениях базы данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="86c99-103">The Reorganize Index task reorganizes indexes in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database tables and views.</span></span> <span data-ttu-id="86c99-104">Дополнительные сведения об управлении индексами см. в разделе [Реорганизация и перестроение индексов](../../relational-databases/indexes/reorganize-and-rebuild-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="86c99-104">For more information about managing indexes, see [Reorganize and Rebuild Indexes](../../relational-databases/indexes/reorganize-and-rebuild-indexes.md).</span></span>  
  
 <span data-ttu-id="86c99-105">Используя задачу «Реорганизация индекса», пакет может перестроить индексы в одной или нескольких базах данных.</span><span class="sxs-lookup"><span data-stu-id="86c99-105">By using the Reorganize Index task, a package can reorganize indexes in a single database or multiple databases.</span></span> <span data-ttu-id="86c99-106">Если задача перестраивает индексы только одной базы данных, можно выбрать представления или таблицы, чьи индексы будут реорганизованы.</span><span class="sxs-lookup"><span data-stu-id="86c99-106">If the task reorganizes only the indexes in a single database, you can choose the views or the tables whose indexes the task reorganizes.</span></span> <span data-ttu-id="86c99-107">Задача «Реорганизация индекса» также содержит параметр сжатия больших объектов данных.</span><span class="sxs-lookup"><span data-stu-id="86c99-107">The Reorganize Index task also includes an option to compact large object data.</span></span> <span data-ttu-id="86c99-108">Большой объект данных — это данные, содержащие значение типа данных `image`, `text`, `ntext`, `varchar(max)`, `nvarchar(max)`, `varbinary(max)` или `xml`.</span><span class="sxs-lookup"><span data-stu-id="86c99-108">Large object data is data with the `image`, `text`, `ntext`, `varchar(max)`, `nvarchar(max)`, `varbinary(max)`, or `xml` data type.</span></span> <span data-ttu-id="86c99-109">Дополнительные сведения см. в разделе [Типы данных (Transact-SQL)](/sql/t-sql/data-types/data-types-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="86c99-109">For more information, see [Data Types &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql).</span></span>  
  
 <span data-ttu-id="86c99-110">Задача «Реорганизация индекса» содержит инструкцию Transact-SQL ALTER INDEX.</span><span class="sxs-lookup"><span data-stu-id="86c99-110">The Reorganize Index task encapsulates the Transact-SQL ALTER INDEX statement.</span></span> <span data-ttu-id="86c99-111">Если необходимо сжать большой объект данных, инструкция использует предложение REORGANIZE WITH (LOB_COMPACTION = ON), иначе значение LOB_COMPACTION устанавливается в OFF.</span><span class="sxs-lookup"><span data-stu-id="86c99-111">If you choose to compact large object data, the statement uses the REORGANIZE WITH (LOB_COMPACTION = ON) clause, otherwise LOB_COMPACTION is set to OFF.</span></span> <span data-ttu-id="86c99-112">Дополнительные сведения см. в разделе [ALTER INDEX (Transact-SQL)](/sql/t-sql/statements/alter-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="86c99-112">For more information, see [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="86c99-113">Время, необходимое на создание инструкции Transact-SQL, которая будет выполнена задачей, пропорционально количеству индексов, которые необходимо перестроить.</span><span class="sxs-lookup"><span data-stu-id="86c99-113">The time the task takes to create the Transact-SQL statement that the task runs is proportionate to the number of indexes the task reorganizes.</span></span> <span data-ttu-id="86c99-114">Если задача настроена на перестроение всех таблиц и представлений базы данных, которая содержит большое количество индексов, или нужно перестроить индексы нескольких баз данных, то создание инструкции Transact-SQL может занять значительное время.</span><span class="sxs-lookup"><span data-stu-id="86c99-114">If the task is configured to reorganize indexes in all the tables and views in a database that holds a large number of indexes, or to reorganize indexes in multiple databases, the task can take a considerable amount of time to generate the Transact-SQL statement.</span></span>  
  
## <a name="configuration-of-the-reorganize-index-task"></a><span data-ttu-id="86c99-115">Настройка задачи «Реорганизация индекса»</span><span class="sxs-lookup"><span data-stu-id="86c99-115">Configuration of the Reorganize Index Task</span></span>  
 <span data-ttu-id="86c99-116">Свойства задаются с помощью конструктора служб [!INCLUDE[ssIS](../../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="86c99-116">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="86c99-117">Эта задача находится в разделе **Задачи плана обслуживания** **области элементов** в конструкторе служб [!INCLUDE[ssIS](../../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="86c99-117">This task is in the **Maintenance Plan Tasks** section of the **Toolbox** in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="86c99-118">Дополнительные сведения о свойствах, которые можно задать в конструкторе служб [!INCLUDE[ssIS](../../../includes/ssis-md.md)] , см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="86c99-118">For information about the properties that you can set in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="86c99-119">Задача "Реорганизация индекса" (план обслуживания)</span><span class="sxs-lookup"><span data-stu-id="86c99-119">Reorganize Index Task &#40;Maintenance Plan&#41;</span></span>](../../relational-databases/maintenance-plans/reorganize-index-task-maintenance-plan.md)  
  
## <a name="related-tasks"></a><span data-ttu-id="86c99-120">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="86c99-120">Related Tasks</span></span>  
 <span data-ttu-id="86c99-121">Дополнительные сведения о настройке свойств этих свойств в конструкторе [!INCLUDE[ssIS](../../../includes/ssis-md.md)] см. в разделе [Задание свойств задач или контейнеров](../set-the-properties-of-a-task-or-container.md).</span><span class="sxs-lookup"><span data-stu-id="86c99-121">For more information about how to set these properties in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, see [Set the Properties of a Task or Container](../set-the-properties-of-a-task-or-container.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86c99-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="86c99-122">See Also</span></span>  
 <span data-ttu-id="86c99-123">[Задачи служб Integration Services](integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="86c99-123">[Integration Services Tasks](integration-services-tasks.md) </span></span>  
 [<span data-ttu-id="86c99-124">Поток управления</span><span class="sxs-lookup"><span data-stu-id="86c99-124">Control Flow</span></span>](control-flow.md)  
  
  
