---
title: Задача "Обновление статистики" | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.updatestatisticstask.f1
helpviewer_keywords:
- updating statistics
- Update Statistics task [Integration Services]
ms.assetid: 0247483b-f092-4511-8fa8-3610108bd1bc
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1507ada1e4fa087901383930fce4996c191fb553
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654425"
---
# <a name="update-statistics-task"></a><span data-ttu-id="a7720-102">Задача «Обновление статистики»</span><span class="sxs-lookup"><span data-stu-id="a7720-102">Update Statistics Task</span></span>
  <span data-ttu-id="a7720-103">Задача «Обновление статистики» обновляет данные о распределении ключевых значений одной или более статистических групп (коллекций) в определенной таблице или индексированном представлении.</span><span class="sxs-lookup"><span data-stu-id="a7720-103">The Update Statistics task updates information about the distribution of key values for one or more statistics groups (collections) in the specified table or indexed view.</span></span> <span data-ttu-id="a7720-104">Дополнительные сведения см. в статье [Managing statistics on tables in SQL Data Warehouse](../../relational-databases/statistics/statistics.md) (Управление статистикой таблиц в хранилище данных SQL).</span><span class="sxs-lookup"><span data-stu-id="a7720-104">For more information, see [Statistics](../../relational-databases/statistics/statistics.md).</span></span>  
  
 <span data-ttu-id="a7720-105">При помощи задачи «Обновление статистики» пакет может обновлять статистику в одной или нескольких базах данных.</span><span class="sxs-lookup"><span data-stu-id="a7720-105">By using the Update Statistics task, a package can update statistics for a single database or multiple databases.</span></span> <span data-ttu-id="a7720-106">Если задача обновляет статистику только одной базы данных, можно выбрать представления и таблицы, статистику которых данная задача обновляет.</span><span class="sxs-lookup"><span data-stu-id="a7720-106">If the task updates only the statistics in a single database, you can choose the views or the tables whose statistics the task updates.</span></span> <span data-ttu-id="a7720-107">Можно определить, необходимо ли обновлять всю статистику, только статистику столбцов, или только статистику индекса.</span><span class="sxs-lookup"><span data-stu-id="a7720-107">You can configure the update to update all statistics, column statistics only, or index statistics only.</span></span>  
  
 <span data-ttu-id="a7720-108">Эта задача содержит инструкцию UPDATE STATISTICS, включающую следующие аргументы и предложения:</span><span class="sxs-lookup"><span data-stu-id="a7720-108">This task encapsulates an UPDATE STATISTICS statement, including the following arguments and clauses:</span></span>  
  
-   <span data-ttu-id="a7720-109">Аргумент *table_name* или *view_name* .</span><span class="sxs-lookup"><span data-stu-id="a7720-109">The *table_name* or *view_name* argument.</span></span>  
  
-   <span data-ttu-id="a7720-110">Если необходимо обновление всех статистик, нужно применить предложение WITH ALL.</span><span class="sxs-lookup"><span data-stu-id="a7720-110">If the update applies to all statistics, the WITH ALL clause is implied.</span></span>  
  
-   <span data-ttu-id="a7720-111">Если необходимо обновление только столбцов, применяется предложение WITH COLUMN.</span><span class="sxs-lookup"><span data-stu-id="a7720-111">If the update applies only to columns, the WITH COLUMN clause is included.</span></span>  
  
