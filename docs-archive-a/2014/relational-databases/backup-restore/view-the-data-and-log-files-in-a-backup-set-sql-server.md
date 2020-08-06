---
title: Просмотр файлов данных и журналов в резервном наборе данных (SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- database backups [SQL Server], viewing backup sets
- viewing backup set information
- backup sets [SQL Server], viewing files in
- displaying backup set information
- transaction log backups [SQL Server], viewing backup sets
- backing up [SQL Server], viewing backup sets
ms.assetid: abb6420c-f809-426e-aeb4-d0a74989cf39
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 7dbcb14a658b49aba6f5f2ebe3425a2ab5759efa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734177"
---
# <a name="view-the-data-and-log-files-in-a-backup-set-sql-server"></a><span data-ttu-id="54055-102">Просмотр файлов данных и журналов в резервном наборе данных (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="54055-102">View the Data and Log Files in a Backup Set (SQL Server)</span></span>
  <span data-ttu-id="54055-103">В этом разделе описываются способы просмотра файлов данных и файлов журнала в резервном наборе данных в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="54055-103">This topic describes how to view the data and log files in a backup set in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="54055-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="54055-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="54055-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="54055-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="54055-106">Безопасность</span><span class="sxs-lookup"><span data-stu-id="54055-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="54055-107">**Для просмотра файлов данных и журналов в резервном наборе данных используется:**</span><span class="sxs-lookup"><span data-stu-id="54055-107">**To view the data and log files in a backup set, using:**</span></span>  
  
     [<span data-ttu-id="54055-108">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="54055-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="54055-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="54055-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="54055-110">Перед началом</span><span class="sxs-lookup"><span data-stu-id="54055-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="54055-111">безопасность</span><span class="sxs-lookup"><span data-stu-id="54055-111">Security</span></span>  
 <span data-ttu-id="54055-112">Сведения о безопасности см. в статье [RESTORE FILELISTONLY (Transact-SQL)](/sql/t-sql/statements/restore-statements-filelistonly-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="54055-112">For information about security, see [RESTORE FILELISTONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-filelistonly-transact-sql)</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="54055-113">Permissions</span><span class="sxs-lookup"><span data-stu-id="54055-113">Permissions</span></span>  
 <span data-ttu-id="54055-114">В [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] и более поздних версиях для получения сведений о резервном наборе данных или устройстве резервного копирования необходимо разрешение CREATE DATABASE.</span><span class="sxs-lookup"><span data-stu-id="54055-114">In [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] and later versions, obtaining information about a backup set or backup device requires CREATE DATABASE permission.</span></span> <span data-ttu-id="54055-115">Дополнительные сведения см. в разделе [GRANT, предоставление разрешений для базы данных (Transact-SQL)](/sql/t-sql/statements/grant-database-permissions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="54055-115">For more information, see [GRANT Database Permissions &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-database-permissions-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="54055-116">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="54055-116">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-the-data-and-log-files-in-a-backup-set"></a><span data-ttu-id="54055-117">Просмотр файлов данных и журналов в резервном наборе данных</span><span class="sxs-lookup"><span data-stu-id="54055-117">To view the data and log files in a backup set</span></span>  
  
1.  <span data-ttu-id="54055-118">После подключения к соответствующему экземпляру [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] в обозревателе объектов разверните дерево сервера, щелкнув его имя.</span><span class="sxs-lookup"><span data-stu-id="54055-118">After connecting to the appropriate instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="54055-119">Раскройте узел **Базы данных**и в зависимости от типа восстанавливаемой базы данных выберите пользовательскую базу данных или раскройте узел **Системные базы данных** и выберите системную базу данных.</span><span class="sxs-lookup"><span data-stu-id="54055-119">Expand **Databases**, and, depending on the database, either select a user database or expand **System Databases** and select a system database.</span></span>  
  
3.  <span data-ttu-id="54055-120">Щелкните базу данных правой кнопкой мыши и выберите **Свойства**. Откроется диалоговое окно **Свойства базы данных** .</span><span class="sxs-lookup"><span data-stu-id="54055-120">Right-click the database, and then click **Properties**, which opens the **Database Properties** dialog box.</span></span>  
  
4.  <span data-ttu-id="54055-121">На панели **Выбор страницы** нажмите кнопку **Файлы**.</span><span class="sxs-lookup"><span data-stu-id="54055-121">In the **Select a Page** pane, click **Files**.</span></span>  
  
5.  <span data-ttu-id="54055-122">Список файлов данных и журналов, а также их свойства находятся в сетке **Файлы базы данных** .</span><span class="sxs-lookup"><span data-stu-id="54055-122">Look in the **Database files** grid for a list of the data and log files and their properties.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="54055-123">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="54055-123">Using Transact-SQL</span></span>  
  
#### <a name="to-view-the-data-and-log-files-in-a-backup-set"></a><span data-ttu-id="54055-124">Просмотр файлов данных и журналов в резервном наборе данных</span><span class="sxs-lookup"><span data-stu-id="54055-124">To view the data and log files in a backup set</span></span>  
  
1.  <span data-ttu-id="54055-125">Установите соединение с компонентом [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="54055-125">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="54055-126">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="54055-126">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="54055-127">Используйте инструкцию [RESTORE FILELISTONLY](/sql/t-sql/statements/restore-statements-filelistonly-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="54055-127">Use the [RESTORE FILELISTONLY](/sql/t-sql/statements/restore-statements-filelistonly-transact-sql) statement.</span></span> <span data-ttu-id="54055-128">В этом примере возвращаются сведения о втором резервном наборе данных (`FILE=2`) на устройстве резервного копирования `AdventureWorksBackups` .</span><span class="sxs-lookup"><span data-stu-id="54055-128">This example returns information about the second backup set (`FILE=2`) on the `AdventureWorksBackups` backup device.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
RESTORE FILELISTONLY FROM AdventureWorksBackups   
   WITH FILE=2;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="54055-129">См. также:</span><span class="sxs-lookup"><span data-stu-id="54055-129">See Also</span></span>  
 <span data-ttu-id="54055-130">[backupfilegroup (Transact-SQL)](/sql/relational-databases/system-tables/backupfilegroup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="54055-130">[backupfilegroup &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupfilegroup-transact-sql) </span></span>  
 <span data-ttu-id="54055-131">[backupfile (Transact-SQL)](/sql/relational-databases/system-tables/backupfile-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="54055-131">[backupfile &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupfile-transact-sql) </span></span>  
 <span data-ttu-id="54055-132">[backupset (Transact-SQL)](/sql/relational-databases/system-tables/backupset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="54055-132">[backupset &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupset-transact-sql) </span></span>  
 <span data-ttu-id="54055-133">[backupmediaset (Transact-SQL)](/sql/relational-databases/system-tables/backupmediaset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="54055-133">[backupmediaset &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupmediaset-transact-sql) </span></span>  
 <span data-ttu-id="54055-134">[backupmediafamily (Transact-SQL)](/sql/relational-databases/system-tables/backupmediafamily-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="54055-134">[backupmediafamily &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupmediafamily-transact-sql) </span></span>  
 [<span data-ttu-id="54055-135">Устройства резервного копирования (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="54055-135">Backup Devices &#40;SQL Server&#41;</span></span>](backup-devices-sql-server.md)  
  
  
