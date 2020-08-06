---
title: Изменение индекса | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- indexes [SQL Server], modifying
- modifying indexes
- index changes [SQL Server]
ms.assetid: 97e3110d-fde7-4f5d-9309-dc1697960aeb
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 2af9293966afce8372f5b83a579418c546c82816
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87739968"
---
# <a name="modify-an-index"></a><span data-ttu-id="4a97d-102">Изменение индекса</span><span class="sxs-lookup"><span data-stu-id="4a97d-102">Modify an Index</span></span>
  <span data-ttu-id="4a97d-103">В этом разделе описывается изменение индекса в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4a97d-103">This topic describes how to modify an index in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="4a97d-104">Индексы, созданные в результате применения ограничения PRIMARY KEY или UNIQUE, изменить этим способом нельзя.</span><span class="sxs-lookup"><span data-stu-id="4a97d-104">Indexes created as the result of a PRIMARY KEY or UNIQUE constraint cannot be modified by using this method.</span></span> <span data-ttu-id="4a97d-105">Вместо этого необходимо изменить ограничение.</span><span class="sxs-lookup"><span data-stu-id="4a97d-105">Instead, the constraint must be modified.</span></span>  
  
 <span data-ttu-id="4a97d-106">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="4a97d-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="4a97d-107">**Для изменения индекса используется:**</span><span class="sxs-lookup"><span data-stu-id="4a97d-107">**To modify an index, using:**</span></span>  
  
     [<span data-ttu-id="4a97d-108">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4a97d-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="4a97d-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4a97d-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="4a97d-110">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4a97d-110">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-modify-an-index"></a><span data-ttu-id="4a97d-111">Изменение индекса</span><span class="sxs-lookup"><span data-stu-id="4a97d-111">To modify an index</span></span>  
  
1.  <span data-ttu-id="4a97d-112">В обозревателе объектов подключитесь к экземпляру компонента [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] и разверните его.</span><span class="sxs-lookup"><span data-stu-id="4a97d-112">In Object Explorer, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="4a97d-113">Разверните **Базы данных**, затем базу данных, которой принадлежит таблица, и **Таблицы**.</span><span class="sxs-lookup"><span data-stu-id="4a97d-113">Expand **Databases**, expand the database in which the table belongs, and then expand **Tables**.</span></span>  
  
3.  <span data-ttu-id="4a97d-114">Раскройте таблицу, которой принадлежит индекс, а затем — узел **Индексы**.</span><span class="sxs-lookup"><span data-stu-id="4a97d-114">Expand the table in which the index belongs and then expand **Indexes**.</span></span>  
  
4.  <span data-ttu-id="4a97d-115">Щелкните правой кнопкой мыши индекс, который нужно изменить, и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="4a97d-115">Right-click the index that you want to modify and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="4a97d-116">В диалоговом окне **Свойства индекса** внесите необходимые изменения.</span><span class="sxs-lookup"><span data-stu-id="4a97d-116">In the **Index Properties** dialog box, make the desired changes.</span></span> <span data-ttu-id="4a97d-117">Например, можно добавить или удалить столбец из ключа индекса или изменить значение параметра индекса.</span><span class="sxs-lookup"><span data-stu-id="4a97d-117">For example, you can add or remove a column from the index key, or change the setting of an index option.</span></span>  
  
#### <a name="to-modify-index-columns"></a><span data-ttu-id="4a97d-118">Изменение столбцов индекса</span><span class="sxs-lookup"><span data-stu-id="4a97d-118">To modify index columns</span></span>  
  
1.  <span data-ttu-id="4a97d-119">Чтобы добавить столбец индекса, удалить его или изменить его позицию, выберите в диалоговом окне **Свойства индекса** страницу **Общие** .</span><span class="sxs-lookup"><span data-stu-id="4a97d-119">To add, remove, or change the position of an index column, select the **General** page from the **Index Properties** dialog box.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="4a97d-120">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4a97d-120">Using Transact-SQL</span></span>  
  
#### <a name="to-modify-an-index"></a><span data-ttu-id="4a97d-121">Изменение индекса</span><span class="sxs-lookup"><span data-stu-id="4a97d-121">To modify an index</span></span>  
  
1.  <span data-ttu-id="4a97d-122">Установите соединение с компонентом [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4a97d-122">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="4a97d-123">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="4a97d-123">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="4a97d-124">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="4a97d-124">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="4a97d-125">В этом примере индекс по столбцу `ProductID` таблицы `Production.WorkOrder` удаляется и создается вновь с помощью параметра `DROP_EXISTING` .</span><span class="sxs-lookup"><span data-stu-id="4a97d-125">This example drops and re-creates an existing index on the `ProductID` column of the `Production.WorkOrder` table by using the `DROP_EXISTING` option.</span></span> <span data-ttu-id="4a97d-126">Указываются также параметры `FILLFACTOR` и `PAD_INDEX`.</span><span class="sxs-lookup"><span data-stu-id="4a97d-126">The options `FILLFACTOR` and `PAD_INDEX` are also set.</span></span>  
  
     [!code-sql[IndexDDL#CreateIndex4](../../snippets/tsql/SQL14/tsql/indexddl/transact-sql/createindex.sql#createindex4)]  
  
     <span data-ttu-id="4a97d-127">В следующем примере с помощью инструкции ALTER INDEX задаются несколько параметров для индекса `AK_SalesOrderHeader_SalesOrderNumber`.</span><span class="sxs-lookup"><span data-stu-id="4a97d-127">The following example uses ALTER INDEX to set several options on the index `AK_SalesOrderHeader_SalesOrderNumber`.</span></span>  
  
     [!code-sql[IndexDDL#AlterIndex4](../../snippets/tsql/SQL14/tsql/indexddl/transact-sql/alterindex.sql#alterindex4)]  
  
#### <a name="to-modify-index-columns"></a><span data-ttu-id="4a97d-128">Изменение столбцов индекса</span><span class="sxs-lookup"><span data-stu-id="4a97d-128">To modify index columns</span></span>  
  
1.  <span data-ttu-id="4a97d-129">Чтобы добавить, удалить или изменить позицию столбца индекса, необходимо удалить и повторно создать индекс.</span><span class="sxs-lookup"><span data-stu-id="4a97d-129">To add, remove, or change the position of an index column, you must drop and recreate the index.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a97d-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="4a97d-130">See Also</span></span>  
 <span data-ttu-id="4a97d-131">[CREATE INDEX (Transact-SQL)](/sql/t-sql/statements/create-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4a97d-131">[CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql) </span></span>  
 <span data-ttu-id="4a97d-132">[ALTER INDEX (Transact-SQL)](/sql/t-sql/statements/alter-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4a97d-132">[ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql) </span></span>  
 <span data-ttu-id="4a97d-133">[INDEXPROPERTY (Transact-SQL)](/sql/t-sql/functions/indexproperty-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4a97d-133">[INDEXPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/indexproperty-transact-sql) </span></span>  
 <span data-ttu-id="4a97d-134">[sys.indexes (Transact-SQL)](/sql/relational-databases/system-catalog-views/sys-indexes-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4a97d-134">[sys.indexes &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-indexes-transact-sql) </span></span>  
 <span data-ttu-id="4a97d-135">[sys.index_columns (Transact-SQL)](/sql/relational-databases/system-catalog-views/sys-index-columns-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4a97d-135">[sys.index_columns &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-index-columns-transact-sql) </span></span>  
 <span data-ttu-id="4a97d-136">[Установка параметров индекса](set-index-options.md) </span><span class="sxs-lookup"><span data-stu-id="4a97d-136">[Set Index Options](set-index-options.md) </span></span>  
 [<span data-ttu-id="4a97d-137">Переименование индексов</span><span class="sxs-lookup"><span data-stu-id="4a97d-137">Rename Indexes</span></span>](indexes.md)  
  
  
