---
title: Изменение данных через представление | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- data modifications [SQL Server], views
- views [SQL Server], modifying data through
- modifying data [SQL Server], views
ms.assetid: 410e2812-4ebe-48b2-b95f-c7784f1c4336
author: stevestein
ms.author: sstein
ms.openlocfilehash: df1eb4a33d1d10e63363e52760dad805b20c0a8f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654971"
---
# <a name="modify-data-through-a-view"></a><span data-ttu-id="dea8d-102">Изменение данных через представление</span><span class="sxs-lookup"><span data-stu-id="dea8d-102">Modify Data Through a View</span></span>
  <span data-ttu-id="dea8d-103">Изменить данные столбца базовой таблицы можно в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dea8d-103">You can modify the data of an underlying base table in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="dea8d-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="dea8d-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="dea8d-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="dea8d-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="dea8d-106">Ограничения</span><span class="sxs-lookup"><span data-stu-id="dea8d-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="dea8d-107">Безопасность</span><span class="sxs-lookup"><span data-stu-id="dea8d-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="dea8d-108">**Изменение данных таблицы с помощью представления с использованием следующих средств:**</span><span class="sxs-lookup"><span data-stu-id="dea8d-108">**To modify table data through a view, using:**</span></span>  
  
     [<span data-ttu-id="dea8d-109">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="dea8d-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="dea8d-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="dea8d-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="dea8d-111">Перед началом</span><span class="sxs-lookup"><span data-stu-id="dea8d-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="dea8d-112">Ограничения</span><span class="sxs-lookup"><span data-stu-id="dea8d-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="dea8d-113">См. раздел "Обновляемые представления" статьи [CREATE VIEW (Transact-SQL)](/sql/t-sql/statements/create-view-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="dea8d-113">See the section 'Updatable Views' in [CREATE VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-view-transact-sql).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="dea8d-114">безопасность</span><span class="sxs-lookup"><span data-stu-id="dea8d-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="dea8d-115">Permissions</span><span class="sxs-lookup"><span data-stu-id="dea8d-115">Permissions</span></span>  
 <span data-ttu-id="dea8d-116">Необходимы разрешения UPDATE, INSERT или DELETE для целевой таблицы в зависимости от выполняемого действия.</span><span class="sxs-lookup"><span data-stu-id="dea8d-116">Requires UPDATE, INSERT, or DELETE permissions on the target table, depending on the action being performed.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="dea8d-117">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="dea8d-117">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-modify-table-data-through-a-view"></a><span data-ttu-id="dea8d-118">Изменение данных таблицы с помощью представления</span><span class="sxs-lookup"><span data-stu-id="dea8d-118">To modify table data through a view</span></span>  
  
1.  <span data-ttu-id="dea8d-119">В **обозревателе объектов**разверните базу данных, содержащую представление, а затем разверните **Представления**.</span><span class="sxs-lookup"><span data-stu-id="dea8d-119">In **Object Explorer**, expand the database that contains the view and then expand **Views**.</span></span>  
  
2.  <span data-ttu-id="dea8d-120">Щелкните правой кнопкой мыши представление и выберите **Изменить 200 верхних строк**.</span><span class="sxs-lookup"><span data-stu-id="dea8d-120">Right-click the view and select **Edit Top 200 Rows**.</span></span>  
  
3.  <span data-ttu-id="dea8d-121">Может потребоваться изменение инструкции SELECT на панели **SQL** для получения строк, которые необходимо изменить.</span><span class="sxs-lookup"><span data-stu-id="dea8d-121">You may need to modify the SELECT statement in the **SQL** pane to return the rows to be modified.</span></span>  
  
4.  <span data-ttu-id="dea8d-122">На панели **Результаты** найдите строку для изменения или удаления.</span><span class="sxs-lookup"><span data-stu-id="dea8d-122">In the **Results** pane, locate the row to be changed or deleted.</span></span> <span data-ttu-id="dea8d-123">Чтобы удалить строку, щелкните правой кнопкой мыши строку и выберите **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="dea8d-123">To delete the row, right-click the row and select **Delete**.</span></span> <span data-ttu-id="dea8d-124">Чтобы изменить данные в одном или нескольких столбцах, измените данные в столбце.</span><span class="sxs-lookup"><span data-stu-id="dea8d-124">To change data in one or more columns, modify the data in the column.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="dea8d-125">Нельзя удалить строку, если представление ссылается на несколько базовых таблиц.</span><span class="sxs-lookup"><span data-stu-id="dea8d-125">You cannot delete a row if the view references more than one base table.</span></span> <span data-ttu-id="dea8d-126">Можно обновлять только те столбцы, которые принадлежат к одной базовой таблице.</span><span class="sxs-lookup"><span data-stu-id="dea8d-126">You can only update columns that belong to a single base table.</span></span>  
  
5.  <span data-ttu-id="dea8d-127">Чтобы вставить строку, прокрутите строки вниз до конца и вставьте новые значения.</span><span class="sxs-lookup"><span data-stu-id="dea8d-127">To insert a row, scroll down to the end of the rows and insert the new values.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="dea8d-128">Нельзя вставить строку, если представление ссылается на несколько базовых таблиц.</span><span class="sxs-lookup"><span data-stu-id="dea8d-128">You cannot insert a row if the view references more than one base table.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="dea8d-129">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="dea8d-129">Using Transact-SQL</span></span>  
  
#### <a name="to-update-table-data-through-a-view"></a><span data-ttu-id="dea8d-130">Обновление данных таблицы с помощью представления</span><span class="sxs-lookup"><span data-stu-id="dea8d-130">To update table data through a view</span></span>  
  
1.  <span data-ttu-id="dea8d-131">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dea8d-131">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="dea8d-132">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="dea8d-132">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="dea8d-133">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="dea8d-133">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="dea8d-134">В этом примере изменяется значение в столбцах `StartDate` и `EndDate` для определенного сотрудника путем создания ссылки на столбцы в представлении `HumanResources.vEmployeeDepartmentHistory`.</span><span class="sxs-lookup"><span data-stu-id="dea8d-134">This example changes the value in the `StartDate` and `EndDate` columns for a specific employee by referencing columns in the view `HumanResources.vEmployeeDepartmentHistory`.</span></span> <span data-ttu-id="dea8d-135">Это представление возвращает значения из двух таблиц.</span><span class="sxs-lookup"><span data-stu-id="dea8d-135">This view returns values from two tables.</span></span> <span data-ttu-id="dea8d-136">Эта инструкция была выполнена успешно, потому что изменялись столбцы только одной из базовых таблиц.</span><span class="sxs-lookup"><span data-stu-id="dea8d-136">This statement succeeds because the columns being modified are from only one of the base tables.</span></span>  
  
    ```  
    USE AdventureWorks2012 ;   
    GO  
    UPDATE HumanResources.vEmployeeDepartmentHistory  
    SET StartDate = '20110203', EndDate = GETDATE()   
    WHERE LastName = N'Smith' AND FirstName = 'Samantha';   
    GO  
    ```  
  
 <span data-ttu-id="dea8d-137">Дополнительные сведения см. в статье [UPDATE (Transact-SQL)](/sql/t-sql/queries/update-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="dea8d-137">For more information, see [UPDATE &#40;Transact-SQL&#41;](/sql/t-sql/queries/update-transact-sql).</span></span>  
  
#### <a name="to-insert-table-data-through-a-view"></a><span data-ttu-id="dea8d-138">Вставка данных таблицы с помощью представления</span><span class="sxs-lookup"><span data-stu-id="dea8d-138">To insert table data through a view</span></span>  
  
1.  <span data-ttu-id="dea8d-139">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dea8d-139">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="dea8d-140">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="dea8d-140">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="dea8d-141">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="dea8d-141">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="dea8d-142">В этом примере выполняется вставка новой строки в базовую таблицу `HumanResouces.Department` путем указания соответствующих столбцов в представлении `HumanResources.vEmployeeDepartmentHistory`.</span><span class="sxs-lookup"><span data-stu-id="dea8d-142">The example inserts a new row into the base table `HumanResouces.Department` by specifying the relevant columns from the view `HumanResources.vEmployeeDepartmentHistory`.</span></span> <span data-ttu-id="dea8d-143">Эта инструкция была выполнена успешно, поскольку были указаны только столбцы из одной базовой таблицы, а другие столбцы в базовой таблице имеют значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="dea8d-143">The statement succeeds because only columns from a single base table are specified and the other columns in the base table have default values.</span></span>  
  
    ```  
    USE AdventureWorks2012 ;  
    GO  
    INSERT INTO HumanResources.vEmployeeDepartmentHistory (Department, GroupName)   
    VALUES ('MyDepartment', 'MyGroup');   
    GO  
    ```  
  
 <span data-ttu-id="dea8d-144">Дополнительные сведения см. в статье [INSERT (Transact-SQL)](/sql/t-sql/statements/insert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="dea8d-144">For more information, see [INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/insert-transact-sql).</span></span>  
  
  
