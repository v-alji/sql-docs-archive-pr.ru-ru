---
title: Удаление структуры плана | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- plan guides [SQL Server], deleting
ms.assetid: aa4d3188-6927-43de-a3e3-90fc16eeaca7
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 303ad6f59cbe24265aec66f3cb780a5b4ad4f157
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730542"
---
# <a name="delete-a-plan-guide"></a><span data-ttu-id="2e8f1-102">Удаление структуры плана</span><span class="sxs-lookup"><span data-stu-id="2e8f1-102">Delete a Plan Guide</span></span>
  <span data-ttu-id="2e8f1-103">Удалить структуру плана в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] можно с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2e8f1-103">You can delete (drop) a plan guide in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="2e8f1-104">С помощью [!INCLUDE[tsql](../../includes/tsql-md.md)]также можно удалить все структуры планов в базе данных.</span><span class="sxs-lookup"><span data-stu-id="2e8f1-104">Using [!INCLUDE[tsql](../../includes/tsql-md.md)], you can also delete all of the plan guides in a database.</span></span>  
  
 <span data-ttu-id="2e8f1-105">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="2e8f1-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="2e8f1-106">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="2e8f1-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="2e8f1-107">Безопасность</span><span class="sxs-lookup"><span data-stu-id="2e8f1-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="2e8f1-108">**Удаление структуры плана с помощью различных средств.**</span><span class="sxs-lookup"><span data-stu-id="2e8f1-108">**To delete a plan guide, using:**</span></span>  
  
     [<span data-ttu-id="2e8f1-109">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2e8f1-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="2e8f1-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2e8f1-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="2e8f1-111">Перед началом</span><span class="sxs-lookup"><span data-stu-id="2e8f1-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="2e8f1-112">безопасность</span><span class="sxs-lookup"><span data-stu-id="2e8f1-112">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="2e8f1-113">Permissions</span><span class="sxs-lookup"><span data-stu-id="2e8f1-113">Permissions</span></span>  
 <span data-ttu-id="2e8f1-114">Для удаления структуры плана OBJECT необходимо разрешение ALTER для того объекта (например функции, хранимой процедуры), на который ссылается структура плана.</span><span class="sxs-lookup"><span data-stu-id="2e8f1-114">Deleting an OBJECT plan guide requires ALTER permission on the object (for example: function, stored procedure) that is referenced by the plan guide.</span></span> <span data-ttu-id="2e8f1-115">Все остальные структуры планов требуют разрешения ALTER DATABASE.</span><span class="sxs-lookup"><span data-stu-id="2e8f1-115">All other plan guides require ALTER DATABASE permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="2e8f1-116">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2e8f1-116">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-a-plan-guide"></a><span data-ttu-id="2e8f1-117">Удаление структуры плана</span><span class="sxs-lookup"><span data-stu-id="2e8f1-117">To delete a plan guide</span></span>  
  
1.  <span data-ttu-id="2e8f1-118">Щелкните значок «+», чтобы развернуть базу данных, в которой требуется удалить структуру плана, затем щелкните значок «+», чтобы развернуть папку **Программирование** .</span><span class="sxs-lookup"><span data-stu-id="2e8f1-118">Click the plus sign to expand the database in which you want to delete a plan guide, and then click the plus sign to expand the **Programmability** folder.</span></span>  
  
2.  <span data-ttu-id="2e8f1-119">Щелкните значок «+», чтобы развернуть папку **Структуры планов** .</span><span class="sxs-lookup"><span data-stu-id="2e8f1-119">Click the plus sign to expand the **Plan Guides** folder.</span></span>  
  
3.  <span data-ttu-id="2e8f1-120">Щелкните правой кнопкой мыши структуру плана, которую необходимо удалить, и выберите команду **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="2e8f1-120">Right-click the plan guide you want to delete and select **Delete**.</span></span>  
  
4.  <span data-ttu-id="2e8f1-121">В диалоговом окне **Удаление объекта** убедитесь, что выбрана верная структура плана, и нажмите кнопку **OК**.</span><span class="sxs-lookup"><span data-stu-id="2e8f1-121">In the **Delete Object** dialog box, ensure that the correct plan guide is selected and then click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="2e8f1-122">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2e8f1-122">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-a-single-plan-guide"></a><span data-ttu-id="2e8f1-123">Удаление одной структуры плана</span><span class="sxs-lookup"><span data-stu-id="2e8f1-123">To delete a single plan guide</span></span>  
  
1.  <span data-ttu-id="2e8f1-124">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2e8f1-124">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="2e8f1-125">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="2e8f1-125">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="2e8f1-126">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="2e8f1-126">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
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
    GO  
    --Drop the plan guide.  
    EXEC sp_control_plan_guide N'DROP', N'Guide3';  
    GO  
    ```  
  
#### <a name="to-delete-all-plan-guides-in-a-database"></a><span data-ttu-id="2e8f1-127">Удаление всех структур планов в базе данных</span><span class="sxs-lookup"><span data-stu-id="2e8f1-127">To delete all plan guides in a database</span></span>  
  
1.  <span data-ttu-id="2e8f1-128">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2e8f1-128">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="2e8f1-129">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="2e8f1-129">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="2e8f1-130">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="2e8f1-130">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    EXEC sp_control_plan_guide N'DROP ALL';  
    GO  
    ```  
  
 <span data-ttu-id="2e8f1-131">Дополнительные сведения см. в разделе [sp_control_plan_guide (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-control-plan-guide-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2e8f1-131">For more information, see [sp_control_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-control-plan-guide-transact-sql).</span></span>  
  
  
