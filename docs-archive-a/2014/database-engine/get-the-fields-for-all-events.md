---
title: Получить поля для всех событий | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- extended events [SQL Server], getting fields
- xe
ms.assetid: 4e4ee03f-5bca-42ed-a37c-db1c82e3aad2
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 01d98e827121a0c47111dd601c6e1772f796849d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732926"
---
# <a name="get-the-fields-for-all-events"></a><span data-ttu-id="6068f-102">получить поля для всех событий</span><span class="sxs-lookup"><span data-stu-id="6068f-102">Get the Fields for All Events</span></span>
  <span data-ttu-id="6068f-103">Выполнение этой задачи предполагает использование редактора запросов в [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6068f-103">Accomplishing this task involves using Query Editor in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="6068f-104">После выполнения инструкций данной процедуры на вкладке **Результаты** редактора запросов будут отображены следующие столбцы.</span><span class="sxs-lookup"><span data-stu-id="6068f-104">After the statements in this procedure finish, the **Results** tab of Query Editor displays the following columns:</span></span>  
  
-   <span data-ttu-id="6068f-105">package_name</span><span class="sxs-lookup"><span data-stu-id="6068f-105">package_name</span></span>  
  
-   <span data-ttu-id="6068f-106">event_name</span><span class="sxs-lookup"><span data-stu-id="6068f-106">event_name</span></span>  
  
-   <span data-ttu-id="6068f-107">event_field</span><span class="sxs-lookup"><span data-stu-id="6068f-107">event_field</span></span>  
  
-   <span data-ttu-id="6068f-108">field_type</span><span class="sxs-lookup"><span data-stu-id="6068f-108">field_type</span></span>  
  
-   <span data-ttu-id="6068f-109">column_type</span><span class="sxs-lookup"><span data-stu-id="6068f-109">column_type</span></span>  
  
 <span data-ttu-id="6068f-110">Можно использовать приведенные выше сведения при настройке сеансов событий, в которых используются сегментированные цели.</span><span class="sxs-lookup"><span data-stu-id="6068f-110">You can use the preceding information when configuring event sessions that use the bucketing target.</span></span> <span data-ttu-id="6068f-111">Дополнительные сведения см. в статье [SQL Server Extended Events Targets](../../2014/database-engine/sql-server-extended-events-targets.md).</span><span class="sxs-lookup"><span data-stu-id="6068f-111">For more information, see [SQL Server Extended Events Targets](../../2014/database-engine/sql-server-extended-events-targets.md).</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="6068f-112">Перед началом работы</span><span class="sxs-lookup"><span data-stu-id="6068f-112">Before you Begin</span></span>  
 <span data-ttu-id="6068f-113">Перед созданием сеанса расширенных событий [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] рекомендуется выявить поля, связанные с этими событиями.</span><span class="sxs-lookup"><span data-stu-id="6068f-113">Before you create a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Extended Events session, it is useful to get information about the fields associated with events.</span></span>  
  
## <a name="to-get-the-fields-for-all-events-using-query-editor"></a><span data-ttu-id="6068f-114">Получение полей для всех событий с помощью редактора запросов</span><span class="sxs-lookup"><span data-stu-id="6068f-114">To get the fields for all events using Query Editor</span></span>  
  
-   <span data-ttu-id="6068f-115">В редакторе запросов выполните следующие инструкции.</span><span class="sxs-lookup"><span data-stu-id="6068f-115">In Query Editor, issue the following statements.</span></span>  
  
    ```  
    select p.name package_name, o.name event_name, c.name event_field, c.type_name field_type, c.column_type column_type  
    from sys.dm_xe_objects o  
    join sys.dm_xe_packages p  
          on o.package_guid = p.guid  
    join sys.dm_xe_object_columns c  
          on o.name = c.object_name  
    where o.object_type = 'event'  
    order by package_name, event_name  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="6068f-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="6068f-116">See Also</span></span>  
 <span data-ttu-id="6068f-117">[sys.dm_xe_objects (Transact-SQL)](/sql/relational-databases/system-dynamic-management-views/sys-dm-xe-objects-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="6068f-117">[sys.dm_xe_objects &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-xe-objects-transact-sql) </span></span>  
 [<span data-ttu-id="6068f-118">sys.dm_xe_packages (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="6068f-118">sys.dm_xe_packages &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-xe-packages-transact-sql)  
  
  
