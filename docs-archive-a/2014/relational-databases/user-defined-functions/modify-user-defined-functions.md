---
title: Изменение определяемых пользователем функций | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
ms.assetid: 891c37b3-cb72-411f-9937-ee87e6d95f34
author: rothja
ms.author: jroth
ms.openlocfilehash: 1cf25fef91834e237f5cbaac26350220840830bc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668117"
---
# <a name="modify-user-defined-functions"></a><span data-ttu-id="354a1-102">Изменение определяемых пользователем функций</span><span class="sxs-lookup"><span data-stu-id="354a1-102">Modify User-defined Functions</span></span>
  <span data-ttu-id="354a1-103">Определяемые пользователем функции [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] можно изменять с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="354a1-103">You can modify user-defined functions in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="354a1-104">При изменении определяемых пользователем функций описанными ниже методами разрешения этих функций не будут изменены, также не будут затронуты любые другие зависимые функции, хранимые процедуры или триггеры.</span><span class="sxs-lookup"><span data-stu-id="354a1-104">Modifying user-defined functions as described below will not change the functions' permissions, nor will it affect any dependent functions, stored procedures, or triggers.</span></span>  
  
 <span data-ttu-id="354a1-105">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="354a1-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="354a1-106">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="354a1-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="354a1-107">Ограничения</span><span class="sxs-lookup"><span data-stu-id="354a1-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="354a1-108">Безопасность</span><span class="sxs-lookup"><span data-stu-id="354a1-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="354a1-109">**Изменение определяемой пользователем функции с помощью:**</span><span class="sxs-lookup"><span data-stu-id="354a1-109">**To modify a user-defined function, using:**</span></span>  
  
     [<span data-ttu-id="354a1-110">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="354a1-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="354a1-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="354a1-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="354a1-112">Перед началом</span><span class="sxs-lookup"><span data-stu-id="354a1-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="354a1-113">Ограничения</span><span class="sxs-lookup"><span data-stu-id="354a1-113">Limitations and Restrictions</span></span>  
 <span data-ttu-id="354a1-114">Инструкцию ALTER FUNCTION нельзя использовать для выполнения следующих действий.</span><span class="sxs-lookup"><span data-stu-id="354a1-114">ALTER FUNCTION cannot be used to perform any of the following actions:</span></span>  
  
-   <span data-ttu-id="354a1-115">Преобразование скалярной функции в функцию с табличным значением или наоборот.</span><span class="sxs-lookup"><span data-stu-id="354a1-115">Change a scalar-valued function to a table-valued function, or vice versa.</span></span>  
  
-   <span data-ttu-id="354a1-116">Преобразование встроенной функции в функцию из нескольких инструкций или наоборот.</span><span class="sxs-lookup"><span data-stu-id="354a1-116">Change an inline function to a multistatement function, or vice versa.</span></span>  
  
-   <span data-ttu-id="354a1-117">Преобразование функции Transact-SQL в функцию CLR или наоборот.</span><span class="sxs-lookup"><span data-stu-id="354a1-117">Change a Transact-SQL function to a CLR function, or vice-versa.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="354a1-118">безопасность</span><span class="sxs-lookup"><span data-stu-id="354a1-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="354a1-119">Permissions</span><span class="sxs-lookup"><span data-stu-id="354a1-119">Permissions</span></span>  
 <span data-ttu-id="354a1-120">Требует разрешения ALTER для функции или для схемы.</span><span class="sxs-lookup"><span data-stu-id="354a1-120">Requires ALTER permission on the function or on the schema.</span></span> <span data-ttu-id="354a1-121">Если в функции указан определяемый пользователем тип, требуется разрешение EXECUTE на этот тип.</span><span class="sxs-lookup"><span data-stu-id="354a1-121">If the function specifies a user-defined type, requires EXECUTE permission on the type.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="354a1-122">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="354a1-122">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-modify-a-user-defined-function"></a><span data-ttu-id="354a1-123">Изменение определяемой пользователем функции</span><span class="sxs-lookup"><span data-stu-id="354a1-123">To modify a user-defined function</span></span>  
  
1.  <span data-ttu-id="354a1-124">Щелкните значок плюса рядом с базой данных, содержащей функцию, которую надо изменить.</span><span class="sxs-lookup"><span data-stu-id="354a1-124">Click on the plus sign next to the database that contains the function you wish to modify.</span></span>  
  
2.  <span data-ttu-id="354a1-125">Щелкните значок плюса рядом с папкой **Программирование** .</span><span class="sxs-lookup"><span data-stu-id="354a1-125">Click on the plus sign next to the **Programmability** folder.</span></span>  
  
3.  <span data-ttu-id="354a1-126">Щелкните значок плюса рядом с папкой, содержащей функцию, которую надо изменить.</span><span class="sxs-lookup"><span data-stu-id="354a1-126">Click the plus sign next to the folder that contains the function you wish to modify:</span></span>  
  
    -   <span data-ttu-id="354a1-127">Table-valued Function</span><span class="sxs-lookup"><span data-stu-id="354a1-127">Table-valued Function</span></span>  
  
    -   <span data-ttu-id="354a1-128">Скалярная функция</span><span class="sxs-lookup"><span data-stu-id="354a1-128">Scalar-valued Function</span></span>  
  
    -   <span data-ttu-id="354a1-129">Агрегатная функция</span><span class="sxs-lookup"><span data-stu-id="354a1-129">Aggregate Function</span></span>  
  
4.  <span data-ttu-id="354a1-130">Щелкните правой кнопкой мыши функцию, которую нужно изменить, и выберите пункт **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="354a1-130">Right-click the function you want to modify and select **Modify**.</span></span>  
  
5.  <span data-ttu-id="354a1-131">В окне запроса внесите нужные изменения в инструкцию ALTER FUNCTION.</span><span class="sxs-lookup"><span data-stu-id="354a1-131">In the Query Window, make the necessary changes to the ALTER FUNCTION statement.</span></span>  
  
6.  <span data-ttu-id="354a1-132">В меню **Файл** выберите пункт **Сохранить**_имя_функции_.</span><span class="sxs-lookup"><span data-stu-id="354a1-132">On the **File** menu, click **Save**_function_name_.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="354a1-133">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="354a1-133">Using Transact-SQL</span></span>  
  
#### <a name="to-modify-a-user-defined-function"></a><span data-ttu-id="354a1-134">Изменение определяемой пользователем функции</span><span class="sxs-lookup"><span data-stu-id="354a1-134">To modify a user-defined function</span></span>  
  
1.  <span data-ttu-id="354a1-135">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="354a1-135">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="354a1-136">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="354a1-136">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="354a1-137">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="354a1-137">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Scalar-Valued Function  
    USE [AdventureWorks2012]  
    GO  
    ALTER FUNCTION [dbo].[ufnGetAccountingEndDate]()  
    RETURNS [datetime]   
    AS   
    BEGIN  
        RETURN DATEADD(millisecond, -2, CONVERT(datetime, '20040701', 112));  
    END;  
    ```  
  
    ```  
    -- Table-Valued Function   
    USE [AdventureWorks2012]  
    GO  
    ALTER FUNCTION [dbo].[ufnGetContactInformation](@PersonID int)  
    RETURNS @retContactInformation TABLE   
    (  
        -- Columns returned by the function  
        [PersonID] int NOT NULL,   
        [FirstName] [nvarchar](50) NULL,   
        [LastName] [nvarchar](50) NULL,   
        [JobTitle] [nvarchar](50) NULL,  
        [BusinessEntityType] [nvarchar](50) NULL  
    )  
    AS   
    -- Returns the first name, last name, job title and business entity type for the specified contact.  
    -- Since a contact can serve multiple roles, more than one row may be returned.  
    BEGIN  
    IF @PersonID IS NOT NULL   
    BEGIN  
         IF EXISTS(SELECT * FROM [HumanResources].[Employee] e   
         WHERE e.[BusinessEntityID] = @PersonID)   
         INSERT INTO @retContactInformation  
              SELECT @PersonID, p.FirstName, p.LastName, e.[JobTitle], 'Employee'  
              FROM [HumanResources].[Employee] AS e  
              INNER JOIN [Person].[Person] p ON p.[BusinessEntityID] = e.[BusinessEntityID]  
              WHERE e.[BusinessEntityID] = @PersonID;  
  
         IF EXISTS(SELECT * FROM [Purchasing].[Vendor] AS v  
         INNER JOIN [Person].[BusinessEntityContact] bec ON bec.[BusinessEntityID] = v.[BusinessEntityID]  
         WHERE bec.[PersonID] = @PersonID)  
         INSERT INTO @retContactInformation  
              SELECT @PersonID, p.FirstName, p.LastName, ct.[Name], 'Vendor Contact'   
              FROM [Purchasing].[Vendor] AS v  
              INNER JOIN [Person].[BusinessEntityContact] bec ON bec.[BusinessEntityID] = v.[BusinessEntityID]  
              INNER JOIN [Person].ContactType ct ON ct.[ContactTypeID] = bec.[ContactTypeID]  
              INNER JOIN [Person].[Person] p ON p.[BusinessEntityID] = bec.[PersonID]  
              WHERE bec.[PersonID] = @PersonID;  
  
         IF EXISTS(SELECT * FROM [Sales].[Store] AS s  
         INNER JOIN [Person].[BusinessEntityContact] bec ON bec.[BusinessEntityID] = s.[BusinessEntityID]  
         WHERE bec.[PersonID] = @PersonID)  
         INSERT INTO @retContactInformation  
              SELECT @PersonID, p.FirstName, p.LastName, ct.[Name], 'Store Contact'   
              FROM [Sales].[Store] AS s  
              INNER JOIN [Person].[BusinessEntityContact] bec ON bec.[BusinessEntityID] = s.[BusinessEntityID]  
              INNER JOIN [Person].ContactType ct ON ct.[ContactTypeID] = bec.[ContactTypeID]  
              INNER JOIN [Person].[Person] p ON p.[BusinessEntityID] = bec.[PersonID]  
              WHERE bec.[PersonID] = @PersonID;  
  
         IF EXISTS(SELECT * FROM [Person].[Person] AS p  
         INNER JOIN [Sales].[Customer] AS c ON c.[PersonID] = p.[BusinessEntityID]  
         WHERE p.[BusinessEntityID] = @PersonID AND c.[StoreID] IS NULL)   
         INSERT INTO @retContactInformation  
              SELECT @PersonID, p.FirstName, p.LastName, NULL, 'Consumer'   
              FROM [Person].[Person] AS p  
              INNER JOIN [Sales].[Customer] AS c ON c.[PersonID] = p.[BusinessEntityID]  
              WHERE p.[BusinessEntityID] = @PersonID AND c.[StoreID] IS NULL;   
         END  
    RETURN;  
    END;  
    ```  
  
 <span data-ttu-id="354a1-138">Дополнительные сведения см. в статье [ALTER FUNCTION (Transact-SQL)](/sql/t-sql/statements/alter-function-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="354a1-138">For more information, see [ALTER FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-function-transact-sql).</span></span>  
  
  
