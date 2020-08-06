---
title: Включение или отключение структуры плана | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- plan guides [SQL Server], disabling
- enabling plan guides
- plan guides [SQL Server], enabling
- disabling plan guides
ms.assetid: b00ab550-5308-4cb8-8330-483cd1d25654
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 2611697e479d318245d8306b28c826e744ae85ad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87736275"
---
# <a name="enable-or-disable-a-plan-guide"></a><span data-ttu-id="473db-102">Включение или отключение структуры плана.</span><span class="sxs-lookup"><span data-stu-id="473db-102">Enable or Disable a Plan Guide</span></span>
  <span data-ttu-id="473db-103">В [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] отключать и включать руководства планов можно с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="473db-103">You can disable and enable plan guides in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="473db-104">Включить или отключить можно как одно руководство планов, так и все сразу.</span><span class="sxs-lookup"><span data-stu-id="473db-104">Either a single plan guides or all plan guides in a database can be enabled or disabled.</span></span>  
  
 <span data-ttu-id="473db-105">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="473db-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="473db-106">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="473db-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="473db-107">Ограничения</span><span class="sxs-lookup"><span data-stu-id="473db-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="473db-108">Безопасность</span><span class="sxs-lookup"><span data-stu-id="473db-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="473db-109">**Отключение и включение руководств планов с помощью различных средств.**</span><span class="sxs-lookup"><span data-stu-id="473db-109">**To disable and enable plan guides, using:**</span></span>  
  
     [<span data-ttu-id="473db-110">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="473db-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="473db-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="473db-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="473db-112">Перед началом</span><span class="sxs-lookup"><span data-stu-id="473db-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="473db-113">Ограничения</span><span class="sxs-lookup"><span data-stu-id="473db-113">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="473db-114">Попытка удаления или изменения функции, хранимой процедуры или триггера DML, на которые имеется ссылка в структуре плана (как включенных, так и отключенных), приводит к ошибке.</span><span class="sxs-lookup"><span data-stu-id="473db-114">Trying to drop or modify a function, stored procedure, or DML trigger that is referenced by a plan guide, either enabled or disabled, causes an error.</span></span> <span data-ttu-id="473db-115">Всегда проверяйте зависимости перед удалением или изменением любого из объектов, перечисленных выше.</span><span class="sxs-lookup"><span data-stu-id="473db-115">Always check for dependencies before dropping or modifying any of the objects listed above.</span></span>  
  
-   <span data-ttu-id="473db-116">Отключение уже отключенной структуры плана или включение включенной не имеет силы и не вызывает ошибки.</span><span class="sxs-lookup"><span data-stu-id="473db-116">Disabling a disabled plan guide or enabling an enabled plan guide has no effect and runs without error.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="473db-117">безопасность</span><span class="sxs-lookup"><span data-stu-id="473db-117">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="473db-118">Permissions</span><span class="sxs-lookup"><span data-stu-id="473db-118">Permissions</span></span>  
 <span data-ttu-id="473db-119">Для отключения или включения структуры плана OBJECT необходимо разрешение ALTER для того объекта (например функции, хранимой процедуры), на который ссылается структура плана.</span><span class="sxs-lookup"><span data-stu-id="473db-119">Disabling or enabling an OBJECT plan guide requires ALTER permission on the object (for example: function, stored procedure) that is referenced by the plan guide.</span></span> <span data-ttu-id="473db-120">Все остальные структуры планов требуют разрешения ALTER DATABASE.</span><span class="sxs-lookup"><span data-stu-id="473db-120">All other plan guides require ALTER DATABASE permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="473db-121">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="473db-121">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-disable-or-enable-a-plan-guide"></a><span data-ttu-id="473db-122">Включение или отключение структуры плана</span><span class="sxs-lookup"><span data-stu-id="473db-122">To disable or enable a plan guide</span></span>  
  
1.  <span data-ttu-id="473db-123">Щелкните значок «+», чтобы развернуть базу данных, в которой требуется включить или отключить структуру плана, затем щелкните значок «+», чтобы развернуть папку **Программирование** .</span><span class="sxs-lookup"><span data-stu-id="473db-123">Click the plus sign to expand the database in which you want to disable or enable a plan guide, and then click the plus sign to expand the **Programmability** folder.</span></span>  
  
2.  <span data-ttu-id="473db-124">Щелкните значок «+», чтобы развернуть папку **Структуры планов** .</span><span class="sxs-lookup"><span data-stu-id="473db-124">Click the plus sign to expand the **Plan Guides** folder.</span></span>  
  
3.  <span data-ttu-id="473db-125">Правой кнопкой мыши щелкните ту структуру плана, которую требуется включить или отключить, затем выберите команду **Отключить** или **Включить**.</span><span class="sxs-lookup"><span data-stu-id="473db-125">Right-click the plan guide you want to disable or enable and select either **Disable** or **Enable**.</span></span>  
  
4.  <span data-ttu-id="473db-126">В диалоговом окне **Отключение структуры плана** или **Включение структуры плана** убедитесь, что выбранное действие выполнено успешно, и нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="473db-126">In either the **Disable Plan Guide** or **Enable Plan Guide** dialog box, verify that the chosen action was successful and then click **Close**.</span></span>  
  
#### <a name="to-disable-or-enable-all-plan-guides-in-a-database"></a><span data-ttu-id="473db-127">Отключение или включение всех структур планов в базе данных</span><span class="sxs-lookup"><span data-stu-id="473db-127">To disable or enable all plan guides in a database</span></span>  
  
1.  <span data-ttu-id="473db-128">Щелкните значок «+», чтобы развернуть базу данных, в которой требуется включить или отключить структуру плана, затем щелкните значок «+», чтобы развернуть папку **Программирование** .</span><span class="sxs-lookup"><span data-stu-id="473db-128">Click the plus sign to expand the database in which you want to disable or enable a plan guide, and then click the plus sign to expand the **Programmability** folder.</span></span>  
  
2.  <span data-ttu-id="473db-129">Правой кнопкой мыши щелкните папку **Структуры планов** , после чего выберите команду **Включить все** или **Отключить все**.</span><span class="sxs-lookup"><span data-stu-id="473db-129">Right-click the **Plan Guides** folder and then select either **Enable All** or **Disable All**.</span></span>  
  
3.  <span data-ttu-id="473db-130">В диалоговом окне **Отключение всех структур планов** или **Включение всех структур планов** убедитесь, что выбранное действие выполнено успешно, и нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="473db-130">In either the **Disable all Plan Guides** or **Enable all Plan Guides** dialog box, verify that the chosen action was successful and then click **Close**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="473db-131">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="473db-131">Using Transact-SQL</span></span>  
  
#### <a name="to-disable-or-enable-a-plan-guide"></a><span data-ttu-id="473db-132">Включение или отключение структуры плана</span><span class="sxs-lookup"><span data-stu-id="473db-132">To disable or enable a plan guide</span></span>  
  
1.  <span data-ttu-id="473db-133">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="473db-133">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="473db-134">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="473db-134">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="473db-135">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="473db-135">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    --Create a procedure on which to define the plan guide.  
    IF OBJECT_ID(N'Sales.GetSalesOrderByCountry', N'P') IS NOT NULL  
        DROP PROCEDURE Sales.GetSalesOrderByCountry;  
    GO  
    CREATE PROCEDURE Sales.GetSalesOrderByCountry   
        (@Country nvarchar(60))  
    AS  
    BEGIN  
        SELECT *  
        FROM Sales.SalesOrderHeader AS h   
        INNER JOIN Sales.Customer AS c ON h.CustomerID = c.CustomerID  
        INNER JOIN Sales.SalesTerritory AS t ON c.TerritoryID = t.TerritoryID  
        WHERE t.CountryRegionCode = @Country;  
    END  
    GO  
    --Create the plan guide.  
    EXEC sp_create_plan_guide N'Guide3',  
        N'SELECT *  
        FROM Sales.SalesOrderHeader AS h   
        INNER JOIN Sales.Customer AS c ON h.CustomerID = c.CustomerID  
        INNER JOIN Sales.SalesTerritory AS t ON c.TerritoryID = t.TerritoryID  
        WHERE t.CountryRegionCode = @Country',  
        N'OBJECT',  
        N'Sales.GetSalesOrderByCountry',  
        NULL,  
        N'OPTION (OPTIMIZE FOR (@Country = N''US''))';  
    --Disable the plan guide.  
    EXEC sp_control_plan_guide N'DISABLE', N'Guide3';  
    GO  
    --Enable the plan guide.  
    EXEC sp_control_plan_guide N'ENABLE', N'Guide3';  
    GO  
  
    ```  
  
#### <a name="to-disable-or-enable-all-plan-guides-in-a-database"></a><span data-ttu-id="473db-136">Отключение или включение всех структур планов в базе данных</span><span class="sxs-lookup"><span data-stu-id="473db-136">To disable or enable all plan guides in a database</span></span>  
  
1.  <span data-ttu-id="473db-137">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="473db-137">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="473db-138">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="473db-138">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="473db-139">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="473db-139">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    --Disable all plan guides in the database.  
    EXEC sp_control_plan_guide N'DISABLE ALL';  
    GO  
    --Enable all plan guides in the database.  
    EXEC sp_control_plan_guide N'ENABLE ALL';  
    GO  
  
    ```  
  
 <span data-ttu-id="473db-140">Дополнительные сведения см. в разделе [sp_control_plan_guide (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-control-plan-guide-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="473db-140">For more information, see [sp_control_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-control-plan-guide-transact-sql).</span></span>  
  
  
