---
title: Задача "Очистка журнала" | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.historycleanuptask.f1
helpviewer_keywords:
- history tables [SQL Server]
- History Cleanup task [Integration Services]
ms.assetid: 5defc5b9-dfd3-4859-a7fe-ac8c2b5480f8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 84bc697b7fb18269fc581cea51e111aebc82c15e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654446"
---
# <a name="history-cleanup-task"></a><span data-ttu-id="fbf73-102">Задача «Очистка журнала»</span><span class="sxs-lookup"><span data-stu-id="fbf73-102">History Cleanup Task</span></span>
  <span data-ttu-id="fbf73-103">Задача «Очистка журнала» удаляет записи в следующих таблицах журнала в базе данных msdb [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fbf73-103">The History Cleanup task deletes entries in the following history tables in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] msdb database.</span></span>  
  
-   <span data-ttu-id="fbf73-104">backupfile;</span><span class="sxs-lookup"><span data-stu-id="fbf73-104">backupfile</span></span>  
  
-   <span data-ttu-id="fbf73-105">backupfilegroup</span><span class="sxs-lookup"><span data-stu-id="fbf73-105">backupfilegroup</span></span>  
  
-   <span data-ttu-id="fbf73-106">backupmediafamily;</span><span class="sxs-lookup"><span data-stu-id="fbf73-106">backupmediafamily</span></span>  
  
-   <span data-ttu-id="fbf73-107">backupmediaset;</span><span class="sxs-lookup"><span data-stu-id="fbf73-107">backupmediaset</span></span>  
  
-   <span data-ttu-id="fbf73-108">backupset;</span><span class="sxs-lookup"><span data-stu-id="fbf73-108">backupset</span></span>  
  
-   <span data-ttu-id="fbf73-109">restorefile;</span><span class="sxs-lookup"><span data-stu-id="fbf73-109">restorefile</span></span>  
  
-   <span data-ttu-id="fbf73-110">restorefilegroup;</span><span class="sxs-lookup"><span data-stu-id="fbf73-110">restorefilegroup</span></span>  
  
-   <span data-ttu-id="fbf73-111">restorehistory.</span><span class="sxs-lookup"><span data-stu-id="fbf73-111">restorehistory</span></span>  
  
 <span data-ttu-id="fbf73-112">Используя задачу «Очистка журнала», пакет может удалить данные журнала, связанные с деятельностью по созданию резервных копий и восстановлению, с заданиями агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и планами обслуживания баз данных.</span><span class="sxs-lookup"><span data-stu-id="fbf73-112">By using the History Cleanup task, a package can delete historical data related to backup and restore activities, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs, and database maintenance plans.</span></span>  
  
 <span data-ttu-id="fbf73-113">Эта задача инкапсулирует системную хранимую процедуру sp_delete_backuphistory и передает указанную дату процедуре как аргумент.</span><span class="sxs-lookup"><span data-stu-id="fbf73-113">This task encapsulates the sp_delete_backuphistory system stored procedure and passes the specified date to the procedure as an argument.</span></span> <span data-ttu-id="fbf73-114">Дополнительные сведения см. в разделе [sp_delete_backuphistory (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-delete-backuphistory-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="fbf73-114">For more information, see [sp_delete_backuphistory &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-backuphistory-transact-sql).</span></span>  
  
## <a name="configuration-of-the-history-cleanup-task"></a><span data-ttu-id="fbf73-115">Настройка задачи «Очистка журнала»</span><span class="sxs-lookup"><span data-stu-id="fbf73-115">Configuration of the History Cleanup Task</span></span>  
 <span data-ttu-id="fbf73-116">Эта задача включает свойство для указания самой ранней даты для данных, остающихся в таблицах журнала.</span><span class="sxs-lookup"><span data-stu-id="fbf73-116">The task includes a property for specifying the oldest date of data retained in the history tables.</span></span> <span data-ttu-id="fbf73-117">Дата может задаваться числом дней, недель, месяцев или лет от текущего дня; в этом случае задача автоматически преобразует промежуток времени в дату.</span><span class="sxs-lookup"><span data-stu-id="fbf73-117">You can indicate the date by number of days, weeks, months, or years from the current day, and the task automatically translates the interval to a date.</span></span>  
  
 <span data-ttu-id="fbf73-118">Свойства задаются с помощью конструктора служб [!INCLUDE[ssIS](../../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fbf73-118">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="fbf73-119">Эта задача находится в разделе **Задачи плана обслуживания** **области элементов** в конструкторе служб [!INCLUDE[ssIS](../../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fbf73-119">This task is in the **Maintenance Plan Tasks** section of the **Toolbox** in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="fbf73-120">Дополнительные сведения о свойствах, которые можно задать в конструкторе служб [!INCLUDE[ssIS](../../../includes/ssis-md.md)] , см. в следующем разделе:</span><span class="sxs-lookup"><span data-stu-id="fbf73-120">For more information about the properties that you can set in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="fbf73-121">Задача "Очистка журнала" (план обслуживания)</span><span class="sxs-lookup"><span data-stu-id="fbf73-121">History Cleanup Task &#40;Maintenance Plan&#41;</span></span>](../../relational-databases/maintenance-plans/history-cleanup-task-maintenance-plan.md)  
  
 <span data-ttu-id="fbf73-122">Дополнительные сведения об установке этих свойств в конструкторе служб [!INCLUDE[ssIS](../../../includes/ssis-md.md)] см. в следующем разделе:</span><span class="sxs-lookup"><span data-stu-id="fbf73-122">For more information about how to set these properties in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="fbf73-123">Задание свойств задач или контейнеров</span><span class="sxs-lookup"><span data-stu-id="fbf73-123">Set the Properties of a Task or Container</span></span>](../set-the-properties-of-a-task-or-container.md)  
  
## <a name="see-also"></a><span data-ttu-id="fbf73-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="fbf73-124">See Also</span></span>  
 <span data-ttu-id="fbf73-125">[Задачи служб Integration Services](integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="fbf73-125">[Integration Services Tasks](integration-services-tasks.md) </span></span>  
 [<span data-ttu-id="fbf73-126">Поток управления</span><span class="sxs-lookup"><span data-stu-id="fbf73-126">Control Flow</span></span>](control-flow.md)  
  
  
