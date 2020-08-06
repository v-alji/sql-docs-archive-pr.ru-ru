---
title: Удаление базы данных | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- database removal [SQL Server], SQL Server Management Studio
- removing databases
- deleting databases
- dropping databases
- databases [SQL Server], dropping
- database removal [SQL Server]
ms.assetid: 1fd8c0f5-03e1-449a-af45-b8cacb479d9c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 633d97815cf69da12f1aa67fd8ef626a2d46e0b0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751096"
---
# <a name="delete-a-database"></a><span data-ttu-id="f04c8-102">Удаление базы данных</span><span class="sxs-lookup"><span data-stu-id="f04c8-102">Delete a Database</span></span>
  <span data-ttu-id="f04c8-103">В этом подразделе описывается, как удалить пользовательскую базу данных в [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f04c8-103">This topic describes how to delete a user-defined database in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="f04c8-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="f04c8-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="f04c8-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="f04c8-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="f04c8-106">Ограничения</span><span class="sxs-lookup"><span data-stu-id="f04c8-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="f04c8-107">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="f04c8-107">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="f04c8-108">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="f04c8-108">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="f04c8-109">Безопасность</span><span class="sxs-lookup"><span data-stu-id="f04c8-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="f04c8-110">**Удаление базы данных с использованием следующих средств:**</span><span class="sxs-lookup"><span data-stu-id="f04c8-110">**To delete a database, using:**</span></span>  
  
     [<span data-ttu-id="f04c8-111">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f04c8-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="f04c8-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f04c8-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="f04c8-113">**Дальнейшие действия.**  [После удаления базы данных](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="f04c8-113">**Follow Up:**  [After deleting a database](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="f04c8-114">Перед началом</span><span class="sxs-lookup"><span data-stu-id="f04c8-114">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="f04c8-115">Ограничения</span><span class="sxs-lookup"><span data-stu-id="f04c8-115">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="f04c8-116">Системные базы данных не могут быть удалены.</span><span class="sxs-lookup"><span data-stu-id="f04c8-116">System databases cannot be deleted.</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="f04c8-117">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="f04c8-117">Prerequisites</span></span>  
  
-   <span data-ttu-id="f04c8-118">Удалите все моментальные снимки базы данных, которые существуют для базы.</span><span class="sxs-lookup"><span data-stu-id="f04c8-118">Delete any database snapshots that exist on the database.</span></span> <span data-ttu-id="f04c8-119">Дополнительные сведения см. в разделе [Удаление моментального снимка базы данных (Transact-SQL)](drop-a-database-snapshot-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="f04c8-119">For more information, see [Drop a Database Snapshot &#40;Transact-SQL&#41;](drop-a-database-snapshot-transact-sql.md).</span></span>  
  
-   <span data-ttu-id="f04c8-120">Если база данных участвует в доставке журналов, удалите доставку журналов.</span><span class="sxs-lookup"><span data-stu-id="f04c8-120">If the database is involved in log shipping, remove log shipping.</span></span>  
  
-   <span data-ttu-id="f04c8-121">Если база данных публикуется для репликации транзакций, опубликована или подписана на репликацию слиянием, удалите репликацию из базы данных.</span><span class="sxs-lookup"><span data-stu-id="f04c8-121">If the database is published for transactional replication, or published or subscribed to merge replication, remove replication from the database.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="f04c8-122">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="f04c8-122">Recommendations</span></span>  
  
-   <span data-ttu-id="f04c8-123">Учтите возможность полного резервного копирования базы данных.</span><span class="sxs-lookup"><span data-stu-id="f04c8-123">Consider taking a full backup of the database.</span></span> <span data-ttu-id="f04c8-124">Удаленную базу данных можно восстановить только с помощью резервной копии.</span><span class="sxs-lookup"><span data-stu-id="f04c8-124">A deleted database can be re-created only by restoring a backup.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="f04c8-125">безопасность</span><span class="sxs-lookup"><span data-stu-id="f04c8-125">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="f04c8-126">Permissions</span><span class="sxs-lookup"><span data-stu-id="f04c8-126">Permissions</span></span>  
 <span data-ttu-id="f04c8-127">Для выполнения инструкции DROP DATABASE пользователь должен, как минимум, иметь разрешение CONTROL на базу данных.</span><span class="sxs-lookup"><span data-stu-id="f04c8-127">To execute DROP DATABASE, at a minimum, a user must have CONTROL permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="f04c8-128">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f04c8-128">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-a-database"></a><span data-ttu-id="f04c8-129">Удаление базы данных</span><span class="sxs-lookup"><span data-stu-id="f04c8-129">To delete a database</span></span>  
  
1.  <span data-ttu-id="f04c8-130">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]и разверните его.</span><span class="sxs-lookup"><span data-stu-id="f04c8-130">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="f04c8-131">Разверните **Базы данных**, щелкните правой кнопкой мыши удаляемую базу данных и затем нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="f04c8-131">Expand **Databases**, right-click the database to delete, and then click **Delete**.</span></span>  
  
3.  <span data-ttu-id="f04c8-132">Подтвердите, что выбрана верная база данных, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="f04c8-132">Confirm the correct database is selected, and then click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="f04c8-133">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f04c8-133">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-a-database"></a><span data-ttu-id="f04c8-134">Удаление базы данных</span><span class="sxs-lookup"><span data-stu-id="f04c8-134">To delete a database</span></span>  
  
1.  <span data-ttu-id="f04c8-135">Установите соединение с компонентом [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f04c8-135">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="f04c8-136">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="f04c8-136">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="f04c8-137">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="f04c8-137">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="f04c8-138">В следующем примере удаляются базы данных `Sales` и `NewSales` .</span><span class="sxs-lookup"><span data-stu-id="f04c8-138">The example removes the `Sales` and `NewSales` databases.</span></span>  
  
```sql  
USE master ;  
GO  
DROP DATABASE Sales, NewSales ;  
GO  
```  
  
##  <a name="follow-up-after-deleting-a-database"></a><a name="FollowUp"></a> <span data-ttu-id="f04c8-139">Дальнейшие действия. После удаления базы данных</span><span class="sxs-lookup"><span data-stu-id="f04c8-139">Follow Up: After deleting a database</span></span>  
 <span data-ttu-id="f04c8-140">Создание резервной копии базы данных **master** .</span><span class="sxs-lookup"><span data-stu-id="f04c8-140">Back up the **master** database.</span></span> <span data-ttu-id="f04c8-141">Если необходимо восстановить базу данных **master** , любая база данных, удаленная с момента создания последней резервной копии базы данных **master** , останется в представлениях системного каталога и может вызвать сообщения об ошибках.</span><span class="sxs-lookup"><span data-stu-id="f04c8-141">If **master** must be restored, any database that has been deleted since the last backup of **master** will still have references in the system catalog views and may cause error messages to be raised.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f04c8-142">См. также:</span><span class="sxs-lookup"><span data-stu-id="f04c8-142">See Also</span></span>  
 <span data-ttu-id="f04c8-143">[CREATE DATABASE (SQL Server Transact-SQL)](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f04c8-143">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span></span>  
 [<span data-ttu-id="f04c8-144">ALTER DATABASE (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="f04c8-144">ALTER DATABASE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql)  
  
  
