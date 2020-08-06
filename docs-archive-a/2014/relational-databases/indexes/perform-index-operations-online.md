---
title: Выполнение операций с индексами в сети | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- index online operations [SQL Server]
- online index operations
- ONLINE option
ms.assetid: 1e43537c-bf67-4db3-9908-3cb45c6fdaa1
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 4d09bd99a0eaec5fdb433bd8c33351d7622957a2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668308"
---
# <a name="perform-index-operations-online"></a><span data-ttu-id="259f6-102">Выполнение операции с индексами в сети</span><span class="sxs-lookup"><span data-stu-id="259f6-102">Perform Index Operations Online</span></span>
  <span data-ttu-id="259f6-103">В этом разделе описывается создание, перестроение и удаление индексов в режиме «в сети» в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] и [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="259f6-103">This topic describes how to create, rebuild, or drop indexes online in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="259f6-104">Параметр ONLINE разрешает одновременный доступ пользователей к базовой таблице или данным кластеризованного индекса и всем связанным некластеризованным индексам во время выполнения этих операций с индексами.</span><span class="sxs-lookup"><span data-stu-id="259f6-104">The ONLINE option allows concurrent user access to the underlying table or clustered index data and any associated nonclustered indexes during these index operations.</span></span> <span data-ttu-id="259f6-105">Например, пока пользователь перестраивает кластеризованный индекс, он и другие пользователи могут продолжать обновление базовых данных и осуществлять к ним запросы.</span><span class="sxs-lookup"><span data-stu-id="259f6-105">For example, while a clustered index is being rebuilt by one user, that user and others can continue to update and query the underlying data.</span></span> <span data-ttu-id="259f6-106">Если операции языка описания данных DDL (DDL), такие как построение или перестроение кластеризованного индекса, выполняются в режиме «вне сети», то они удерживают монопольные блокировки на базовые данные и связанные индексы.</span><span class="sxs-lookup"><span data-stu-id="259f6-106">When you perform data definition language (DDL) operations offline, such as building or rebuilding a clustered index; these operations hold exclusive locks on the underlying data and associated indexes.</span></span> <span data-ttu-id="259f6-107">Это предотвращает изменение базовых данных и осуществление запросов к ним до завершения операции с индексами.</span><span class="sxs-lookup"><span data-stu-id="259f6-107">This prevents modifications and queries to the underlying data until the index operation is complete.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="259f6-108">Операции с индексами в сети доступны не во всех выпусках [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="259f6-108">Online index operations are not available in every [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] edition.</span></span> <span data-ttu-id="259f6-109">Дополнительные сведения см. [в разделе функции, поддерживаемые различными Выпусками SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="259f6-109">For more information, see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
 <span data-ttu-id="259f6-110">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="259f6-110">**In This Topic**</span></span>  
  
-   <span data-ttu-id="259f6-111">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="259f6-111">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="259f6-112">Ограничения</span><span class="sxs-lookup"><span data-stu-id="259f6-112">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="259f6-113">Безопасность</span><span class="sxs-lookup"><span data-stu-id="259f6-113">Security</span></span>](#Security)  
  
-   <span data-ttu-id="259f6-114">**Для перестроения индекса в режиме «в сети» используется:**</span><span class="sxs-lookup"><span data-stu-id="259f6-114">**To rebuild an index online, using:**</span></span>  
  
     [<span data-ttu-id="259f6-115">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="259f6-115">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="259f6-116">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="259f6-116">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="259f6-117">Перед началом</span><span class="sxs-lookup"><span data-stu-id="259f6-117">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="259f6-118">Ограничения</span><span class="sxs-lookup"><span data-stu-id="259f6-118">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="259f6-119">Рекомендуется выполнять операции с индексами в сети в производственной среде, работающей 24 часа в сутки и семь дней в неделю, когда имеется насущная необходимость одновременных действий пользователей во время выполнения операций с индексами.</span><span class="sxs-lookup"><span data-stu-id="259f6-119">We recommend performing online index operations for business environments that operate 24 hours a day, seven days a week, in which the need for concurrent user activity during index operations is vital.</span></span>  
  
-   <span data-ttu-id="259f6-120">Параметр ONLINE доступен в следующих инструкциях языка [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="259f6-120">The ONLINE option is available in the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statements.</span></span>  
  
    -   [<span data-ttu-id="259f6-121">CREATE INDEX</span><span class="sxs-lookup"><span data-stu-id="259f6-121">CREATE INDEX</span></span>](/sql/t-sql/statements/create-index-transact-sql)  
  
    -   [<span data-ttu-id="259f6-122">ALTER INDEX</span><span class="sxs-lookup"><span data-stu-id="259f6-122">ALTER INDEX</span></span>](/sql/t-sql/statements/alter-index-transact-sql)  
  
    -   [<span data-ttu-id="259f6-123">DROP INDEX</span><span class="sxs-lookup"><span data-stu-id="259f6-123">DROP INDEX</span></span>](/sql/t-sql/statements/drop-index-transact-sql)  
  
    -   <span data-ttu-id="259f6-124">[ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql) (чтобы добавить или удалить ограничения UNIQUE или PRIMARY KEY с параметром индекса CLUSTERED)</span><span class="sxs-lookup"><span data-stu-id="259f6-124">[ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql) (To add or drop UNIQUE or PRIMARY KEY constraints with CLUSTERED index option)</span></span>  
  
-   <span data-ttu-id="259f6-125">Дополнительные ограничения и ограничения, касающиеся создания, восстановления или удаления индексов в режиме "в сети", см. в разделе [Инструкции по операциям с индексами в сети](guidelines-for-online-index-operations.md).</span><span class="sxs-lookup"><span data-stu-id="259f6-125">For more limitations and restrictions concerning creating, rebuilding, or dropping indexes online, see [Guidelines for Online Index Operations](guidelines-for-online-index-operations.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="259f6-126">безопасность</span><span class="sxs-lookup"><span data-stu-id="259f6-126">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="259f6-127">Permissions</span><span class="sxs-lookup"><span data-stu-id="259f6-127">Permissions</span></span>  
 <span data-ttu-id="259f6-128">Необходимо разрешение ALTER для таблицы или представления.</span><span class="sxs-lookup"><span data-stu-id="259f6-128">Requires ALTER permission on the table or view.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="259f6-129">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="259f6-129">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-rebuild-an-index-online"></a><span data-ttu-id="259f6-130">Перестроение индекса в режиме «в сети»</span><span class="sxs-lookup"><span data-stu-id="259f6-130">To rebuild an index online</span></span>  
  
1.  <span data-ttu-id="259f6-131">В обозревателе объектов щелкните знак «плюс», чтобы развернуть базу данных, содержащую таблицу, в которой необходимо перестроить индекс в режиме «в сети».</span><span class="sxs-lookup"><span data-stu-id="259f6-131">In Object Explorer, click the plus sign to expand the database that contains the table on which you want to rebuild an index online.</span></span>  
  
2.  <span data-ttu-id="259f6-132">Разверните папку **Таблицы**.</span><span class="sxs-lookup"><span data-stu-id="259f6-132">Expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="259f6-133">Щелкните знак «плюс», чтобы развернуть таблицу, в которой необходимо перестроить индекс в режиме «в сети».</span><span class="sxs-lookup"><span data-stu-id="259f6-133">Click the plus sign to expand the table on which you want to rebuild an index online.</span></span>  
  
4.  <span data-ttu-id="259f6-134">Разверните папку **Индексы**.</span><span class="sxs-lookup"><span data-stu-id="259f6-134">Expand the **Indexes** folder.</span></span>  
  
5.  <span data-ttu-id="259f6-135">Щелкните правой кнопкой мыши индекс, который нужно перестроить в режиме "в сети", и выберите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="259f6-135">Right-click the index that you want to rebuild online and select **Properties**.</span></span>  
  
6.  <span data-ttu-id="259f6-136">В разделе **Выбор страницы**щелкните **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="259f6-136">Under **Select a page**, select **Options**.</span></span>  
  
7.  <span data-ttu-id="259f6-137">Выберите свойство **Разрешить обработку DML в сети**и выберите из списка значение **True** .</span><span class="sxs-lookup"><span data-stu-id="259f6-137">Select **Allow online DML processing**, and then select **True** from the list.</span></span>  
  
8.  <span data-ttu-id="259f6-138">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="259f6-138">Click **OK**.</span></span>  
  
9. <span data-ttu-id="259f6-139">Щелкните правой кнопкой мыши индекс, который нужно перестроить в режиме "в сети", и выберите пункт **Перестроить**.</span><span class="sxs-lookup"><span data-stu-id="259f6-139">Right-click the index that you want to rebuild online and select **Rebuild**.</span></span>  
  
10. <span data-ttu-id="259f6-140">В диалоговом окне **Перестроение индексов** убедитесь, что нужный индекс приведен в сетке **Индексы для перестройки** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="259f6-140">In the **Rebuild Indexes** dialog box, verify that the correct index is in the **Indexes to rebuild** grid and click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="259f6-141">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="259f6-141">Using Transact-SQL</span></span>  
  
#### <a name="to-create-rebuild-or-drop-an-index-online"></a><span data-ttu-id="259f6-142">Создание, перестроение и удаление индекса в режиме «в сети»</span><span class="sxs-lookup"><span data-stu-id="259f6-142">To create, rebuild, or drop an index online</span></span>  
  
1.  <span data-ttu-id="259f6-143">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="259f6-143">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="259f6-144">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="259f6-144">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="259f6-145">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="259f6-145">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="259f6-146">В примере перестраивается существующий индекс в режиме «в сети»</span><span class="sxs-lookup"><span data-stu-id="259f6-146">The example rebuilds an existing online</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    ALTER INDEX AK_Employee_NationalIDNumber ON HumanResources.Employee  
    REBUILD WITH (ONLINE = ON);  
    GO  
    ```  
  
     <span data-ttu-id="259f6-147">В следующем примере кластеризованный индекс удаляется в режиме в сети и результирующая таблица (куча) перемещается в файловую группу `NewGroup` с использованием предложения `MOVE TO` .</span><span class="sxs-lookup"><span data-stu-id="259f6-147">The following example deletes a clustered index online and moves the resulting table (heap) to the filegroup `NewGroup` by using the `MOVE TO` clause.</span></span> <span data-ttu-id="259f6-148">Представления каталога `sys.indexes`, `sys.tables`и `sys.filegroups` запрашиваются для проверки размещения индекса и таблицы в файловых группах до и после перемещения.</span><span class="sxs-lookup"><span data-stu-id="259f6-148">The `sys.indexes`, `sys.tables`, and `sys.filegroups` catalog views are queried to verify the index and table placement in the filegroups before and after the move.</span></span>  
  
     [!code-sql[IndexDDL#DropIndex4](../../snippets/tsql/SQL14/tsql/indexddl/transact-sql/dropindex.sql#dropindex4)]  
  
 <span data-ttu-id="259f6-149">Дополнительные сведения см. в разделе [ALTER INDEX (Transact-SQL)](/sql/t-sql/statements/alter-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="259f6-149">For more information, see [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql).</span></span>  
  
  
