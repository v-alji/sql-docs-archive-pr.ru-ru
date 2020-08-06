---
title: Удаление статистики | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- statistics [SQL Server], deleting
- deleting statistics
ms.assetid: eccce0aa-591e-4a1d-bd10-373b022f8749
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 36b74d7e1465c0742cda4fef9f34fb4b3930719c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667636"
---
# <a name="delete-statistics"></a><span data-ttu-id="d04d2-102">Удаление статистики</span><span class="sxs-lookup"><span data-stu-id="d04d2-102">Delete Statistics</span></span>
  <span data-ttu-id="d04d2-103">Удалить статистику из таблиц и представлений в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] можно с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d04d2-103">You can delete (drop) statistics from tables and views in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)]</span></span>  
  
 <span data-ttu-id="d04d2-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="d04d2-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="d04d2-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="d04d2-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="d04d2-106">Ограничения</span><span class="sxs-lookup"><span data-stu-id="d04d2-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="d04d2-107">Безопасность</span><span class="sxs-lookup"><span data-stu-id="d04d2-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="d04d2-108">**Для удаления статистики из таблицы или представления используются:**</span><span class="sxs-lookup"><span data-stu-id="d04d2-108">**To drop statistics from a table or view, using:**</span></span>  
  
     [<span data-ttu-id="d04d2-109">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d04d2-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="d04d2-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d04d2-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="d04d2-111">Перед началом</span><span class="sxs-lookup"><span data-stu-id="d04d2-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="d04d2-112">Ограничения</span><span class="sxs-lookup"><span data-stu-id="d04d2-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="d04d2-113">Будьте внимательны при удалении статистических данных.</span><span class="sxs-lookup"><span data-stu-id="d04d2-113">Be careful when you drop statistics.</span></span> <span data-ttu-id="d04d2-114">Эта операция может повлиять на план выполнения, избранный оптимизатором запросов.</span><span class="sxs-lookup"><span data-stu-id="d04d2-114">Doing so may affect the execution plan chosen by the query optimizer.</span></span>  
  
-   <span data-ttu-id="d04d2-115">Статистическая информация по индексам не может быть удалена с помощью инструкции DROP STATISTICS.</span><span class="sxs-lookup"><span data-stu-id="d04d2-115">Statistics on indexes cannot be dropped by using DROP STATISTICS.</span></span> <span data-ttu-id="d04d2-116">Статистические данные существуют, пока существует соответствующий индекс.</span><span class="sxs-lookup"><span data-stu-id="d04d2-116">Statistics remain as long as the index exists.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="d04d2-117">безопасность</span><span class="sxs-lookup"><span data-stu-id="d04d2-117">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="d04d2-118">Permissions</span><span class="sxs-lookup"><span data-stu-id="d04d2-118">Permissions</span></span>  
 <span data-ttu-id="d04d2-119">Необходимо разрешение ALTER для таблицы или представления.</span><span class="sxs-lookup"><span data-stu-id="d04d2-119">Requires ALTER permission on the table or view.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="d04d2-120">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d04d2-120">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-drop-statistics-from-a-table-or-view"></a><span data-ttu-id="d04d2-121">Удаление статистики из таблицы или представления</span><span class="sxs-lookup"><span data-stu-id="d04d2-121">To drop statistics from a table or view</span></span>  
  
1.  <span data-ttu-id="d04d2-122">В **обозревателе объектов**щелкните значок «плюс», чтобы развернуть базу данных, в которой нужно удалить статистику.</span><span class="sxs-lookup"><span data-stu-id="d04d2-122">In **Object Explorer**, click the plus sign to expand the database in which you want to delete a statistic.</span></span>  
  
2.  <span data-ttu-id="d04d2-123">Чтобы развернуть папку **Таблицы** , щелкните значок «плюс».</span><span class="sxs-lookup"><span data-stu-id="d04d2-123">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="d04d2-124">Щелкните значок «плюс», чтобы развернуть таблицу, в которой нужно удалить статистику.</span><span class="sxs-lookup"><span data-stu-id="d04d2-124">Click the plus sign to expand the table in which you want to delete a statistic.</span></span>  
  
4.  <span data-ttu-id="d04d2-125">Щелкните значок «плюс», чтобы развернуть папку **Статистика** .</span><span class="sxs-lookup"><span data-stu-id="d04d2-125">Click the plus sign to expand the **Statistics** folder.</span></span>  
  
5.  <span data-ttu-id="d04d2-126">Щелкните правой кнопкой мыши объект статистики, который нужно удалить, и выберите пункт **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="d04d2-126">Right-click the statistics object that you want to delete and select **Delete**.</span></span>  
  
6.  <span data-ttu-id="d04d2-127">В диалоговом окне **Удаление объекта** убедитесь, что выбрана правильная статистика, и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="d04d2-127">In the **Delete Object** dialog box, ensure that the correct statistic has been selected and click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="d04d2-128">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d04d2-128">Using Transact-SQL</span></span>  
  
#### <a name="to-drop-statistics-from-a-table-or-view"></a><span data-ttu-id="d04d2-129">Удаление статистики из таблицы или представления</span><span class="sxs-lookup"><span data-stu-id="d04d2-129">To drop statistics from a table or view</span></span>  
  
1.  <span data-ttu-id="d04d2-130">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d04d2-130">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="d04d2-131">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="d04d2-131">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="d04d2-132">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="d04d2-132">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- First, create two statistics named VendorCredit and CustomerTotal  
    -- The first statistic uses a random 50% sample of information provided from the Name and CreditRating columns in the Purchasing.Vendor table.  
    CREATE STATISTICS VendorCredit  
        ON Purchasing.Vendor (Name, CreditRating)  
        WITH SAMPLE 50 PERCENT  
    -- The second statistic uses all of the information from the CustomerID and TotalDue columns in the Sales.SalesOrderHeader table  
    CREATE STATISTICS CustomerTotal  
        ON Sales.SalesOrderHeader (CustomerID, TotalDue)  
        WITH FULLSCAN;  
    GO  
    -- This next statement drops both of the statistics created above. Note that the naming convention is [table_name].[statistics_name].  
    DROP STATISTICS Purchasing.Vendor.VendorCredit, Sales.SalesOrderHeader.CustomerTotal;  
    GO  
    ```  
  
 <span data-ttu-id="d04d2-133">Дополнительные сведения см. в разделе [DROP STATISTICS (Transact-SQL)](/sql/t-sql/statements/drop-statistics-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="d04d2-133">For more information, see [DROP STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-statistics-transact-sql).</span></span>  
  
  
