---
title: Задача "Перестроение индекса" | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.rebuildindextask.f1
helpviewer_keywords:
- rebuilding indexes
- indexes [Integration Services]
- Rebuild Index task
ms.assetid: 021884dd-e72d-47b2-99e8-b741410509c3
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 33bbe25bc8c47f4f749f95dbb7096c3a76c25297
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665478"
---
# <a name="rebuild-index-task"></a><span data-ttu-id="e5abc-102">задача «Перестроение индекса»</span><span class="sxs-lookup"><span data-stu-id="e5abc-102">Rebuild Index Task</span></span>
  <span data-ttu-id="e5abc-103">Задача «Перестроение индекса» перестраивает индекс в таблицах или представлениях базы данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e5abc-103">The Rebuild Index task rebuilds indexes in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database tables and views.</span></span> <span data-ttu-id="e5abc-104">Дополнительные сведения об управлении индексами см. в разделе [Реорганизация и перестроение индексов](../../relational-databases/indexes/reorganize-and-rebuild-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="e5abc-104">For more information about managing indexes, see [Reorganize and Rebuild Indexes](../../relational-databases/indexes/reorganize-and-rebuild-indexes.md).</span></span>  
  
 <span data-ttu-id="e5abc-105">При помощи задачи «Перестроение индекса» пакет может перестроить индексы в одной или нескольких базах данных.</span><span class="sxs-lookup"><span data-stu-id="e5abc-105">By using the Rebuild Index task, a package can rebuild indexes in a single database or multiple databases.</span></span> <span data-ttu-id="e5abc-106">Если задача перестраивает индексы только одной базы данных, можно выбрать представления и таблицы, индексы которых данная задача перестраивает.</span><span class="sxs-lookup"><span data-stu-id="e5abc-106">If the task rebuilds only the indexes in a single database, you can choose the views and tables whose indexes the task rebuilds.</span></span>  
  
 <span data-ttu-id="e5abc-107">Эта задача содержит инструкцию ALTER INDEX REBUILD со следующими параметрами перестроения индекса.</span><span class="sxs-lookup"><span data-stu-id="e5abc-107">This task encapsulates an ALTER INDEX REBUILD statement with the following index rebuild options:</span></span>  
  
-   <span data-ttu-id="e5abc-108">Определите значение коэффициента FILLFACTOR или используйте исходное значение FILLFACTOR.</span><span class="sxs-lookup"><span data-stu-id="e5abc-108">Specify a FILLFACTOR percentage or use the original FILLFACTOR amount.</span></span>  
  
-   <span data-ttu-id="e5abc-109">Установите значение PAD_INDEX = ON для выделения свободного места, которое определяется с помощью FILLFACTOR для страниц индекса промежуточного уровня.</span><span class="sxs-lookup"><span data-stu-id="e5abc-109">Set PAD_INDEX = ON to allocate the free space specified by FILLFACTOR to the intermediate-level pages of the index.</span></span>  
  
-   <span data-ttu-id="e5abc-110">Установите значение SORT_IN_TEMPDB = ON для сохранения промежуточных результатов сортировки, используемых для перестроения индекса в базе данных tempdb.</span><span class="sxs-lookup"><span data-stu-id="e5abc-110">Set SORT_IN_TEMPDB = ON to store the intermediate sort result used to rebuild the index in tempdb.</span></span> <span data-ttu-id="e5abc-111">Если этот параметр установлен в положение OFF, результат сохраняется в ту же базу данных, что и индекс.</span><span class="sxs-lookup"><span data-stu-id="e5abc-111">When the intermediate sort result is set to OFF, the result is stored in the same database as the index.</span></span>  
  
-   <span data-ttu-id="e5abc-112">Установите значение IGNORE_DUP_KEY = ON, чтобы разрешить операциям многострочной вставки, которые включают в себя записи, нарушающие ограничения уникальности, вставлять те из записей, которые не нарушают этих ограничений.</span><span class="sxs-lookup"><span data-stu-id="e5abc-112">Set IGNORE_DUP_KEY = ON to allow a multirow insert operation that includes records that violate unique constraints to insert the records that do not violate the unique constraints.</span></span>  
  
