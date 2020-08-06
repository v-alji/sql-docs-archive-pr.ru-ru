---
title: Создание проверочного ограничения | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- table constraints [SQL Server]
- attaching check constraints
- columns [SQL Server], constraints
- constraints [SQL Server], check
- CHECK constraints, attaching
ms.assetid: b8756304-9454-4d39-996a-64516831b7df
author: stevestein
ms.author: sstein
ms.openlocfilehash: 7795ee6eca85a22bdd4e84c90ce49a9449ddff28
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669360"
---
# <a name="create-check-constraints"></a><span data-ttu-id="ce6bb-102">Создание ограничений CHECK</span><span class="sxs-lookup"><span data-stu-id="ce6bb-102">Create Check Constraints</span></span>
  <span data-ttu-id="ce6bb-103">В [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] можно создать в таблице проверочное ограничение, чтобы указать значения данных, допустимые в одном или нескольких столбцах, с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или в [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ce6bb-103">You can create a check constraint in a table to specify the data values that are acceptable in one or more columns in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="ce6bb-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="ce6bb-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="ce6bb-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="ce6bb-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="ce6bb-106">Безопасность</span><span class="sxs-lookup"><span data-stu-id="ce6bb-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="ce6bb-107">**Создание нового проверочного ограничения с помощью следующих средств:**</span><span class="sxs-lookup"><span data-stu-id="ce6bb-107">**To create a new check constraint using:**</span></span>  
  
     [<span data-ttu-id="ce6bb-108">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ce6bb-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="ce6bb-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ce6bb-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="ce6bb-110">Перед началом</span><span class="sxs-lookup"><span data-stu-id="ce6bb-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="ce6bb-111">безопасность</span><span class="sxs-lookup"><span data-stu-id="ce6bb-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="ce6bb-112">Permissions</span><span class="sxs-lookup"><span data-stu-id="ce6bb-112">Permissions</span></span>  
 <span data-ttu-id="ce6bb-113">Требуется разрешение ALTER на таблицу.</span><span class="sxs-lookup"><span data-stu-id="ce6bb-113">Requires ALTER permissions on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="ce6bb-114">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ce6bb-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-new-check-constraint"></a><span data-ttu-id="ce6bb-115">Создание нового проверочного ограничения</span><span class="sxs-lookup"><span data-stu-id="ce6bb-115">To create a new check constraint</span></span>  
  
1.  <span data-ttu-id="ce6bb-116">В **обозревателе объектов**разверните таблицу, в которую необходимо добавить проверочное ограничение, щелкните правой кнопкой пункт **Ограничения** и выберите команду **Создать ограничение**.</span><span class="sxs-lookup"><span data-stu-id="ce6bb-116">In **Object Explorer**, expand the table to which you want to add a check constraint, right-click **Constraints** and click **New Constraint**.</span></span>  
  
2.  <span data-ttu-id="ce6bb-117">В диалоговом окне **Проверочные ограничения** установите курсор в поле **Выражение** и затем нажмите кнопку с многоточием **(…)** .</span><span class="sxs-lookup"><span data-stu-id="ce6bb-117">In the **Check Constraints** dialog box, click in the **Expression** field and then click the ellipses **(...)**.</span></span>  
  
3.  <span data-ttu-id="ce6bb-118">В диалоговом окне **Выражение проверочного ограничения** введите выражения SQL, соответствующие проверочному ограничению.</span><span class="sxs-lookup"><span data-stu-id="ce6bb-118">In the **Check Constraint Expression** dialog box, type the SQL expressions for the check constraint.</span></span> <span data-ttu-id="ce6bb-119">Например, чтобы ограничить записи в столбце `SellEndDate` таблицы `Product` значениями, которые больше или равны дате в столбце `SellStartDate` или равны NULL, введите следующее:</span><span class="sxs-lookup"><span data-stu-id="ce6bb-119">For example, to limit the entries in the `SellEndDate` column of the `Product` table to a value that is either greater than or equal to the date in the `SellStartDate` column or is a NULL value, type:</span></span>  
  
    ```  
    SellEndDate >= SellStartDate OR SellEndDate IS NULL  
    ```  
  
     <span data-ttu-id="ce6bb-120">Чтобы ограничить записи в столбце `zip` записями, состоящими из 5 цифр, введите:</span><span class="sxs-lookup"><span data-stu-id="ce6bb-120">Or, to require entries in the `zip` column to be 5 digits, type:</span></span>  
  
    ```  
    zip LIKE '[0-9][0-9][0-9][0-9][0-9]'  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="ce6bb-121">Убедитесь, что все нечисловые ограничения по значению заключены в одиночные кавычки (').</span><span class="sxs-lookup"><span data-stu-id="ce6bb-121">Make sure to enclose any non-numeric constraint values in single quotation marks (').</span></span>  
  
4.  <span data-ttu-id="ce6bb-122">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="ce6bb-122">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="ce6bb-123">В категории **Идентификация** можно изменить имя проверочного ограничения и добавить описание (расширенное свойство) ограничения.</span><span class="sxs-lookup"><span data-stu-id="ce6bb-123">In the **Identity** category, you can change the name of the check constraint and add a description (extended property) for the constraint.</span></span>  
  
6.  <span data-ttu-id="ce6bb-124">В категории **Конструктор таблиц** можно задать время принудительного выполнения проверочного ограничения.</span><span class="sxs-lookup"><span data-stu-id="ce6bb-124">In the **Table Designer** category, you can set when the constraint is enforced.</span></span>  
  
    |<span data-ttu-id="ce6bb-125">**Кому.**</span><span class="sxs-lookup"><span data-stu-id="ce6bb-125">**To:**</span></span>|<span data-ttu-id="ce6bb-126">**Выберите «Да» в следующих полях:**</span><span class="sxs-lookup"><span data-stu-id="ce6bb-126">**Select Yes in the Following Fields:**</span></span>|  
    |-------------|---------------------------------------------|  
    |<span data-ttu-id="ce6bb-127">Проверить ограничение для данных, которые существовали до создания ограничения</span><span class="sxs-lookup"><span data-stu-id="ce6bb-127">Test the constraint on data that existed before you created the constraint</span></span>|<span data-ttu-id="ce6bb-128">**Проверить существующие данные при создании или включении**</span><span class="sxs-lookup"><span data-stu-id="ce6bb-128">**Check Existing Data On Creation Or Enabling**</span></span>|  
    |<span data-ttu-id="ce6bb-129">Принудительно применять ограничение при каждой операции репликации данной таблицы</span><span class="sxs-lookup"><span data-stu-id="ce6bb-129">Enforce the constraint whenever a replication operation occurs on this table</span></span>|<span data-ttu-id="ce6bb-130">**Принудительное применение для репликации**</span><span class="sxs-lookup"><span data-stu-id="ce6bb-130">**Enforce For Replication**</span></span>|  
    |<span data-ttu-id="ce6bb-131">Принудительно применять это ограничение при каждой вставке или обновлении строки таблицы</span><span class="sxs-lookup"><span data-stu-id="ce6bb-131">Enforce the constraint whenever a row of this table is inserted or updated</span></span>|<span data-ttu-id="ce6bb-132">**Применять для INSERT и UPDATE**</span><span class="sxs-lookup"><span data-stu-id="ce6bb-132">**Enforce For INSERTs And UPDATEs**</span></span>|  
  
7.  <span data-ttu-id="ce6bb-133">Щелкните **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="ce6bb-133">Click **Close**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="ce6bb-134">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ce6bb-134">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-new-check-constraint"></a><span data-ttu-id="ce6bb-135">Создание нового проверочного ограничения</span><span class="sxs-lookup"><span data-stu-id="ce6bb-135">To create a new check constraint</span></span>  
  
1.  <span data-ttu-id="ce6bb-136">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ce6bb-136">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="ce6bb-137">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="ce6bb-137">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="ce6bb-138">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="ce6bb-138">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    ALTER TABLE dbo.DocExc   
       ADD ColumnD int NULL   
       CONSTRAINT CHK_ColumnD_DocExc   
       CHECK (ColumnD > 10 AND ColumnD < 50);  
    GO  
    -- Adding values that will pass the check constraint  
    INSERT INTO dbo.DocExc (ColumnD) VALUES (49);  
    GO  
    -- Adding values that will fail the check constraint  
    INSERT INTO dbo.DocExc (ColumnD) VALUES (55);  
    GO  
  
    ```  
  
 <span data-ttu-id="ce6bb-139">Дополнительные сведения см. в разделе [ALTER TABLE (Transact-SQL)](/sql/t-sql/statements/alter-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ce6bb-139">For more information, see [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span></span>  
  
###  <a name="TsqlExample"></a>  
