---
title: Получить настраиваемые параметры для аргумента "добавить целевой объект" | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- extended events [SQL Server], ADD TARGET argument
- xe
ms.assetid: 08454543-c5c8-4ca3-9af9-f1d82264471c
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 30644bc30c0bd8c4ccbc17c616c6f24bf9455dc8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732934"
---
# <a name="get-the-configurable-parameters-for-the-add-target-argument"></a><span data-ttu-id="78437-102">получить настраиваемые параметры для аргумента ADD TARGET</span><span class="sxs-lookup"><span data-stu-id="78437-102">Get the Configurable Parameters for the ADD TARGET Argument</span></span>
  <span data-ttu-id="78437-103">Выполнение этой задачи предполагает использование редактора запросов в [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="78437-103">Accomplishing this task involves using Query Editor in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="78437-104">После выполнения инструкций данной процедуры на вкладке **Результаты** редактора запросов будут отображены следующие столбцы.</span><span class="sxs-lookup"><span data-stu-id="78437-104">After the statements in this procedure finish, the **Results** tab of Query Editor displays the following columns:</span></span>  
  
-   <span data-ttu-id="78437-105">package_name</span><span class="sxs-lookup"><span data-stu-id="78437-105">package_name</span></span>  
  
-   <span data-ttu-id="78437-106">target_name</span><span class="sxs-lookup"><span data-stu-id="78437-106">target_name</span></span>  
  
-   <span data-ttu-id="78437-107">parameter_name</span><span class="sxs-lookup"><span data-stu-id="78437-107">parameter_name</span></span>  
  
-   <span data-ttu-id="78437-108">parameter_type</span><span class="sxs-lookup"><span data-stu-id="78437-108">parameter_type</span></span>  
  
-   <span data-ttu-id="78437-109">обязательно</span><span class="sxs-lookup"><span data-stu-id="78437-109">required</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="78437-110">Перед началом</span><span class="sxs-lookup"><span data-stu-id="78437-110">Before You Begin</span></span>  
 <span data-ttu-id="78437-111">Перед созданием сеанса расширенных событий [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] полезно выяснить, какие параметры можно установить при использовании аргумента ADD TARGET в CREATE EVENT SESSION или ALTER EVENT SESSION.</span><span class="sxs-lookup"><span data-stu-id="78437-111">Before you create a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Extended Events session, it is useful to find out what parameters you can set when you use the ADD TARGET argument in CREATE EVENT SESSION or ALTER EVENT SESSION.</span></span>  
  
### <a name="to-get-the-configurable-parameters-for-the-add-target-argument-using-query-editor"></a><span data-ttu-id="78437-112">Получение настраиваемых параметров для аргумента ADD TARGET с использованием редактора запросов.</span><span class="sxs-lookup"><span data-stu-id="78437-112">To get the configurable parameters for the ADD TARGET argument using Query Editor</span></span>  
  
-   <span data-ttu-id="78437-113">В редакторе запросов выполните следующие инструкции.</span><span class="sxs-lookup"><span data-stu-id="78437-113">In Query Editor, issue the following statements.</span></span>  
  
    ```  
    SELECT p.name package_name, o.name target_name, c.name parameter_name,   
    c.type_name parameter_type, CASE c.capabilities_desc WHEN 'mandatory' THEN 'yes' ELSE 'no' END   
    required   
    FROM sys.dm_xe_objects o JOIN sys.dm_xe_packages p ON o.package_guid = p.guid   
    JOIN sys.dm_xe_object_columns c ON o.name = c.object_name AND c.column_type = 'customizable'  
    WHERE o.object_type = 'target'   
    ORDER BY package_name, target_name, required DESC  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="78437-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="78437-114">See Also</span></span>  
 <span data-ttu-id="78437-115">[CREATE EVENT SESSION (Transact-SQL)](/sql/t-sql/statements/create-event-session-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="78437-115">[CREATE EVENT SESSION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-event-session-transact-sql) </span></span>  
 <span data-ttu-id="78437-116">[ALTER EVENT SESSION &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-event-session-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="78437-116">[ALTER EVENT SESSION &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-event-session-transact-sql) </span></span>  
 <span data-ttu-id="78437-117">[sys.dm_xe_objects (Transact-SQL)](/sql/relational-databases/system-dynamic-management-views/sys-dm-xe-objects-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="78437-117">[sys.dm_xe_objects &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-xe-objects-transact-sql) </span></span>  
 [<span data-ttu-id="78437-118">sys.dm_xe_packages (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="78437-118">sys.dm_xe_packages &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-xe-packages-transact-sql)  
  
  
