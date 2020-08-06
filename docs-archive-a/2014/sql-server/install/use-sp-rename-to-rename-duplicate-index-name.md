---
title: Использование sp_rename для переименования повторяющегося имени индекса | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- table names [SQL Server]
- duplicate table names
- index names [SQL Server]
- sp_rename
- duplicate index names
ms.assetid: ee66c7a5-eb6d-4fcf-970c-ab099d78c8d9
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: b8ffe3b9befd0c7239d32094e5738e0fb2947c5a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751660"
---
# <a name="use-sp_rename-to-rename-duplicate-index-name"></a><span data-ttu-id="f3b24-102">При помощи хранимой процедуры sp_rename переименуйте повторяющиеся имена индексов</span><span class="sxs-lookup"><span data-stu-id="f3b24-102">Use sp_rename to rename duplicate index name</span></span>
  <span data-ttu-id="f3b24-103">Советник по переходу обнаружил повторяющиеся имена таблиц или индексированных представлений.</span><span class="sxs-lookup"><span data-stu-id="f3b24-103">Upgrade Advisor has detected duplicate table or view index names.</span></span> <span data-ttu-id="f3b24-104">Перед обновлением переименуйте повторяющиеся индексы, чтобы их не было.</span><span class="sxs-lookup"><span data-stu-id="f3b24-104">Rename the indexes to remove duplicates before upgrading.</span></span>  
  
## <a name="component"></a><span data-ttu-id="f3b24-105">Компонент</span><span class="sxs-lookup"><span data-stu-id="f3b24-105">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="corrective-action"></a><span data-ttu-id="f3b24-106">Действие по исправлению</span><span class="sxs-lookup"><span data-stu-id="f3b24-106">Corrective Action</span></span>  
  
1.  <span data-ttu-id="f3b24-107">Определите наличие повторяющихся имен индексов, выполнив следующий запрос.</span><span class="sxs-lookup"><span data-stu-id="f3b24-107">Locate the duplicate indexes by executing the following query.</span></span>  
  
    ```  
    SELECT DISTINCT OBJECT_NAME(o.id), name  
    FROM sysindexes as o  
    WHERE EXISTS   
        (SELECT name FROM sysindexes  as i  
          WHERE i.id = o.id  
          AND i.name = o.name and i.indid < o.indid);  
    ```  
  
2.  <span data-ttu-id="f3b24-108">Используйте **sp_rename** , чтобы изменить одно из имен индексов.</span><span class="sxs-lookup"><span data-stu-id="f3b24-108">Use **sp_rename** to change one of the index names.</span></span> <span data-ttu-id="f3b24-109">Поскольку имена индексов одинаковые, невозможно определить, какой из этих индексов будет переименован.</span><span class="sxs-lookup"><span data-stu-id="f3b24-109">Because the index names are the same, you cannot determine which index will be renamed.</span></span> <span data-ttu-id="f3b24-110">Следующий шаг позволит различить такие индексы.</span><span class="sxs-lookup"><span data-stu-id="f3b24-110">This step allows you to differentiate the indexes.</span></span>  
  
    ```  
    EXEC sp_rename N'table_name.index_name', N'new_index_name', N'INDEX'  
    ```  
  
3.  <span data-ttu-id="f3b24-111">Проверьте, какой из индексов был переименован, выполнив следующий запрос.</span><span class="sxs-lookup"><span data-stu-id="f3b24-111">Verify which index was renamed by executing the following query.</span></span> <span data-ttu-id="f3b24-112">Этот запрос возвращает все индексы, включая имена ключевых столбцов, в указанной таблице или представлении.</span><span class="sxs-lookup"><span data-stu-id="f3b24-112">This query returns all indexes (including key column names) on the specified table or view.</span></span>  
  
    ```  
    SELECT i.name AS IndexName, c.name AS ColumnName, ik.colid, ik.keyno  
    FROM sysindexes i  
    JOIN sysindexkeys ik ON i.id = ik.id and i.indid = ik.indid   
    JOIN syscolumns c ON c.id = ik.id and ik.colid = c.colid  
    WHERE i.id = OBJECT_ID('table_or_view_name')  
    ```  
  
4.  <span data-ttu-id="f3b24-113">При необходимости используйте **sp_rename** еще раз, чтобы исправить имена индексов.</span><span class="sxs-lookup"><span data-stu-id="f3b24-113">If necessary, use **sp_rename** again to correct the index names.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3b24-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="f3b24-114">See Also</span></span>  
 <span data-ttu-id="f3b24-115">[Проблемы обновления ядро СУБД](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="f3b24-115">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="f3b24-116">Советник по переходу SQL Server 2014 &#91;New&#93;</span><span class="sxs-lookup"><span data-stu-id="f3b24-116">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
