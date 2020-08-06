---
title: Просмотр свойств структуры плана | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
f1_keywords:
- sql12.swb.planguideprop.general.f1
helpviewer_keywords:
- plan guides [SQL Server], view plan guide properties
- viewing plan guide properties
ms.assetid: 8c0d2f39-59c1-4168-a649-65473f6a771b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: af29c66690a43f89106c1f77aca8c3a02eff2ba9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731550"
---
# <a name="view-plan-guide-properties"></a><span data-ttu-id="a61e0-102">Просмотр свойств структуры плана</span><span class="sxs-lookup"><span data-stu-id="a61e0-102">View Plan Guide Properties</span></span>
  <span data-ttu-id="a61e0-103">Свойства структур планов в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] можно просмотреть при помощи среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a61e0-103">You can view the properties of plan guides in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)]</span></span>  
  
 <span data-ttu-id="a61e0-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="a61e0-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="a61e0-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="a61e0-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="a61e0-106">Безопасность</span><span class="sxs-lookup"><span data-stu-id="a61e0-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="a61e0-107">**Просмотр свойств структур планов при помощи различных средств**</span><span class="sxs-lookup"><span data-stu-id="a61e0-107">**To view the properties of plan guides, using:**</span></span>  
  
     [<span data-ttu-id="a61e0-108">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a61e0-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="a61e0-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a61e0-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="a61e0-110">Перед началом</span><span class="sxs-lookup"><span data-stu-id="a61e0-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="a61e0-111">безопасность</span><span class="sxs-lookup"><span data-stu-id="a61e0-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="a61e0-112">Permissions</span><span class="sxs-lookup"><span data-stu-id="a61e0-112">Permissions</span></span>  
 <span data-ttu-id="a61e0-113">Видимость метаданных в представлениях каталогов ограничивается защищаемыми объектами, которыми пользователь владеет или на которые ему были предоставлены разрешения.</span><span class="sxs-lookup"><span data-stu-id="a61e0-113">The visibility of the metadata in catalog views is limited to securables that either a user owns or on which the user has been granted some permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="a61e0-114">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a61e0-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-the-properties-of-a-plan-guide"></a><span data-ttu-id="a61e0-115">Просмотр свойств структуры плана</span><span class="sxs-lookup"><span data-stu-id="a61e0-115">To view the properties of a plan guide</span></span>  
  
1.  <span data-ttu-id="a61e0-116">Щелкните значок «+», чтобы развернуть базу данных, в которой требуется просмотреть свойства структуры планов, после чего щелкните значок «+», чтобы развернуть папку **Программирование** .</span><span class="sxs-lookup"><span data-stu-id="a61e0-116">Click the plus sign to expand the database in which you want to view the properties of a plan guide, and then click the plus sign to expand the **Programmability** folder.</span></span>  
  
2.  <span data-ttu-id="a61e0-117">Щелкните значок «+», чтобы развернуть папку **Структуры планов** .</span><span class="sxs-lookup"><span data-stu-id="a61e0-117">Click the plus sign to expand the **Plan Guides** folder.</span></span>  
  
3.  <span data-ttu-id="a61e0-118">Щелкните правой кнопкой мыши структуру плана, свойства которого необходимо просмотреть, и выберите команду **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="a61e0-118">Right-click the plan guide of which you want to view the properties and select **Properties**.</span></span>  
  
     <span data-ttu-id="a61e0-119">Следующие свойства отображаются в диалоговом окне **Свойства структуры плана** .</span><span class="sxs-lookup"><span data-stu-id="a61e0-119">The following properties show in the **Plan Guide Properties** dialog box.</span></span>  
  
     <span data-ttu-id="a61e0-120">**Указания**</span><span class="sxs-lookup"><span data-stu-id="a61e0-120">**Hints**</span></span>  
     <span data-ttu-id="a61e0-121">Отображает указания запросов или план запроса для применения к инструкции [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a61e0-121">Displays the query hints or query plan to be applied to the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement.</span></span> <span data-ttu-id="a61e0-122">Если план запроса задан как указание, отображаются выходные данные инструкции XML Showplan для этого плана.</span><span class="sxs-lookup"><span data-stu-id="a61e0-122">When a query plan is specified as a hint, the XML Showplan output for the plan is displayed.</span></span>  
  
     <span data-ttu-id="a61e0-123">**Отключен**</span><span class="sxs-lookup"><span data-stu-id="a61e0-123">**Is disabled**</span></span>  
     <span data-ttu-id="a61e0-124">Отображает состояние структуры плана.</span><span class="sxs-lookup"><span data-stu-id="a61e0-124">Displays the status of the plan guide.</span></span> <span data-ttu-id="a61e0-125">Допустимые значения — **True** и **False**.</span><span class="sxs-lookup"><span data-stu-id="a61e0-125">Possible values are **True** and **False**.</span></span>  
  
     <span data-ttu-id="a61e0-126">**имя**;</span><span class="sxs-lookup"><span data-stu-id="a61e0-126">**Name**</span></span>  
     <span data-ttu-id="a61e0-127">Отображает имя структуры плана.</span><span class="sxs-lookup"><span data-stu-id="a61e0-127">Displays the name of the plan guide.</span></span>  
  
     <span data-ttu-id="a61e0-128">**Параметры**</span><span class="sxs-lookup"><span data-stu-id="a61e0-128">**Parameters**</span></span>  
     <span data-ttu-id="a61e0-129">Если тип области равен «SQL» или «TEMPLATE», отображает имя и тип данных для всех параметров, внедренных в инструкции [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a61e0-129">When the scope type is SQL or TEMPLATE, displays the name and data type of all parameters that are embedded in the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement.</span></span>  
  
     <span data-ttu-id="a61e0-130">**Поток области**</span><span class="sxs-lookup"><span data-stu-id="a61e0-130">**Scope batch**</span></span>  
     <span data-ttu-id="a61e0-131">Отображает текст пакета, в котором находится инструкция [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a61e0-131">Displays the batch text in which the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement appears.</span></span>  
  
     <span data-ttu-id="a61e0-132">**Имя объекта области**</span><span class="sxs-lookup"><span data-stu-id="a61e0-132">**Scope object name**</span></span>  
     <span data-ttu-id="a61e0-133">Если тип области равен «OBJECT», отображает имя хранимой процедуры [!INCLUDE[tsql](../../includes/tsql-md.md)] , определяемой пользователем скалярной функции, многооператорной возвращающей табличное значение функции или триггера DML, где содержится инструкция [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a61e0-133">When the scope type is OBJECT, displays the name of the [!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedure, user-defined scalar function, multistatement table-valued function, or DML trigger in which the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement appears.</span></span>  
  
     <span data-ttu-id="a61e0-134">**Имя схемы области**</span><span class="sxs-lookup"><span data-stu-id="a61e0-134">**Scope schema name**</span></span>  
     <span data-ttu-id="a61e0-135">Если тип области равен «OBJECT», отображает имя схемы, содержащей объект.</span><span class="sxs-lookup"><span data-stu-id="a61e0-135">When the scope type is OBJECT, displays the name of the schema in which the object is contained.</span></span>  
  
     <span data-ttu-id="a61e0-136">**Тип области**</span><span class="sxs-lookup"><span data-stu-id="a61e0-136">**Scope type**</span></span>  
     <span data-ttu-id="a61e0-137">Отображает тип сущности, в которой присутствует инструкция [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a61e0-137">Displays the type of entity in which the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement appears.</span></span> <span data-ttu-id="a61e0-138">Это указывает контекст для сопоставления оператора [!INCLUDE[tsql](../../includes/tsql-md.md)] со структурой плана.</span><span class="sxs-lookup"><span data-stu-id="a61e0-138">This specifies the context for matching the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement to the plan guide.</span></span> <span data-ttu-id="a61e0-139">Возможными значениями являются **OBJECT**, **SQL**и **TEMPLATE**.</span><span class="sxs-lookup"><span data-stu-id="a61e0-139">Possible values are **OBJECT**, **SQL**, and **TEMPLATE**.</span></span>  
  
     <span data-ttu-id="a61e0-140">**Инструкция**</span><span class="sxs-lookup"><span data-stu-id="a61e0-140">**Statement**</span></span>  
     <span data-ttu-id="a61e0-141">Отображает инструкцию [!INCLUDE[tsql](../../includes/tsql-md.md)] , для которой необходимо применить структуру плана.</span><span class="sxs-lookup"><span data-stu-id="a61e0-141">Displays the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement against which the plan guide is applied.</span></span>  
  
4.  <span data-ttu-id="a61e0-142">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="a61e0-142">Click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="a61e0-143">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a61e0-143">Using Transact-SQL</span></span>  
  
#### <a name="to-view-the-properties-of-a-plan-guide"></a><span data-ttu-id="a61e0-144">Просмотр свойств структуры плана</span><span class="sxs-lookup"><span data-stu-id="a61e0-144">To view the properties of a plan guide</span></span>  
  
1.  <span data-ttu-id="a61e0-145">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a61e0-145">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="a61e0-146">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="a61e0-146">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="a61e0-147">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="a61e0-147">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- If a plan guide named "Guide1" already exists in the AdventureWorks2012 database, delete it.  
    USE AdventureWorks2012;  
    GO  
    IF OBJECT_ID(N'Guide1') IS NOT NULL  
       EXEC sp_control_plan_guide N'DROP', N'Guide1';  
    GO  
    -- creates a plan guide named Guide1 based on a SQL statement  
    EXEC sp_create_plan_guide   
        @name = N'Guide1',   
        @stmt = N'SELECT TOP 1 *   
                  FROM Sales.SalesOrderHeader   
                  ORDER BY OrderDate DESC',   
        @type = N'SQL',  
        @module_or_batch = NULL,   
        @params = NULL,   
        @hints = N'OPTION (MAXDOP 1)';  
    GO  
    -- Gets the name, created date, and all other relevant property information on the plan guide created above.   
    SELECT name AS plan_guide_name,  
       create_date,  
       query_text,  
       scope_type_desc,  
       OBJECT_NAME(scope_object_id) AS scope_object_name,  
       scope_batch,  
       parameters,  
       hints,  
       is_disabled  
    FROM sys.plan_guides  
    WHERE name = N'Guide1';  
    GO  
    ```  
  
 <span data-ttu-id="a61e0-148">Дополнительные сведения см. в разделе [sys.plan_guides (Transact-SQL)](/sql/relational-databases/system-catalog-views/sys-plan-guides-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="a61e0-148">For more information, see [sys.plan_guides &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-plan-guides-transact-sql).</span></span>  
  
  
