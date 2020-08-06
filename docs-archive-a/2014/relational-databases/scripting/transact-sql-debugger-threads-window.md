---
title: Окно потоков
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Threads Window [Transact-SQL]
ms.assetid: e153f619-0049-4162-9076-c24a454f3278
author: rothja
ms.author: jroth
ms.openlocfilehash: 6f3460c892c182996a753c2a16076418a6b2008f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730457"
---
# <a name="threads-window"></a><span data-ttu-id="122ef-102">Окно потоков</span><span class="sxs-lookup"><span data-stu-id="122ef-102">Threads Window</span></span>
  <span data-ttu-id="122ef-103">В окне **Потоки** отображаются сведения о потоке компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] , который используется в отлаживаемом сеансе редактора запросов компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="122ef-103">The **Threads** window displays information about the [!INCLUDE[ssDE](../../includes/ssde-md.md)] thread that is used by the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor session that is being debugged.</span></span> <span data-ttu-id="122ef-104">Чтобы иметь возможность просматривать сведения о потоке, необходимо находиться в режиме отладки.</span><span class="sxs-lookup"><span data-stu-id="122ef-104">You must be in debug mode to display the thread information.</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="122ef-105">Список задач</span><span class="sxs-lookup"><span data-stu-id="122ef-105">Task List</span></span>  
 <span data-ttu-id="122ef-106">**Доступ к окну «Потоки»**</span><span class="sxs-lookup"><span data-stu-id="122ef-106">**To access the Threads window**</span></span>  
  
-   <span data-ttu-id="122ef-107">В меню **Отладка** укажите **Окна**и выберите пункт **Потоки**.</span><span class="sxs-lookup"><span data-stu-id="122ef-107">On the **Debug** menu, click **Windows**, and then click **Threads**.</span></span>  
  
