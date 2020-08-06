---
title: Задать параметры сортировки определяемых пользователем баз данных в соответствии с параметрами баз данных master и Model | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: c686446f-dae1-4b05-a3df-837b3422988d
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: b48696fb56c40062d62f04845715170887f84fda
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728665"
---
# <a name="set-the-collation-of-user-defined-databases-to-match-those-of-the-master-and-model-databases"></a><span data-ttu-id="7c11a-102">Задание параметров сортировки пользовательских баз данных в соответствии с параметрами баз данных master и model</span><span class="sxs-lookup"><span data-stu-id="7c11a-102">Set the Collation of User-defined Databases to Match Those of the master and model Databases</span></span>
  <span data-ttu-id="7c11a-103">Это правило проверяет, определены ли в пользовательской базе данных те же параметры сортировки, что и в базах данных master и model.</span><span class="sxs-lookup"><span data-stu-id="7c11a-103">This rule checks whether user-defined databases are defined by using a database collation that is the same as the collation for master or model.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="7c11a-104">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="7c11a-104">Best Practices Recommendations</span></span>  
 <span data-ttu-id="7c11a-105">Рекомендуется, чтобы параметры сортировки пользовательских баз данных соответствовали параметрам сортировки баз данных master и model.</span><span class="sxs-lookup"><span data-stu-id="7c11a-105">We recommend that the collations of user-defined databases match the collation of master or model.</span></span> <span data-ttu-id="7c11a-106">Иначе может произойти конфликт параметров сортировки, мешающий выполнению кода.</span><span class="sxs-lookup"><span data-stu-id="7c11a-106">Otherwise, collation conflicts can occur that might prevent code from executing.</span></span> <span data-ttu-id="7c11a-107">Например, если хранимая процедура производит соединение таблицы с временной таблицей, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] может завершить работу пакета и вернуть ошибку конфликта параметров сортировки, если параметры сортировки базы данных model отличаются от параметров сортировки пользовательской базы данных.</span><span class="sxs-lookup"><span data-stu-id="7c11a-107">For example, when a stored procedure joins one table to a temporary table, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] might end the batch and return a collation conflict error if the collations of the user-defined database and the model database are different.</span></span> <span data-ttu-id="7c11a-108">Это происходит потому, что в базе данных tempdb создаются временные таблицы, параметры сортировки которых основаны на параметрах сортировки базы данных model.</span><span class="sxs-lookup"><span data-stu-id="7c11a-108">This occurs because temporary tables are created in tempdb, which bases its collation on that of model.</span></span>  
  
 <span data-ttu-id="7c11a-109">При возникновении ошибок из-за конфликтующих параметров сортировки рекомендуется одно из следующих решений.</span><span class="sxs-lookup"><span data-stu-id="7c11a-109">If you experience collation conflict errors, consider one of the following solutions:</span></span>  
  
-   <span data-ttu-id="7c11a-110">Экспортируйте данные из пользовательской базы данных и импортируйте их в новые таблицы, параметры сортировки которых совпадают с параметрами сортировки баз данных master и model.</span><span class="sxs-lookup"><span data-stu-id="7c11a-110">Export the data from the user database and import it into new tables that have the same collation as the master and model databases.</span></span>  
  
-   <span data-ttu-id="7c11a-111">Перестройте системные базы данных таким образом, чтобы их параметры сортировки совпадали с параметрами сортировки пользовательской базы данных.</span><span class="sxs-lookup"><span data-stu-id="7c11a-111">Rebuild the system databases to use a collation that matches the user database collation.</span></span> <span data-ttu-id="7c11a-112">Дополнительные сведения о перестроении системных баз данных см. в разделе [Перестроение системных баз данных](../relational-databases/databases/system-databases.md).</span><span class="sxs-lookup"><span data-stu-id="7c11a-112">For more information about how to rebuild the system databases, see [Rebuild System Databases](../relational-databases/databases/system-databases.md).</span></span>  
  
-   <span data-ttu-id="7c11a-113">Внесите изменения во все хранимые процедуры, производящие соединение пользовательских таблиц с таблицами в базе данных tempdb, чтобы таблицы в tempdb создавались с параметрами сортировки пользовательской базы данных.</span><span class="sxs-lookup"><span data-stu-id="7c11a-113">Modify any stored procedures that join user tables to tables in tempdb to create the tables in tempdb by using the collation of the user database.</span></span> <span data-ttu-id="7c11a-114">Для этого в определения столбцов временной таблицы добавьте предложение `COLLATE database_default`, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="7c11a-114">To do this, add the `COLLATE database_default` clause to the column definitions of the temporary table, as shown in the following example:</span></span>  
  
    ```  
    CREATE TABLE #temp1 ( c1 int, c2 varchar(30) COLLATE database_default )  
    ```  
  
## <a name="for-more-information"></a><span data-ttu-id="7c11a-115">Дополнительные сведения см. в разделе</span><span class="sxs-lookup"><span data-stu-id="7c11a-115">For More Information</span></span>  
 [<span data-ttu-id="7c11a-116">Установка и изменение параметров сортировки базы данных</span><span class="sxs-lookup"><span data-stu-id="7c11a-116">Set or Change the Database Collation</span></span>](../relational-databases/collations/set-or-change-the-database-collation.md)  
  
 [<span data-ttu-id="7c11a-117">Задание или изменение параметров сортировки столбца</span><span class="sxs-lookup"><span data-stu-id="7c11a-117">Set or Change the Column Collation</span></span>](../relational-databases/collations/set-or-change-the-column-collation.md)  
  
 [<span data-ttu-id="7c11a-118">ALTER DATABASE (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="7c11a-118">ALTER DATABASE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql)  
  
 [<span data-ttu-id="7c11a-119">COLLATE (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="7c11a-119">COLLATE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/collations)  
  
 [<span data-ttu-id="7c11a-120">sys.databases (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="7c11a-120">sys.databases &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql)  
  
 [<span data-ttu-id="7c11a-121">Статья базы знаний Майкрософт 325335</span><span class="sxs-lookup"><span data-stu-id="7c11a-121">Microsoft Knowledge Base article 325335</span></span>](https://go.microsoft.com/fwlink/?linkid=117751)  
  
 [<span data-ttu-id="7c11a-122">Как установить SQL Server 2008 из командной строки</span><span class="sxs-lookup"><span data-stu-id="7c11a-122">How to: Install SQL Server 2008 from the Command Prompt</span></span>](https://go.microsoft.com/fwlink/?LinkId=81585)  
  
## <a name="see-also"></a><span data-ttu-id="7c11a-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="7c11a-123">See Also</span></span>  
 [<span data-ttu-id="7c11a-124">Наблюдение с помощью управления на основе политик и принудительное применение рекомендаций с помощью управления на основе политик</span><span class="sxs-lookup"><span data-stu-id="7c11a-124">Monitor and Enforce Best Practices by Using Policy-Based Management</span></span>](../relational-databases/policy-based-management/monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