-   <span data-ttu-id="a7720-112">Если необходимо обновление только индексов, применяется предложение WITH INDEX.</span><span class="sxs-lookup"><span data-stu-id="a7720-112">If the update applies only to indexes, the WITH INDEX clause is included.</span></span>  
  
 <span data-ttu-id="a7720-113">Если задача «Обновление статистики» обновляет статистику в нескольких базах данных, она запускает несколько инструкций UPDATE STATISTICS, каждую для отдельной таблицы или представления.</span><span class="sxs-lookup"><span data-stu-id="a7720-113">If the Update Statistics task updates statistics in multiple databases, the task runs multiple UPDATE STATISTICS statements, one for each table or view.</span></span> <span data-ttu-id="a7720-114">Все экземпляры инструкции UPDATE STATISTICS используют одно и то же предложение, но различные значения аргументов *table_name* или *view_name* .</span><span class="sxs-lookup"><span data-stu-id="a7720-114">All instances of UPDATE STATISTICS use the same clause, but different *table_name* or *view_name* values.</span></span> <span data-ttu-id="a7720-115">Дополнительные сведения см. в разделах [CREATE STATISTICS (Transact-SQL)](/sql/t-sql/statements/create-statistics-transact-sql) и [UPDATE STATISTICS (Transact-SQL)](/sql/t-sql/statements/update-statistics-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="a7720-115">For more information, see [CREATE STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-statistics-transact-sql) and [UPDATE STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/statements/update-statistics-transact-sql).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="a7720-116">Время, которое необходимо задаче для создания инструкции Transact-SQL, пропорционально числу статистик, которые обновляет задача.</span><span class="sxs-lookup"><span data-stu-id="a7720-116">The time the task takes to create the Transact-SQL statement that the task runs is proportionate to the number of statistics the task updates.</span></span> <span data-ttu-id="a7720-117">Если задача настроена на обновление статистики во всех таблицах и представлениях базы данных с большим числом индексов или на обновление статистики в нескольких базах данных, ей может потребоваться существенное количество времени для формирования инструкции Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="a7720-117">If the task is configured to update statistics in all the tables and views in a database with a large number of indexes, or to update statistics in multiple databases, the task can take a considerable amount of time to generate the Transact-SQL statement.</span></span>  
  
## <a name="configuration-of-the-update-statistics-task"></a><span data-ttu-id="a7720-118">Настройка задачи «Обновление статистики»</span><span class="sxs-lookup"><span data-stu-id="a7720-118">Configuration of the Update Statistics Task</span></span>  
 <span data-ttu-id="a7720-119">Свойства задаются с помощью конструктора служб [!INCLUDE[ssIS](../../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a7720-119">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="a7720-120">Эта задача находится в разделе **Задачи плана обслуживания** **области элементов** в конструкторе служб [!INCLUDE[ssIS](../../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a7720-120">This task is in the **Maintenance Plan Tasks** section of the **Toolbox** in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="a7720-121">Дополнительные сведения о свойствах, которые можно задать в конструкторе служб [!INCLUDE[ssIS](../../../includes/ssis-md.md)] , см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="a7720-121">For information about the properties that you can set in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="a7720-122">Задача "Обновление статистики" (план обслуживания)</span><span class="sxs-lookup"><span data-stu-id="a7720-122">Update Statistics Task &#40;Maintenance Plan&#41;</span></span>](../../relational-databases/maintenance-plans/update-statistics-task-maintenance-plan.md)  
  
## <a name="related-tasks"></a><span data-ttu-id="a7720-123">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="a7720-123">Related Tasks</span></span>  
 <span data-ttu-id="a7720-124">Дополнительные сведения об установке этих свойств в конструкторе служб [!INCLUDE[ssIS](../../../includes/ssis-md.md)] см. в следующем разделе:</span><span class="sxs-lookup"><span data-stu-id="a7720-124">For more information about how to set these properties in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="a7720-125">Задание свойств задач или контейнеров</span><span class="sxs-lookup"><span data-stu-id="a7720-125">Set the Properties of a Task or Container</span></span>](../set-the-properties-of-a-task-or-container.md)  
  
## <a name="see-also"></a><span data-ttu-id="a7720-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="a7720-126">See Also</span></span>  
 <span data-ttu-id="a7720-127">[Задачи служб Integration Services](integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="a7720-127">[Integration Services Tasks](integration-services-tasks.md) </span></span>  
 [<span data-ttu-id="a7720-128">Поток управления</span><span class="sxs-lookup"><span data-stu-id="a7720-128">Control Flow</span></span>](control-flow.md)  
  
  
