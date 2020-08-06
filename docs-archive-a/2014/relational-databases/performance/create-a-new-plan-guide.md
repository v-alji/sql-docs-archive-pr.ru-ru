---
title: Создание структуры плана | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
f1_keywords:
- sql12.swb.designer.newplanguide.f1
helpviewer_keywords:
- creating plan guides
- plan guides [SQL Server]. creating
ms.assetid: e1ad78bb-4857-40ea-a0c6-dcf5c28aef2f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 60ba31e2a63575a316db5befb397bea59c0ad1e6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668834"
---
# <a name="create-a-new-plan-guide"></a><span data-ttu-id="6adf7-102">Создание структуры плана</span><span class="sxs-lookup"><span data-stu-id="6adf7-102">Create a New Plan Guide</span></span>
  <span data-ttu-id="6adf7-103">Структуру плана в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] можно создать с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6adf7-103">You can create a plan guide in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="6adf7-104">Структура плана влияет на оптимизацию запросов путем присоединения указаний запросов или фиксированного плана запросов к ним.</span><span class="sxs-lookup"><span data-stu-id="6adf7-104">Plan guides influence query optimization by attaching query hints or a fixed query plan to them.</span></span> <span data-ttu-id="6adf7-105">В структуре плана указывается оператор [!INCLUDE[tsql](../../includes/tsql-md.md)] , который нужно оптимизировать, и либо предложение OPTION, которое содержит указания запросов, которые будут использоваться, либо специальный план запроса, который используется для оптимизации запроса.</span><span class="sxs-lookup"><span data-stu-id="6adf7-105">In the plan guide, you specify the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement that you want optimized and either an OPTION clause that contains the query hints you want to use or a specific query plan you want to use to optimize the query.</span></span> <span data-ttu-id="6adf7-106">Когда запрос выполняется, оптимизатор запросов сопоставляет инструкцию [!INCLUDE[tsql](../../includes/tsql-md.md)] со структурой плана и либо присоединяет условие OPTION к запросу в процессе выполнения, либо использует указанный план запроса.</span><span class="sxs-lookup"><span data-stu-id="6adf7-106">When the query executes, the query optimizer matches the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement to the plan guide and either attaches the OPTION clause to the query at run time or uses the specified query plan.</span></span>  
  
 <span data-ttu-id="6adf7-107">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="6adf7-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="6adf7-108">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="6adf7-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="6adf7-109">Ограничения</span><span class="sxs-lookup"><span data-stu-id="6adf7-109">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="6adf7-110">Безопасность</span><span class="sxs-lookup"><span data-stu-id="6adf7-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="6adf7-111">**Создание структуры плана**</span><span class="sxs-lookup"><span data-stu-id="6adf7-111">**To create a plan guide, using:**</span></span>  
  
     [<span data-ttu-id="6adf7-112">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6adf7-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="6adf7-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="6adf7-113">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="6adf7-114">Перед началом</span><span class="sxs-lookup"><span data-stu-id="6adf7-114">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="6adf7-115">Ограничения</span><span class="sxs-lookup"><span data-stu-id="6adf7-115">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="6adf7-116">Аргументы процедуры sp_create_plan_guide должны задаваться в указанном порядке.</span><span class="sxs-lookup"><span data-stu-id="6adf7-116">The arguments to sp_create_plan_guide must be provided in the order that is shown.</span></span> <span data-ttu-id="6adf7-117">При задании значений параметрам процедуры `sp_create_plan_guide` все имена параметров необходимо указывать явно или вообще не указывать.</span><span class="sxs-lookup"><span data-stu-id="6adf7-117">When you supply values for the parameters of `sp_create_plan_guide`, all parameter names must be specified explicitly, or none at all.</span></span> <span data-ttu-id="6adf7-118">Например, если указан параметр `@name =`, необходимо также указать параметры `@stmt =`, `@type =` и т. д.</span><span class="sxs-lookup"><span data-stu-id="6adf7-118">For example, if `@name =` is specified, then `@stmt =` , `@type =`, and so on, must also be specified.</span></span> <span data-ttu-id="6adf7-119">Подобным образом, если параметр `@name =` пропущен и указано только его значение, имена остальных параметров должны быть также пропущены и должны быть указаны только их значения.</span><span class="sxs-lookup"><span data-stu-id="6adf7-119">Likewise, if `@name =` is omitted and only the parameter value is provided, the remaining parameter names must also be omitted, and only their values provided.</span></span> <span data-ttu-id="6adf7-120">Имена аргументов приводятся исключительно в целях описания, чтобы помочь разобраться с синтаксисом.</span><span class="sxs-lookup"><span data-stu-id="6adf7-120">Argument names are for descriptive purposes only, to help understand the syntax.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="6adf7-121">не проверяет соответствие указанных имен параметров их позициям.</span><span class="sxs-lookup"><span data-stu-id="6adf7-121">does not verify that the specified parameter name matches the name for the parameter in the position where the name is used.</span></span>  
  
-   <span data-ttu-id="6adf7-122">Можно создать несколько структур планов OBJECT или SQL для одного и того же запроса и пакета либо модуля.</span><span class="sxs-lookup"><span data-stu-id="6adf7-122">You can create more than one OBJECT or SQL plan guide for the same query and batch or module.</span></span> <span data-ttu-id="6adf7-123">Однако только одна структура плана может быть включена в данный момент времени.</span><span class="sxs-lookup"><span data-stu-id="6adf7-123">However, only one plan guide can be enabled at any given time.</span></span>  
  
-   <span data-ttu-id="6adf7-124">Нельзя создавать структуры планов типа OBJECT для значения @module_or_batch, ссылающегося на хранимую процедуру, функцию или триггер DML, который задает предложение WITH ENCRYPTION или является временным.</span><span class="sxs-lookup"><span data-stu-id="6adf7-124">Plan guides of type OBJECT cannot be created for an @module_or_batch value that references a stored procedure, function, or DML trigger that specifies the WITH ENCRYPTION clause or that is temporary.</span></span>  
  
-   <span data-ttu-id="6adf7-125">Попытка удаления или изменения функции, хранимой процедуры или триггера DML, на которые имеется ссылка в структуре плана (как включенных, так и отключенных), приводит к ошибке.</span><span class="sxs-lookup"><span data-stu-id="6adf7-125">Trying to drop or modify a function, stored procedure, or DML trigger that is referenced by a plan guide, either enabled or disabled, causes an error.</span></span> <span data-ttu-id="6adf7-126">Попытка удалить таблицу, для которой определен триггер, имеющий соответствующую ссылку в структуре плана, также вызывает ошибку.</span><span class="sxs-lookup"><span data-stu-id="6adf7-126">Trying to drop a table that has a trigger defined on it that is referenced by a plan guide also causes an error.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="6adf7-127">безопасность</span><span class="sxs-lookup"><span data-stu-id="6adf7-127">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="6adf7-128">Permissions</span><span class="sxs-lookup"><span data-stu-id="6adf7-128">Permissions</span></span>  
 <span data-ttu-id="6adf7-129">Для создания структуры плана типа OBJECT необходимо разрешение ALTER на соответствующий объект.</span><span class="sxs-lookup"><span data-stu-id="6adf7-129">To create a plan guide of type OBJECT, requires ALTER permission on the referenced object.</span></span> <span data-ttu-id="6adf7-130">Чтобы создать структуру плана типа SQL или TEMPLATE, необходимо обладать разрешением ALTER на текущую базу данных.</span><span class="sxs-lookup"><span data-stu-id="6adf7-130">To create a plan guide of type SQL or TEMPLATE, requires ALTER permission on the current database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="6adf7-131">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6adf7-131">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-plan-guide"></a><span data-ttu-id="6adf7-132">Создание структуры плана</span><span class="sxs-lookup"><span data-stu-id="6adf7-132">To create a plan guide</span></span>  
  
1.  <span data-ttu-id="6adf7-133">Щелкните значок «+», чтобы развернуть базу данных, в которой требуется создать структуру плана, затем щелкните значок «+», чтобы развернуть папку **Программирование** .</span><span class="sxs-lookup"><span data-stu-id="6adf7-133">Click the plus sign to expand the database in which you want to create a plan guide, and then click the plus sign to expand the **Programmability** folder.</span></span>  
  
2.  <span data-ttu-id="6adf7-134">Щелкните правой кнопкой мыши папку **структуры планов** и выберите пункт **создать структуру плана...**.</span><span class="sxs-lookup"><span data-stu-id="6adf7-134">Right-click the **Plan Guides** folder and select **New Plan Guide...**.</span></span>  
  
3.  <span data-ttu-id="6adf7-135">В поле **Имя** диалогового окна **Создание структуры плана** введите имя новой структуры плана.</span><span class="sxs-lookup"><span data-stu-id="6adf7-135">In the **New Plan Guide** dialog box, in the **Name** box, enter the name of the plan guide.</span></span>  
  
4.  <span data-ttu-id="6adf7-136">В поле **Инструкция** введите инструкцию [!INCLUDE[tsql](../../includes/tsql-md.md)] , к которой должна быть применена структура плана.</span><span class="sxs-lookup"><span data-stu-id="6adf7-136">In the **Statement** box, enter the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement against which the plan guide is to be applied.</span></span>  
  
5.  <span data-ttu-id="6adf7-137">В списке **Тип области** выберите сущность, в которой содержится инструкция [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6adf7-137">In the **Scope type** list, select the type of entity in which the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement appears.</span></span> <span data-ttu-id="6adf7-138">Это указывает контекст для сопоставления оператора [!INCLUDE[tsql](../../includes/tsql-md.md)] со структурой плана.</span><span class="sxs-lookup"><span data-stu-id="6adf7-138">This specifies the context for matching the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement to the plan guide.</span></span> <span data-ttu-id="6adf7-139">Возможными значениями являются **OBJECT**, **SQL**и **TEMPLATE**.</span><span class="sxs-lookup"><span data-stu-id="6adf7-139">Possible values are **OBJECT**, **SQL**, and **TEMPLATE**.</span></span>  
  
6.  <span data-ttu-id="6adf7-140">В поле **Поток области** введите текст пакета, в котором содержится инструкция [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6adf7-140">In the **Scope batch** box, enter the batch text in which the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement appears.</span></span> <span data-ttu-id="6adf7-141">Текст пакета не может содержать инструкцию USE\`\`*database* .</span><span class="sxs-lookup"><span data-stu-id="6adf7-141">The batch text cannot include a USE\`\`*database* statement.</span></span> <span data-ttu-id="6adf7-142">Поле **Поток области** доступно, только если в качестве второго типа выбран тип **SQL** .</span><span class="sxs-lookup"><span data-stu-id="6adf7-142">The **Scope batch** box is only available when **SQL** is selected as a scope type.</span></span> <span data-ttu-id="6adf7-143">Если типом области является SQL, а поле пакета области пустое, в качестве текста пакета используется значение, указанное в поле **Инструкция** .</span><span class="sxs-lookup"><span data-stu-id="6adf7-143">If nothing is entered in the scope batch box when SQL is the scope type, then the value of the batch text is set to the same value as is in the **Statement** box.</span></span>  
  
7.  <span data-ttu-id="6adf7-144">В списке **Имя схемы области** введите имя схемы, в которой содержится объект.</span><span class="sxs-lookup"><span data-stu-id="6adf7-144">In the **Scope schema name** list, enter the name of the schema in which the object is contained.</span></span> <span data-ttu-id="6adf7-145">Поле **Имя схемы области** доступно, только если в качестве второго типа выбран тип области **Объект** .</span><span class="sxs-lookup"><span data-stu-id="6adf7-145">The **Scope schema name** box is only available when **Object** is selected as a scope type.</span></span>  
  
8.  <span data-ttu-id="6adf7-146">В поле **Имя области объекта** введите имя хранимой процедуры [!INCLUDE[tsql](../../includes/tsql-md.md)] , определяемой пользователем скалярной функции, функции с табличным значением из нескольких инструкций или триггера DML, в котором содержится инструкция [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6adf7-146">In the **Scope object name** box, enter the name of the [!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedure, user-defined scalar function, multistatement table-valued function, or DML trigger in which the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement appears.</span></span> <span data-ttu-id="6adf7-147">Поле **Имя объекта области** доступно, только если выбран тип области **Объект** .</span><span class="sxs-lookup"><span data-stu-id="6adf7-147">The **Scope object name** box is only available when **Object** is selected as a scope type.</span></span>  
  
9. <span data-ttu-id="6adf7-148">В поле **Параметры** введите имя параметра и тип данных для всех параметров, внедренных в инструкции [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6adf7-148">In the **Parameters** box, enter the parameter name and data type of all parameters that are embedded in the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement.</span></span>  
  
     <span data-ttu-id="6adf7-149">Параметры применяются только при выполнении одного из следующих условий.</span><span class="sxs-lookup"><span data-stu-id="6adf7-149">Parameters apply only when either of the following is true:</span></span>  
  
    -   <span data-ttu-id="6adf7-150">Тип области равен **SQL** или **TEMPLATE**.</span><span class="sxs-lookup"><span data-stu-id="6adf7-150">The scope type is **SQL** or **TEMPLATE**.</span></span> <span data-ttu-id="6adf7-151">Если тип области равен **TEMPLATE**, то параметры не могут иметь значение NULL.</span><span class="sxs-lookup"><span data-stu-id="6adf7-151">If **TEMPLATE**, parameters must not be NULL.</span></span>  
  
    -   <span data-ttu-id="6adf7-152">Инструкция [!INCLUDE[tsql](../../includes/tsql-md.md)] передается при помощи хранимой процедуры sp_executesql с указанием значения параметра, или компонент [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] выполняет внутреннюю отправку инструкции после ее параметризации.</span><span class="sxs-lookup"><span data-stu-id="6adf7-152">The [!INCLUDE[tsql](../../includes/tsql-md.md)] statement is submitted by using sp_executesql and a value for the parameter is specified, or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] internally submits a statement after parameterizing it.</span></span>  
  
10. <span data-ttu-id="6adf7-153">В поле **Подсказки** введите указания запросов или план запроса, применяемые к инструкции [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6adf7-153">In the **Hints** box, enter the query hints or query plan to be applied to the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement.</span></span> <span data-ttu-id="6adf7-154">Чтобы задать одно или несколько указаний запроса, введите предложение OPTION.</span><span class="sxs-lookup"><span data-stu-id="6adf7-154">To specify one or more query hints, enter a valid OPTION clause.</span></span>  
  
11. <span data-ttu-id="6adf7-155">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="6adf7-155">Click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="6adf7-156">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="6adf7-156">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-plan-guide"></a><span data-ttu-id="6adf7-157">Создание структуры плана</span><span class="sxs-lookup"><span data-stu-id="6adf7-157">To create a plan guide</span></span>  
  
1.  <span data-ttu-id="6adf7-158">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6adf7-158">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="6adf7-159">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="6adf7-159">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="6adf7-160">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="6adf7-160">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
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
  
    ```  
  
 <span data-ttu-id="6adf7-161">Дополнительные сведения см. в разделе [sp_create_plan_guide (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="6adf7-161">For more information, see [sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql).</span></span>  
  
  