-   <span data-ttu-id="e5abc-113">Установите значение ONLINE = ON для отмены блокировки таблицы, что позволяет производить запросы и обновления базовой таблицы во время повторного индексирования.</span><span class="sxs-lookup"><span data-stu-id="e5abc-113">Set ONLINE = ON to not hold table locks so that queries or updates to the underlying table can proceed during re-indexing.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e5abc-114">Операции с индексами в сети доступны не во всех выпусках [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e5abc-114">Online index operations are not available in every edition of [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="e5abc-115">Перечень функций, поддерживаемых в разных выпусках [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], см. в разделе [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="e5abc-115">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
 <span data-ttu-id="e5abc-116">Дополнительные сведения об инструкции ALTER INDEX и параметрах перестроения индекса см. в разделе [ALTER INDEX (Transact-SQL)](/sql/t-sql/statements/alter-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e5abc-116">For more information about the ALTER INDEX statement and index rebuild options, see [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="e5abc-117">Время, необходимое задаче для создания инструкции [!INCLUDE[tsql](../../includes/tsql-md.md)] , пропорционально числу индексов, которые задача перестраивает.</span><span class="sxs-lookup"><span data-stu-id="e5abc-117">The time the task takes to create the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement that the task runs is proportionate to the number of indexes the task rebuilds.</span></span> <span data-ttu-id="e5abc-118">Если задача настроена на перестроение индексов во всех таблицах и представлениях базы данных с большим числом индексов или на перестроение индексов в нескольких базах данных, ей может потребоваться существенное количество времени для формирования инструкции Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="e5abc-118">If the task is configured to rebuild indexes in all the tables and views in a database with a large number of indexes, or to rebuild indexes in multiple databases, the task can take a considerable amount of time to generate the Transact-SQL statement.</span></span>  
  
## <a name="configuration-of-the-rebuild-index-task"></a><span data-ttu-id="e5abc-119">Настройка задачи «Перестроение индекса»</span><span class="sxs-lookup"><span data-stu-id="e5abc-119">Configuration of the Rebuild Index Task</span></span>  
 <span data-ttu-id="e5abc-120">Свойства задаются с помощью конструктора служб [!INCLUDE[ssIS](../../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e5abc-120">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="e5abc-121">Эта задача находится в разделе **Задачи плана обслуживания\*\*\*\*области элементов** в конструкторе служб [!INCLUDE[ssIS](../../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e5abc-121">This task is in the **Maintenance Plan Tasks** section of the **Toolbox** in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="e5abc-122">Дополнительные сведения о свойствах, которые можно задать в конструкторе служб [!INCLUDE[ssIS](../../../includes/ssis-md.md)] , см. в следующем разделе:</span><span class="sxs-lookup"><span data-stu-id="e5abc-122">For more information about the properties that you can set in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
 [<span data-ttu-id="e5abc-123">Задача "Перестроение индекса" (план обслуживания)</span><span class="sxs-lookup"><span data-stu-id="e5abc-123">Rebuild Index Task &#40;Maintenance Plan&#41;</span></span>](../../relational-databases/maintenance-plans/rebuild-index-task-maintenance-plan.md)  
  
## <a name="related-tasks"></a><span data-ttu-id="e5abc-124">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="e5abc-124">Related Tasks</span></span>  
 <span data-ttu-id="e5abc-125">Дополнительные сведения о настройке свойств этих свойств в конструкторе [!INCLUDE[ssIS](../../../includes/ssis-md.md)] см. в разделе [Задание свойств задач или контейнеров](../set-the-properties-of-a-task-or-container.md).</span><span class="sxs-lookup"><span data-stu-id="e5abc-125">For more about how to set these properties in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, see [Set the Properties of a Task or Container](../set-the-properties-of-a-task-or-container.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5abc-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="e5abc-126">See Also</span></span>  
 <span data-ttu-id="e5abc-127">[Задачи служб Integration Services](integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="e5abc-127">[Integration Services Tasks](integration-services-tasks.md) </span></span>  
 [<span data-ttu-id="e5abc-128">Поток управления</span><span class="sxs-lookup"><span data-stu-id="e5abc-128">Control Flow</span></span>](control-flow.md)  
  
  