## <a name="columns"></a><span data-ttu-id="122ef-108">Столбцы</span><span class="sxs-lookup"><span data-stu-id="122ef-108">Columns</span></span>  
 <span data-ttu-id="122ef-109">**Идентификатор**</span><span class="sxs-lookup"><span data-stu-id="122ef-109">**ID**</span></span>  
 <span data-ttu-id="122ef-110">Уникальный идентификационный номер, присвоенный отладчиком [!INCLUDE[tsql](../../includes/tsql-md.md)] потоку.</span><span class="sxs-lookup"><span data-stu-id="122ef-110">Is a unique identifying number that the [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger assigns to the thread.</span></span> <span data-ttu-id="122ef-111">Чтобы получить дополнительные сведения о потоке, можно выбрать строки в динамическом административном представлении sys.dm_os_threads.</span><span class="sxs-lookup"><span data-stu-id="122ef-111">You can find more information about the thread by selecting a row from the sys.dm_os_threads dynamic management view.</span></span>  
  
 <span data-ttu-id="122ef-112">При работе не в режиме использования упрощенных пулов должна быть выполнена выборка строки, в которой значение os_thread_id совпадает со значением в столбце **Идентификатор** .</span><span class="sxs-lookup"><span data-stu-id="122ef-112">If you are not running in lightweight pooling mode, select the row in which the value in os_thread_id matches the value in the **ID** column.</span></span> <span data-ttu-id="122ef-113">При работе в режиме использования упрощенных пулов выберите строку, в которой значение fiber_context_address совпадает со значением в столбце **Идентификатор** .</span><span class="sxs-lookup"><span data-stu-id="122ef-113">If you are running in lightweight pooling mode, select the row in which the value in fiber_context_address matches the value in the **ID** column.</span></span>  
  
 <span data-ttu-id="122ef-114">**Название**</span><span class="sxs-lookup"><span data-stu-id="122ef-114">**Name**</span></span>  
 <span data-ttu-id="122ef-115">Выводится информация о сеансе компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] в формате **ИмяКомпьютера/ИмяЭкземпляра [SPID]** .</span><span class="sxs-lookup"><span data-stu-id="122ef-115">Displays information about the [!INCLUDE[ssDE](../../includes/ssde-md.md)] session in the format **ComputerName/InstanceName [SPID]**.</span></span>  
  
 <span data-ttu-id="122ef-116">**ИмяКомпьютера**</span><span class="sxs-lookup"><span data-stu-id="122ef-116">**ComputerName**</span></span>  
 <span data-ttu-id="122ef-117">Имя компьютера, на котором работает экземпляр компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] , к которому подключен сеанс редактора запросов.</span><span class="sxs-lookup"><span data-stu-id="122ef-117">The name of the computer that is running the instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] that the Query Editor session is connected to.</span></span>  
  
 <span data-ttu-id="122ef-118">**InstanceName**</span><span class="sxs-lookup"><span data-stu-id="122ef-118">**InstanceName**</span></span>  
 <span data-ttu-id="122ef-119">Имя экземпляра, к которому подключен сеанс редактора запросов компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="122ef-119">The name of the instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] that the Query Editor session is connected to.</span></span>  
  
 <span data-ttu-id="122ef-120">**[SPID]**</span><span class="sxs-lookup"><span data-stu-id="122ef-120">**[SPID]**</span></span>  
 <span data-ttu-id="122ef-121">Идентификатор процесса сеанса [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , который однозначно определяет этот сеанс.</span><span class="sxs-lookup"><span data-stu-id="122ef-121">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] session process ID that uniquely identifies this session.</span></span> <span data-ttu-id="122ef-122">Можно получить дополнительные сведения об этом сеансе путем выборки строки в представлении sys.sysprocesses, которая имеет то же значение в столбце spid.</span><span class="sxs-lookup"><span data-stu-id="122ef-122">You can obtain more information about the session by selecting the row in the sys.sysprocesses view that has the same value in the spid column.</span></span>  
  
 <span data-ttu-id="122ef-123">**Местоположение**</span><span class="sxs-lookup"><span data-stu-id="122ef-123">**Location**</span></span>  
 <span data-ttu-id="122ef-124">Отображается имя файла скрипта, который используется в отлаживаемом сеансе редактора запросов.</span><span class="sxs-lookup"><span data-stu-id="122ef-124">Displays the name of the script file that is used in the Query Editor session that is being debugged.</span></span>  
  
 <span data-ttu-id="122ef-125">**Приоритет**</span><span class="sxs-lookup"><span data-stu-id="122ef-125">**Priority**</span></span>  
 <span data-ttu-id="122ef-126">Отладчик [!INCLUDE[tsql](../../includes/tsql-md.md)] не поддерживает эту функцию.</span><span class="sxs-lookup"><span data-stu-id="122ef-126">The [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger does not support this feature.</span></span>  
  
 <span data-ttu-id="122ef-127">**Приостановить**</span><span class="sxs-lookup"><span data-stu-id="122ef-127">**Suspend**</span></span>  
 <span data-ttu-id="122ef-128">Отладчик [!INCLUDE[tsql](../../includes/tsql-md.md)] не поддерживает эту функцию.</span><span class="sxs-lookup"><span data-stu-id="122ef-128">The [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger does not support this feature.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="122ef-129">См. также:</span><span class="sxs-lookup"><span data-stu-id="122ef-129">See Also</span></span>  
 <span data-ttu-id="122ef-130">[Отладчик Transact-SQL](transact-sql-debugger.md) </span><span class="sxs-lookup"><span data-stu-id="122ef-130">[Transact-SQL Debugger](transact-sql-debugger.md) </span></span>  
 <span data-ttu-id="122ef-131">[Сведения отладчика Transact-SQL](transact-sql-debugger-information.md) </span><span class="sxs-lookup"><span data-stu-id="122ef-131">[Transact-SQL Debugger Information](transact-sql-debugger-information.md) </span></span>  
 <span data-ttu-id="122ef-132">[sys.dm_os_threads (Transact-SQL)](/sql/relational-databases/system-dynamic-management-views/sys-dm-os-threads-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="122ef-132">[sys.dm_os_threads &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-os-threads-transact-sql) </span></span>  
 [<span data-ttu-id="122ef-133">sys.sysprocesses (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="122ef-133">sys.sysprocesses &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-compatibility-views/sys-sysprocesses-transact-sql)  
