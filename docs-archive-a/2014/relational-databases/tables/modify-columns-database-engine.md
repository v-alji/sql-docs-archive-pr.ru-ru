---
title: Изменение столбцов (ядро СУБД) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- modifying data types
- column data types [SQL Server]
- data types [SQL Server], columns
ms.assetid: b67b95c5-61ef-4bd8-9a3e-1640eb7583ac
author: stevestein
ms.author: sstein
ms.openlocfilehash: a73c25d91b742f1cc1f7edcc8a95cdf226b2683c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665249"
---
# <a name="modify-columns-database-engine"></a><span data-ttu-id="3306a-102">Изменение столбцов (компонент Database Engine)</span><span class="sxs-lookup"><span data-stu-id="3306a-102">Modify Columns (Database Engine)</span></span>
  <span data-ttu-id="3306a-103">Изменить тип данных столбца в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] можно в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или в [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3306a-103">You can modify the data type of a column in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="3306a-104">Изменение типа данных столбца, в котором уже есть данные, может привести к полной потере данных при преобразовании существующих данных в новый тип.</span><span class="sxs-lookup"><span data-stu-id="3306a-104">Modifying the data type of a column that already contains data can result in the permanent loss of data when the existing data is converted to the new type.</span></span> <span data-ttu-id="3306a-105">Кроме того, код и приложения, которые используют измененный столбец, могут завершиться сбоем.</span><span class="sxs-lookup"><span data-stu-id="3306a-105">In addition, code and applications that depend on the modified column may fail.</span></span> <span data-ttu-id="3306a-106">Это касается запросов, представлений, хранимых процедур, определяемых пользователем функций и клиентских приложений.</span><span class="sxs-lookup"><span data-stu-id="3306a-106">These include queries, views, stored procedures, user-defined functions, and client applications.</span></span> <span data-ttu-id="3306a-107">Следует иметь в виду, что возникновение ошибок происходит каскадом.</span><span class="sxs-lookup"><span data-stu-id="3306a-107">Note that these failures will cascade.</span></span> <span data-ttu-id="3306a-108">Например, может произойти сбой хранимой процедуры, которая вызывает определяемую пользователем функцию, зависящую от изменяемого столбца.</span><span class="sxs-lookup"><span data-stu-id="3306a-108">For example, a stored procedure that calls a user-defined function that depends on the modified column may fail.</span></span> <span data-ttu-id="3306a-109">Внимательно рассмотрите любые изменения, которые необходимо сделать со столбцом таблицы.</span><span class="sxs-lookup"><span data-stu-id="3306a-109">Carefully consider any changes you want to make to a column before making it.</span></span>  
  
 <span data-ttu-id="3306a-110">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="3306a-110">**In This Topic**</span></span>  
  
-   <span data-ttu-id="3306a-111">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="3306a-111">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="3306a-112">Безопасность</span><span class="sxs-lookup"><span data-stu-id="3306a-112">Security</span></span>](#Security)  
  
-   <span data-ttu-id="3306a-113">**Изменение типа данных столбца с помощью следующих средств:**</span><span class="sxs-lookup"><span data-stu-id="3306a-113">**To modify the data type of a column, using:**</span></span>  
  
     [<span data-ttu-id="3306a-114">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3306a-114">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="3306a-115">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="3306a-115">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="3306a-116">Перед началом</span><span class="sxs-lookup"><span data-stu-id="3306a-116">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="3306a-117">безопасность</span><span class="sxs-lookup"><span data-stu-id="3306a-117">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="3306a-118">Permissions</span><span class="sxs-lookup"><span data-stu-id="3306a-118">Permissions</span></span>  
 <span data-ttu-id="3306a-119">Требуется разрешение ALTER на таблицу.</span><span class="sxs-lookup"><span data-stu-id="3306a-119">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="3306a-120">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3306a-120">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-modify-the-data-type-of-a-column"></a><span data-ttu-id="3306a-121">Изменение типа данных столбца</span><span class="sxs-lookup"><span data-stu-id="3306a-121">To modify the data type of a column</span></span>  
  
1.  <span data-ttu-id="3306a-122">В **Обозревателе объектов**щелкните правой кнопкой мыши таблицу со столбцами, масштаб которых необходимо изменить, и выберите пункт **Конструктор**.</span><span class="sxs-lookup"><span data-stu-id="3306a-122">In **Object Explorer**, right-click the table with columns for which you want to change the scale and click **Design**.</span></span>  
  
2.  <span data-ttu-id="3306a-123">Выберите столбец, тип данных которого планируется изменить.</span><span class="sxs-lookup"><span data-stu-id="3306a-123">Select the column for which you want to modify the data type.</span></span>  
  
3.  <span data-ttu-id="3306a-124">На вкладке **Свойства столбца** выберите ячейку сетки для свойства **Тип данных** и выберите новый тип данных из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="3306a-124">In the **Column Properties** tab, click the grid cell for the **Data Type** property and choose a new data type from the drop-down list.</span></span>  
  
4.  <span data-ttu-id="3306a-125">В меню **Файл** выберите пункт **Сохранить**_table name_.</span><span class="sxs-lookup"><span data-stu-id="3306a-125">On the **File** menu, click **Save**_table name_.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3306a-126">При изменении типа данных столбца конструктор таблиц применяет длину типа данных, определенную по умолчанию для выбранного типа данных, даже если была указана другая длина.</span><span class="sxs-lookup"><span data-stu-id="3306a-126">When you modify the data type of a column, Table Designer applies the default length of the data type you selected, even if you have already specified another.</span></span> <span data-ttu-id="3306a-127">Всегда устанавливайте необходимое значение длины типа данных после того, как был указан тип данных.</span><span class="sxs-lookup"><span data-stu-id="3306a-127">Always set the data type length for to the desired value after specifying the data type.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="3306a-128">При попытке изменения типа данных столбца, связанного с другими таблицами, конструктор таблиц запрашивает подтверждение на внесение изменений и в столбцы других таблиц.</span><span class="sxs-lookup"><span data-stu-id="3306a-128">If you attempt to modify the data type of a column that relates to other tables, Table Designer asks you to confirm that the change should be made to the columns in the other tables as well.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="3306a-129">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="3306a-129">Using Transact-SQL</span></span>  
  
#### <a name="to-modify-the-data-type-of-a-column"></a><span data-ttu-id="3306a-130">Изменение типа данных столбца</span><span class="sxs-lookup"><span data-stu-id="3306a-130">To modify the data type of a column</span></span>  
  
1.  <span data-ttu-id="3306a-131">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3306a-131">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="3306a-132">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="3306a-132">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="3306a-133">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="3306a-133">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    CREATE TABLE dbo.doc_exy (column_a INT ) ;  
    GO  
    INSERT INTO dbo.doc_exy (column_a) VALUES (10) ;  
    GO  
    ALTER TABLE dbo.doc_exy ALTER COLUMN column_a DECIMAL (5, 2) ;  
    GO  
  
    ```  
  
 <span data-ttu-id="3306a-134">Дополнительные сведения см. в разделе [ALTER TABLE (Transact-SQL)](/sql/t-sql/statements/alter-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="3306a-134">For more information, see [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql)</span></span>  
  
  
