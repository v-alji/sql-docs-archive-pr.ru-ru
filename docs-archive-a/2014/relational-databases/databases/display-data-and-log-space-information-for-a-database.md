---
title: Отображение данных и сведений о пространстве журнала для базы данных | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- logs [SQL Server], space
- status information [SQL Server], space
- displaying space information
- disk space [SQL Server], displaying
- databases [SQL Server], space used
- viewing space information
- space allocation [SQL Server], displaying
- data space [SQL Server]
ms.assetid: c7b99463-4bab-4e9b-9217-fcb0898dc757
author: stevestein
ms.author: sstein
ms.openlocfilehash: 1beb8cdedbc2b72eadeeb350ee1c3b6d16218205
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751092"
---
# <a name="display-data-and-log-space-information-for-a-database"></a><span data-ttu-id="d02dd-102">Отображение данных и сведений о пространстве журнала для базы данных</span><span class="sxs-lookup"><span data-stu-id="d02dd-102">Display Data and Log Space Information for a Database</span></span>
  <span data-ttu-id="d02dd-103">В этом разделе описано, как отобразить данные и сведения о пространстве журнала для базы данных в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] при помощи среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d02dd-103">This topic describes how to display the data and log space information for a database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="d02dd-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="d02dd-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="d02dd-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="d02dd-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="d02dd-106">Безопасность</span><span class="sxs-lookup"><span data-stu-id="d02dd-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="d02dd-107">**Отображение данных и сведений о пространстве журнала с помощью различных средств.**</span><span class="sxs-lookup"><span data-stu-id="d02dd-107">**To display data and log space information for a database, using:**</span></span>  
  
     [<span data-ttu-id="d02dd-108">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d02dd-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="d02dd-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d02dd-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="d02dd-110">Перед началом</span><span class="sxs-lookup"><span data-stu-id="d02dd-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="d02dd-111">безопасность</span><span class="sxs-lookup"><span data-stu-id="d02dd-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="d02dd-112">Permissions</span><span class="sxs-lookup"><span data-stu-id="d02dd-112">Permissions</span></span>  
 <span data-ttu-id="d02dd-113">Разрешение на выполнение процедуры **sp_spaceused** предоставлено роли **public** .</span><span class="sxs-lookup"><span data-stu-id="d02dd-113">Permission to execute **sp_spaceused** is granted to the **public** role.</span></span> <span data-ttu-id="d02dd-114">Параметр **@updateusage** могут указывать только члены предопределенной роли базы данных **@updateusage** .</span><span class="sxs-lookup"><span data-stu-id="d02dd-114">Only members of the **db_owner** fixed database role can specify the **@updateusage** parameter.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="d02dd-115">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d02dd-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-display-data-and-log-space-information-for-a-database"></a><span data-ttu-id="d02dd-116">Отображение данных и сведений о пространстве для базы данных</span><span class="sxs-lookup"><span data-stu-id="d02dd-116">To display data and log space information for a database</span></span>  
  
1.  <span data-ttu-id="d02dd-117">В обозревателе объектов подключитесь к экземпляру [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и разверните его.</span><span class="sxs-lookup"><span data-stu-id="d02dd-117">In Object Explorer, connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="d02dd-118">Разверните узел **Базы данных**.</span><span class="sxs-lookup"><span data-stu-id="d02dd-118">Expand **Databases**.</span></span>  
  
3.  <span data-ttu-id="d02dd-119">Щелкните правой кнопкой мыши базу данных, укажите **Отчеты**, **Стандартные отчеты**, а затем щелкните **Использование диска**.</span><span class="sxs-lookup"><span data-stu-id="d02dd-119">Right-click a database, point to **Reports**, point to **Standard Reports,**, and then click **Disk Usage**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="d02dd-120">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d02dd-120">Using Transact-SQL</span></span>  
  
#### <a name="to-display-data-and-log-space-information-for-a-database-by-using-sp_spaceused"></a><span data-ttu-id="d02dd-121">Отображение данных и сведений о пространстве журнала для базы данных при помощи процедуры sp_spaceused</span><span class="sxs-lookup"><span data-stu-id="d02dd-121">To display data and log space information for a database by using sp_spaceused</span></span>  
  
1.  <span data-ttu-id="d02dd-122">Установите соединение с компонентом [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d02dd-122">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="d02dd-123">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="d02dd-123">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="d02dd-124">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="d02dd-124">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="d02dd-125">В этом примере используется системная хранимая процедура [sp_spaceused](/sql/relational-databases/system-stored-procedures/sp-spaceused-transact-sql) , которая передает сведения о заполнении места на диске для таблицы `Vendor` и ее индексов.</span><span class="sxs-lookup"><span data-stu-id="d02dd-125">This example uses the [sp_spaceused](/sql/relational-databases/system-stored-procedures/sp-spaceused-transact-sql) system stored procedure to report disk space information for the `Vendor` table and its indexes.</span></span>  
  
```sql  
USE AdventureWorks2012;  
GO  
EXEC sp_spaceused N'Purchasing.Vendor';  
GO  
```  
  
#### <a name="to-display-data-and-log-space-information-for-a-database-by-querying-sysdatabase_files"></a><span data-ttu-id="d02dd-126">Отображение данных и сведений о пространстве журнала для базы данных путем запроса к представлению каталога sys.database_files</span><span class="sxs-lookup"><span data-stu-id="d02dd-126">To display data and log space information for a database by querying sys.database_files</span></span>  
  
1.  <span data-ttu-id="d02dd-127">Установите соединение с компонентом [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d02dd-127">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="d02dd-128">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="d02dd-128">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="d02dd-129">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="d02dd-129">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="d02dd-130">В этом примере выполняется запрос к представлению каталога [sys.database_files](/sql/relational-databases/system-catalog-views/sys-database-files-transact-sql) , который возвращает определенные сведения о файлах данных и журнала из базы данных [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d02dd-130">This example queries the [sys.database_files](/sql/relational-databases/system-catalog-views/sys-database-files-transact-sql) catalog view to return specific information about the data and log files in the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span>  
  
```sql  
USE AdventureWorks2012;  
GO  
SELECT file_id, name, type_desc, physical_name, size, max_size  
FROM sys.database_files ;  
GO  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="d02dd-131">См. также:</span><span class="sxs-lookup"><span data-stu-id="d02dd-131">See Also</span></span>  
 <span data-ttu-id="d02dd-132">[SELECT (Transact-SQL)](/sql/t-sql/queries/select-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="d02dd-132">[SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql) </span></span>  
 <span data-ttu-id="d02dd-133">[sys.database_files (Transact-SQL)](/sql/relational-databases/system-catalog-views/sys-database-files-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="d02dd-133">[sys.database_files &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-files-transact-sql) </span></span>  
 <span data-ttu-id="d02dd-134">[sp_spaceused (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-spaceused-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="d02dd-134">[sp_spaceused &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-spaceused-transact-sql) </span></span>  
 <span data-ttu-id="d02dd-135">[Добавление файлов данных или журналов в базу данных](add-data-or-log-files-to-a-database.md) </span><span class="sxs-lookup"><span data-stu-id="d02dd-135">[Add Data or Log Files to a Database](add-data-or-log-files-to-a-database.md) </span></span>  
 [<span data-ttu-id="d02dd-136">Удаление файлов данных или журналов из базы данных</span><span class="sxs-lookup"><span data-stu-id="d02dd-136">Delete Data or Log Files from a Database</span></span>](delete-data-or-log-files-from-a-database.md)  
  
  
