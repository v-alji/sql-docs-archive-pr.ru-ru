---
title: Удаление определяемых пользователем функций | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
ms.assetid: db1d668a-23b7-4757-a9c5-1bd848ba7f6d
author: rothja
ms.author: jroth
ms.openlocfilehash: e5f6b2b306c4fe8db08b088d9607cfb19ab0f25e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668120"
---
# <a name="delete-user-defined-functions"></a><span data-ttu-id="525a5-102">Удаление определенных пользователем функций</span><span class="sxs-lookup"><span data-stu-id="525a5-102">Delete User-defined Functions</span></span>
  <span data-ttu-id="525a5-103">Определяемые пользователем функции в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] можно удалить с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)]</span><span class="sxs-lookup"><span data-stu-id="525a5-103">You can delete (drop) user-defined functions in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)]</span></span>  
  
 <span data-ttu-id="525a5-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="525a5-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="525a5-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="525a5-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="525a5-106">Ограничения</span><span class="sxs-lookup"><span data-stu-id="525a5-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="525a5-107">Безопасность</span><span class="sxs-lookup"><span data-stu-id="525a5-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="525a5-108">**Для удаления определяемой пользователем функции используются**</span><span class="sxs-lookup"><span data-stu-id="525a5-108">**To delete a user-defined function, using:**</span></span>  
  
     [<span data-ttu-id="525a5-109">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="525a5-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="525a5-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="525a5-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="525a5-111">Перед началом</span><span class="sxs-lookup"><span data-stu-id="525a5-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="525a5-112">Ограничения</span><span class="sxs-lookup"><span data-stu-id="525a5-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="525a5-113">Удалить функцию не удастся, если в базе данных имеются функции Transact-SQL или представления, которые ссылаются на эту функцию и были созданы с помощью SCHEMABINDING, или при наличии вычисляемых столбцов, ограничений CHECK либо DEFAULT, которые ссылаются на эту функцию.</span><span class="sxs-lookup"><span data-stu-id="525a5-113">You will not be able to delete the function if there are Transact-SQL functions or views in the database that reference this function and were created by using SCHEMABINDING, or if there are computed columns, CHECK constraints, or DEFAULT constraints that reference the function.</span></span>  
  
-   <span data-ttu-id="525a5-114">Удалить функцию не удастся, если имеются вычисляемые столбцы, которые ссылаются на эту функцию и были индексированы.</span><span class="sxs-lookup"><span data-stu-id="525a5-114">You will not be able to delete the function if there are computed columns that reference this function and have been indexed.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="525a5-115">безопасность</span><span class="sxs-lookup"><span data-stu-id="525a5-115">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="525a5-116">Permissions</span><span class="sxs-lookup"><span data-stu-id="525a5-116">Permissions</span></span>  
 <span data-ttu-id="525a5-117">Необходимо разрешение ALTER на схему, которой принадлежит функция, или разрешение CONTROL на функцию.</span><span class="sxs-lookup"><span data-stu-id="525a5-117">Requires ALTER permission on the schema to which the function belongs, or CONTROL permission on the function.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="525a5-118">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="525a5-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-a-user-defined-function"></a><span data-ttu-id="525a5-119">Удаление определяемой пользователем функции</span><span class="sxs-lookup"><span data-stu-id="525a5-119">To delete a user-defined function</span></span>  
  
1.  <span data-ttu-id="525a5-120">Щелкните значок плюса рядом с базой данных, содержащей функцию, которую надо изменить.</span><span class="sxs-lookup"><span data-stu-id="525a5-120">Click on the plus sign next to the database that contains the function you wish to modify.</span></span>  
  
2.  <span data-ttu-id="525a5-121">Щелкните значок плюса рядом с папкой **Программирование** .</span><span class="sxs-lookup"><span data-stu-id="525a5-121">Click on the plus sign next to the **Programmability** folder.</span></span>  
  
3.  <span data-ttu-id="525a5-122">Щелкните значок плюса рядом с папкой, содержащей функцию, которую надо изменить.</span><span class="sxs-lookup"><span data-stu-id="525a5-122">Click the plus sign next to the folder that contains the function you wish to modify:</span></span>  
  
    -   <span data-ttu-id="525a5-123">Table-valued Function</span><span class="sxs-lookup"><span data-stu-id="525a5-123">Table-valued Function</span></span>  
  
    -   <span data-ttu-id="525a5-124">Скалярная функция</span><span class="sxs-lookup"><span data-stu-id="525a5-124">Scalar-valued Function</span></span>  
  
    -   <span data-ttu-id="525a5-125">Агрегатная функция</span><span class="sxs-lookup"><span data-stu-id="525a5-125">Aggregate Function</span></span>  
  
4.  <span data-ttu-id="525a5-126">Щелкните правой кнопкой мыши функцию, которую нужно удалить, и выберите пункт **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="525a5-126">Right-click the function you want to delete and select **Delete**.</span></span>  
  
5.  <span data-ttu-id="525a5-127">В диалоговом окне **Удаление объекта** нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="525a5-127">In the **Delete Object** dialog box, click **OK**.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="525a5-128">Щелкните **Показать зависимости** в диалоговом окне **Удаление объекта** , чтобы открыть диалоговое окно _имя_функции_**Зависимости** .</span><span class="sxs-lookup"><span data-stu-id="525a5-128">Click **Show Dependencies** in the **Delete Object** dialog box to open the _function_name_**Dependencies** dialog box.</span></span> <span data-ttu-id="525a5-129">При этом будут отображены все объекты, зависящие от функции, и все объекты, от которых зависит функция.</span><span class="sxs-lookup"><span data-stu-id="525a5-129">This will show all of the objects that depend on the function and all of the objects on which the function depends.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="525a5-130">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="525a5-130">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-a-user-defined-function"></a><span data-ttu-id="525a5-131">Удаление определяемой пользователем функции</span><span class="sxs-lookup"><span data-stu-id="525a5-131">To delete a user-defined function</span></span>  
  
1.  <span data-ttu-id="525a5-132">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="525a5-132">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="525a5-133">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="525a5-133">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="525a5-134">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="525a5-134">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- creates function called "Sales.ufn_SalesByStore"  
    USE AdventureWorks2012;  
    GO  
    CREATE FUNCTION Sales.ufn_SalesByStore (@storeid int)  
    RETURNS TABLE  
    AS  
    RETURN   
    (  
        SELECT P.ProductID, P.Name, SUM(SD.LineTotal) AS 'Total'  
        FROM Production.Product AS P   
        JOIN Sales.SalesOrderDetail AS SD ON SD.ProductID = P.ProductID  
        JOIN Sales.SalesOrderHeader AS SH ON SH.SalesOrderID = SD.SalesOrderID  
        JOIN Sales.Customer AS C ON SH.CustomerID = C.CustomerID  
        WHERE C.StoreID = @storeid  
        GROUP BY P.ProductID, P.Name  
    );  
    GO  
    ```  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- determines if function exists in database  
    IF OBJECT_ID (N'Sales.fn_SalesByStore', N'IF') IS NOT NULL  
    -- deletes function  
        DROP FUNCTION Sales.fn_SalesByStore;  
    GO  
    ```  
  
 <span data-ttu-id="525a5-135">Дополнительные сведения см. в статье [DROP FUNCTION (Transact-SQL)](/sql/t-sql/statements/drop-function-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="525a5-135">For more information, see [DROP FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-function-transact-sql).</span></span>  
  
  
