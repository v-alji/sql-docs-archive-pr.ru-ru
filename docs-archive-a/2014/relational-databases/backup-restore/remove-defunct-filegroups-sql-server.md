---
title: Удаление несуществующих файловых групп (SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- piecemeal restores [SQL Server], defunct filegroups
- defunct filegroups
- restoring filegroups [SQL Server]
- deferred transactions
- filegroups [SQL Server], defunct
- unrestored filegroups
ms.assetid: 055f9c6a-5c18-4942-98e7-ec918f0ff975
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: a2bcba095d668c5c1ab317269a18af4dc996f63b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87736431"
---
# <a name="remove-defunct-filegroups-sql-server"></a><span data-ttu-id="495aa-102">Удаление уничтоженных файловых групп (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="495aa-102">Remove Defunct Filegroups (SQL Server)</span></span>
  <span data-ttu-id="495aa-103">В этом разделе описывается удаление уничтоженных файловых групп в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="495aa-103">This topic describes how to remove defunct filegroups in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="495aa-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="495aa-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="495aa-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="495aa-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="495aa-106">Ограничения</span><span class="sxs-lookup"><span data-stu-id="495aa-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
-   [<span data-ttu-id="495aa-107">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="495aa-107">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="495aa-108">Безопасность</span><span class="sxs-lookup"><span data-stu-id="495aa-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="495aa-109">**Удаление уничтоженных файловых групп с использованием следующих средств:**</span><span class="sxs-lookup"><span data-stu-id="495aa-109">**To remove defunct filegroups, using:**</span></span>  
  
     [<span data-ttu-id="495aa-110">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="495aa-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="495aa-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="495aa-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="495aa-112">Перед началом</span><span class="sxs-lookup"><span data-stu-id="495aa-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="495aa-113">Ограничения</span><span class="sxs-lookup"><span data-stu-id="495aa-113">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="495aa-114">Сведения в этом разделе относятся к базам данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , содержащим несколько файлов или файловых групп (а для простой модели восстановления — к файловым группам, доступным только для чтения).</span><span class="sxs-lookup"><span data-stu-id="495aa-114">This topic is relevant for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases that contain multiple files or filegroups; and, under the simple model, only for read-only filegroups.</span></span>  
  
-   <span data-ttu-id="495aa-115">При удалении файловой группы вне сети все файлы группы помечаются удаленными.</span><span class="sxs-lookup"><span data-stu-id="495aa-115">All files in a filegroup become defunct when an offline filegroup is removed.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="495aa-116">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="495aa-116">Recommendations</span></span>  
  
-   <span data-ttu-id="495aa-117">Если восстановление невосстановленной файловой группы не предполагается, необходимо сделать ее *уничтоженной* , удалив из базы данных.</span><span class="sxs-lookup"><span data-stu-id="495aa-117">If an unrestored filegroup will never have to be restored, you can make the filegroup *defunct* by removing it from the database.</span></span> <span data-ttu-id="495aa-118">Такая файловая группа не может быть восстановлена в данной базе данных, однако при этом сохраняются ее метаданные.</span><span class="sxs-lookup"><span data-stu-id="495aa-118">The defunct filegroup can never be restored to this database, but its metadata remains.</span></span> <span data-ttu-id="495aa-119">После того как файловая группа стала уничтоженной, базу данных можно перезапустить, и в процессе восстановления будет восстановлена согласованность базы данных между восстановленными файловыми группами.</span><span class="sxs-lookup"><span data-stu-id="495aa-119">After the filegroup is defunct, the database can be restarted, and recovery will make the database consistent across the restored filegroups.</span></span>  
  
     <span data-ttu-id="495aa-120">Например, объявление файловой группы как нефункционирующей позволяет разрешить отложенные транзакции, возникшие из-за файловой группы вне сети, которая больше не нужна в базе данных.</span><span class="sxs-lookup"><span data-stu-id="495aa-120">For example, making a filegroup defunct is an option for resolving deferred transactions that were caused by an offline filegroup that you no longer want in the database.</span></span> <span data-ttu-id="495aa-121">Транзакции, отложенные из-за того, что файловая группа находилась в режиме «вне сети», выходят из отложенного состояния после того, как эта файловая группа перестанет функционировать.</span><span class="sxs-lookup"><span data-stu-id="495aa-121">Transactions that were deferred because the filegroup was offline are moved out of the deferred state after the filegroup becomes defunct.</span></span> <span data-ttu-id="495aa-122">Дополнительные сведения см. в разделе [Отложенные транзакции (SQL Server)](deferred-transactions-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="495aa-122">For more information, see [Deferred Transactions &#40;SQL Server&#41;](deferred-transactions-sql-server.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="495aa-123">безопасность</span><span class="sxs-lookup"><span data-stu-id="495aa-123">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="495aa-124">Permissions</span><span class="sxs-lookup"><span data-stu-id="495aa-124">Permissions</span></span>  
 <span data-ttu-id="495aa-125">Необходимо разрешение ALTER на базу данных.</span><span class="sxs-lookup"><span data-stu-id="495aa-125">Requires ALTER permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="495aa-126">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="495aa-126">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-remove-defunct-filegroups"></a><span data-ttu-id="495aa-127">Удаление уничтоженных файловых групп</span><span class="sxs-lookup"><span data-stu-id="495aa-127">To remove defunct filegroups</span></span>  
  
1.  <span data-ttu-id="495aa-128">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] и разверните его.</span><span class="sxs-lookup"><span data-stu-id="495aa-128">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="495aa-129">Раскройте список **Базы данных**, щелкните правой кнопкой мыши базу данных, из которой удаляется файл, а затем выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="495aa-129">Expand **Databases**, right-click the database from which to delete the file, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="495aa-130">Выберите страницу **Файлы** .</span><span class="sxs-lookup"><span data-stu-id="495aa-130">Select the **Files** page.</span></span>  
  
4.  <span data-ttu-id="495aa-131">В списке **Файлы базы данных** выберите файлы для удаления, нажмите кнопку **Удалить**, а затем кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="495aa-131">In the **Database files** grid, select the files to delete, click **Remove**, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="495aa-132">Выберите страницу **Файловые группы** .</span><span class="sxs-lookup"><span data-stu-id="495aa-132">Select the **Filegroups** page.</span></span>  
  
6.  <span data-ttu-id="495aa-133">В списке **Строки** выберите файловую группу для удаления, нажмите кнопку **Удалить**, а затем кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="495aa-133">In the **Rows** grid, select the filegroup to delete, click **Remove**, and then click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="495aa-134">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="495aa-134">Using Transact-SQL</span></span>  
  
#### <a name="to-remove-defunct-filegroups"></a><span data-ttu-id="495aa-135">Удаление уничтоженных файловых групп</span><span class="sxs-lookup"><span data-stu-id="495aa-135">To remove defunct filegroups</span></span>  
  
1.  <span data-ttu-id="495aa-136">Установите соединение с компонентом [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="495aa-136">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="495aa-137">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="495aa-137">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="495aa-138">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="495aa-138">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="495aa-139">(**Примечание**. В этом примере предполагается, что файлы и файловая группа уже существуют.</span><span class="sxs-lookup"><span data-stu-id="495aa-139">(**Note:** This example assumes that the files and filegroup already exist.</span></span> <span data-ttu-id="495aa-140">Для создания этих объектов см. пример Б в разделе [Параметры инструкции ALTER DATABASE для файлов и файловых групп](/sql/t-sql/statements/alter-database-transact-sql-file-and-filegroup-options).) В первом примере удаляются файлы `test1dat3` и `test1dat4` из уничтоженной файловой группы с помощью инструкции `ALTER DATABASE` с предложением `REMOVE FILE`.</span><span class="sxs-lookup"><span data-stu-id="495aa-140">To create these objects, see example B in the [ALTER DATABASE File and Filegroup Options](/sql/t-sql/statements/alter-database-transact-sql-file-and-filegroup-options) topic.) The first example removes the `test1dat3` and `test1dat4` files from the defunct filegroup by using the `ALTER DATABASE` statement with the `REMOVE FILE` clause.</span></span> <span data-ttu-id="495aa-141">Во втором примере удаляется уничтоженная файловая группа `Test1FG1`с помощью предложения `REMOVE FILEGROUP` .</span><span class="sxs-lookup"><span data-stu-id="495aa-141">The second example removes the defunct filegroup `Test1FG1`by using the `REMOVE FILEGROUP` clause.</span></span>  
  
```sql  
USE master;  
GO  
ALTER DATABASE AdventureWorks2012  
REMOVE FILE test1dat3 ;  
ALTER DATABASE AdventureWorks2012  
REMOVE FILE test1dat4 ;  
GO  
  
```  
  
```sql  
USE master;  
GO  
ALTER DATABASE AdventureWorks2012  
REMOVE FILEGROUP Test1FG1 ;  
GO  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="495aa-142">См. также:</span><span class="sxs-lookup"><span data-stu-id="495aa-142">See Also</span></span>  
 <span data-ttu-id="495aa-143">[Параметры инструкции ALTER DATABASE для файлов и файловых групп (Transact-SQL)](/sql/t-sql/statements/alter-database-transact-sql-file-and-filegroup-options) </span><span class="sxs-lookup"><span data-stu-id="495aa-143">[ALTER DATABASE File and Filegroup Options &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-file-and-filegroup-options) </span></span>  
 <span data-ttu-id="495aa-144">[Отложенные транзакции (SQL Server)](deferred-transactions-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="495aa-144">[Deferred Transactions &#40;SQL Server&#41;](deferred-transactions-sql-server.md) </span></span>  
 <span data-ttu-id="495aa-145">[Восстановления файлов (модель полного восстановления)](file-restores-full-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="495aa-145">[File Restores &#40;Full Recovery Model&#41;](file-restores-full-recovery-model.md) </span></span>  
 <span data-ttu-id="495aa-146">[Восстановление файлов (простая модель восстановления)](file-restores-simple-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="495aa-146">[File Restores &#40;Simple Recovery Model&#41;](file-restores-simple-recovery-model.md) </span></span>  
 <span data-ttu-id="495aa-147">[Восстановление в сети (SQL Server)](online-restore-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="495aa-147">[Online Restore &#40;SQL Server&#41;](online-restore-sql-server.md) </span></span>  
 <span data-ttu-id="495aa-148">[Восстановление страниц (SQL Server)](restore-pages-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="495aa-148">[Restore Pages &#40;SQL Server&#41;](restore-pages-sql-server.md) </span></span>  
 [<span data-ttu-id="495aa-149">Поэтапное восстановление (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="495aa-149">Piecemeal Restores &#40;SQL Server&#41;</span></span>](piecemeal-restores-sql-server.md)  
  
  
