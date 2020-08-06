---
title: Руководство. Цепочки владения и переключение контекста | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- context switching [SQL Server], tutorials
- ownership chains [SQL Server]
ms.assetid: db5d4cc3-5fc5-4cf5-afc1-8d4edc1d512b
author: rothja
ms.author: jroth
ms.openlocfilehash: 1e9072a68dd3179e5900fda06d4fea58b484a37e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657622"
---
# <a name="tutorial-ownership-chains-and-context-switching"></a><span data-ttu-id="b46a1-102">Tutorial: Ownership Chains and Context Switching</span><span class="sxs-lookup"><span data-stu-id="b46a1-102">Tutorial: Ownership Chains and Context Switching</span></span>
  <span data-ttu-id="b46a1-103">В этом учебнике приведен пример, в котором рассматриваются основные понятия безопасности [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , включая цепочки владения и переключение контекста.</span><span class="sxs-lookup"><span data-stu-id="b46a1-103">This tutorial uses a scenario to illustrate [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] security concepts involving ownership chains and user context switching.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b46a1-104">Для запуска кода в этом учебнике необходимо, чтобы был настроен режим смешанной безопасности. Кроме того, необходимо установить базу данных [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b46a1-104">To run the code in this tutorial you must have both Mixed Mode security configured and the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] database installed.</span></span> <span data-ttu-id="b46a1-105">Дополнительные сведения о смешанном режиме безопасности см. в разделе [Выбор режима проверки подлинности](security/choose-an-authentication-mode.md).</span><span class="sxs-lookup"><span data-stu-id="b46a1-105">For more information about Mixed Mode security, see [Choose an Authentication Mode](security/choose-an-authentication-mode.md).</span></span>  
  
## <a name="scenario"></a><span data-ttu-id="b46a1-106">Сценарий</span><span class="sxs-lookup"><span data-stu-id="b46a1-106">Scenario</span></span>  
 <span data-ttu-id="b46a1-107">В этом сценарии двум пользователям нужны учетные записи для доступа к данным о заказах на покупку, которые хранятся в базе данных [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b46a1-107">In this scenario, two users need accounts to access purchase order data stored in the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] database.</span></span> <span data-ttu-id="b46a1-108">Требования:</span><span class="sxs-lookup"><span data-stu-id="b46a1-108">The requirements are as follows:</span></span>  
  
-   <span data-ttu-id="b46a1-109">Пользователь первой учетной записи (ТестовыйМенеджер) должен видеть все сведения о каждом заказе на покупку.</span><span class="sxs-lookup"><span data-stu-id="b46a1-109">The first account (TestManagerUser) must be able to see all details in every purchase order.</span></span>  
  
-   <span data-ttu-id="b46a1-110">Пользователь второй учетной записи (ТестовыйСотрудник) должен видеть номера заказов на покупку, даты заказов, даты отгрузки, коды продуктов, а также количество отправленных и полученных экземпляров продукта в заказе по номеру заказа (для заказов, получаемых частичной отгрузкой).</span><span class="sxs-lookup"><span data-stu-id="b46a1-110">The second account (TestEmployeeUser) must be able to see the purchase order number, order date, shipping date, product ID numbers, and the ordered and received items per purchase order, by purchase order number, for items where partial shipments have been received.</span></span>  
  
-   <span data-ttu-id="b46a1-111">Все другие учетные записи должны сохранять текущие разрешения.</span><span class="sxs-lookup"><span data-stu-id="b46a1-111">All other accounts must retain their current permissions.</span></span>  
  
 <span data-ttu-id="b46a1-112">Чтобы выполнялись требования этого сценария, этот пример разбит на 4 части, в которых проиллюстрированы основные понятия, касающиеся цепочек владения и переключения контекста.</span><span class="sxs-lookup"><span data-stu-id="b46a1-112">To fulfill the requirements of this scenario, the example is broken into four parts that demonstrate the concepts of ownership chains and context switching:</span></span>  
  
1.  <span data-ttu-id="b46a1-113">Настройка среды.</span><span class="sxs-lookup"><span data-stu-id="b46a1-113">Configuring the environment.</span></span>  
  
2.  <span data-ttu-id="b46a1-114">Создание хранимой процедуры для получения доступа к данным по заказам на покупку.</span><span class="sxs-lookup"><span data-stu-id="b46a1-114">Creating a stored procedure to access data by purchase order.</span></span>  
  
3.  <span data-ttu-id="b46a1-115">Доступ к данным через хранимую процедуру.</span><span class="sxs-lookup"><span data-stu-id="b46a1-115">Accessing the data through the stored procedure.</span></span>  
  
4.  <span data-ttu-id="b46a1-116">Сброс среды.</span><span class="sxs-lookup"><span data-stu-id="b46a1-116">Resetting the environment.</span></span>  
  
 <span data-ttu-id="b46a1-117">Каждый блок кода в этом примере объясняется по порядку.</span><span class="sxs-lookup"><span data-stu-id="b46a1-117">Each code block in this example is explained in line.</span></span> <span data-ttu-id="b46a1-118">Чтобы скопировать весь пример, см. раздел [Пример целиком](#CompleteExample) в конце этого учебника.</span><span class="sxs-lookup"><span data-stu-id="b46a1-118">To copy the complete example, see [Complete Example](#CompleteExample) at the end of this tutorial.</span></span>  
  
## <a name="1-configure-the-environment"></a><span data-ttu-id="b46a1-119">1. Настройка среды</span><span class="sxs-lookup"><span data-stu-id="b46a1-119">1. Configure the Environment</span></span>  
 <span data-ttu-id="b46a1-120">Используйте [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] и следующий код, чтобы открыть `AdventureWorks2012` базу данных, и используйте `CURRENT_USER` [!INCLUDE[tsql](../includes/tsql-md.md)] инструкцию, чтобы убедиться, что пользователь dbo отображается в качестве контекста.</span><span class="sxs-lookup"><span data-stu-id="b46a1-120">Use [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] and the following code to open the `AdventureWorks2012` database, and use the `CURRENT_USER` [!INCLUDE[tsql](../includes/tsql-md.md)] statement to check that the dbo user is displayed as the context.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT CURRENT_USER AS 'Current User Name';  
GO  
```  
  
 <span data-ttu-id="b46a1-121">Дополнительные сведения об инструкции CURRENT_USER см. в разделе [CURRENT_USER (Transact-SQL)](/sql/t-sql/functions/current-user-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b46a1-121">For more information about the CURRENT_USER statement, see [CURRENT_USER &#40;Transact-SQL&#41;](/sql/t-sql/functions/current-user-transact-sql).</span></span>  
  
 <span data-ttu-id="b46a1-122">От имени пользователя dbo создайте с помощью этого кода двух пользователей на сервере и в базе данных [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b46a1-122">Use this code as the dbo user to create two users on the server and in the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] database.</span></span>  
  
```  
CREATE LOGIN TestManagerUser   
    WITH PASSWORD = '340$Uuxwp7Mcxo7Khx';  
GO  
CREATE USER TestManagerUser   
   FOR LOGIN TestManagerUser  
   WITH DEFAULT_SCHEMA = Purchasing;  
GO   
  
CREATE LOGIN TestEmployeeUser  
    WITH PASSWORD = '340$Uuxwp7Mcxo7Khy';  
GO  
CREATE USER TestEmployeeUser   
   FOR LOGIN TestEmployeeUser;  
GO   
```  
  
 <span data-ttu-id="b46a1-123">Дополнительные сведения об инструкции CREATE USER см. в разделе [CREATE USER (Transact-SQL)](/sql/t-sql/statements/create-user-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b46a1-123">For more information about the CREATE USER statement, see [CREATE USER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-user-transact-sql).</span></span> <span data-ttu-id="b46a1-124">Дополнительные сведения об инструкции CREATE LOGIN см. в разделе [CREATE LOGIN (Transact-SQL)](/sql/t-sql/statements/create-login-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b46a1-124">For more information about the CREATE LOGIN statement, see [CREATE LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-login-transact-sql).</span></span>  
  
 <span data-ttu-id="b46a1-125">Изменить владельца схемы `Purchasing` на учетную запись `TestManagerUser` можно с помощью приведенного ниже кода.</span><span class="sxs-lookup"><span data-stu-id="b46a1-125">Use the following code to change the ownership of the `Purchasing` schema to the `TestManagerUser` account.</span></span> <span data-ttu-id="b46a1-126">Это позволит учетной записи использовать все инструкции доступа языка обработки данных DML (например, разрешения `SELECT` или `INSERT` ) для объектов, которые содержит эта схема.</span><span class="sxs-lookup"><span data-stu-id="b46a1-126">This allows that account to use all Data Manipulation Language (DML) statement access (such as `SELECT` and `INSERT` permissions) on the objects it contains.</span></span> <span data-ttu-id="b46a1-127">`TestManagerUser` также предоставляет возможность создавать хранимые процедуры.</span><span class="sxs-lookup"><span data-stu-id="b46a1-127">`TestManagerUser` is also granted the ability to create stored procedures.</span></span>  
  
```  
/* Change owner of the Purchasing Schema to TestManagerUser */  
ALTER AUTHORIZATION   
   ON SCHEMA::Purchasing   
   TO TestManagerUser;  
GO  
  
GRANT CREATE PROCEDURE   
   TO TestManagerUser   
   WITH GRANT OPTION;  
GO  
```  
  
 <span data-ttu-id="b46a1-128">Дополнительные сведения об инструкции GRANT см. в разделе [GRANT (Transact-SQL)](/sql/t-sql/statements/grant-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b46a1-128">For more information about the GRANT statement, see [GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql).</span></span> <span data-ttu-id="b46a1-129">Дополнительные сведения о хранимых процедурах см. в разделе [Хранимые процедуры (компонент Database Engine)](stored-procedures/stored-procedures-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="b46a1-129">For more information about stored procedures, see [Stored Procedures &#40;Database Engine&#41;](stored-procedures/stored-procedures-database-engine.md).</span></span> <span data-ttu-id="b46a1-130">Афишу всех [!INCLUDE[ssDE](../includes/ssde-md.md)] разрешений см. в разделе [https://github.com/microsoft/sql-server-samples/blob/master/samples/features/security/permissions-posters/Microsoft_SQL_Server_2017_and_Azure_SQL_Database_permissions_infographic.pdf](https://github.com/microsoft/sql-server-samples/blob/master/samples/features/security/permissions-posters/Microsoft_SQL_Server_2017_and_Azure_SQL_Database_permissions_infographic.pdf) .</span><span class="sxs-lookup"><span data-stu-id="b46a1-130">For a poster of all [!INCLUDE[ssDE](../includes/ssde-md.md)] permissions, see [https://github.com/microsoft/sql-server-samples/blob/master/samples/features/security/permissions-posters/Microsoft_SQL_Server_2017_and_Azure_SQL_Database_permissions_infographic.pdf](https://github.com/microsoft/sql-server-samples/blob/master/samples/features/security/permissions-posters/Microsoft_SQL_Server_2017_and_Azure_SQL_Database_permissions_infographic.pdf).</span></span>  
  
## <a name="2-create-a-stored-procedure-to-access-data"></a><span data-ttu-id="b46a1-131">2. Создание хранимой процедуры для доступа к данным</span><span class="sxs-lookup"><span data-stu-id="b46a1-131">2. Create a Stored Procedure to Access Data</span></span>  
 <span data-ttu-id="b46a1-132">Для переключения контекста внутри базы данных используйте инструкцию EXECUTE AS.</span><span class="sxs-lookup"><span data-stu-id="b46a1-132">To switch context within a database, use the EXECUTE AS statement.</span></span> <span data-ttu-id="b46a1-133">Инструкции EXECUTE AS требуются разрешения IMPERSONATE.</span><span class="sxs-lookup"><span data-stu-id="b46a1-133">EXECUTE AS requires IMPERSONATE permissions.</span></span>  
  
 <span data-ttu-id="b46a1-134">С помощью инструкции `EXECUTE AS` в приведенном ниже коде измените контекст на `TestManagerUser` и создайте хранимую процедуру, показывающую только те данные, которые должны быть видны пользователю `TestEmployeeUser`.</span><span class="sxs-lookup"><span data-stu-id="b46a1-134">Use the `EXECUTE AS` statement in the following code to change the context to `TestManagerUser` and create a stored procedure showing only the data required by `TestEmployeeUser`.</span></span> <span data-ttu-id="b46a1-135">Для соответствия требованиям хранимая процедура принимает одну переменную для номера заказа на покупку и не показывает финансовую информацию, а предложение WHERE ограничивает результаты для частичных отгрузок.</span><span class="sxs-lookup"><span data-stu-id="b46a1-135">To satisfy the requirements, the stored procedure accepts one variable for the purchase order number and does not display financial information, and the WHERE clause limits the results to partial shipments.</span></span>  
  
```  
EXECUTE AS LOGIN = 'TestManagerUser'  
GO  
SELECT CURRENT_USER AS 'Current User Name';  
GO  
  
/* Note: The user that calls the EXECUTE AS statement must have IMPERSONATE permissions on the target principal */  
CREATE PROCEDURE usp_ShowWaitingItems @ProductID int  
AS  
BEGIN   
   SELECT a.PurchaseOrderID, a.OrderDate, a.ShipDate  
      , b.ProductID, b.OrderQty, b.ReceivedQty  
   FROM Purchasing.PurchaseOrderHeader a  
      INNER JOIN Purchasing.PurchaseOrderDetail b  
         ON a.PurchaseOrderID = b.PurchaseOrderID  
   WHERE b.OrderQty > b.ReceivedQty  
      AND @ProductID = b.ProductID  
   ORDER BY b.ProductID ASC  
END  
GO  
```  
  
 <span data-ttu-id="b46a1-136">В данный момент пользователь `TestEmployeeUser` не имеет доступа к объектам базы данных.</span><span class="sxs-lookup"><span data-stu-id="b46a1-136">Currently `TestEmployeeUser` does not have access to any database objects.</span></span> <span data-ttu-id="b46a1-137">Следующий код (все еще в контексте `TestManagerUser` ) предоставляет учетной записи пользователя возможность запрашивать информацию из базовой таблицы через хранимую процедуру.</span><span class="sxs-lookup"><span data-stu-id="b46a1-137">The following code (still in the `TestManagerUser` context) grants the user account the ability to query base-table information through the stored procedure.</span></span>  
  
```  
GRANT EXECUTE  
   ON OBJECT::Purchasing.usp_ShowWaitingItems  
   TO TestEmployeeUser;  
GO  
```  
  
 <span data-ttu-id="b46a1-138">Хотя схема не была указана явно, хранимая процедура является частью схемы `Purchasing` , поскольку пользователь `TestManagerUser` по умолчанию связан со схемой `Purchasing` .</span><span class="sxs-lookup"><span data-stu-id="b46a1-138">The stored procedure is part of the `Purchasing` schema, even though no schema was explicitly specified, because `TestManagerUser` is assigned by default to the `Purchasing` schema.</span></span> <span data-ttu-id="b46a1-139">Для поиска объектов можно использовать информацию из системного каталога, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="b46a1-139">You can use system catalog information to locate objects, as shown in the following code.</span></span>  
  
```  
SELECT a.name AS 'Schema'  
   , b.name AS 'Object Name'  
   , b.type AS 'Object Type'  
FROM sys.schemas a  
   INNER JOIN sys.objects b  
      ON a.schema_id = b.schema_id   
WHERE b.name = 'usp_ShowWaitingItems';  
GO  
```  
  
 <span data-ttu-id="b46a1-140">После завершения этого раздела примера код переключает контекст обратно на dbo с помощью инструкции `REVERT`.</span><span class="sxs-lookup"><span data-stu-id="b46a1-140">With this section of the example completed, the code switches context back to dbo using the `REVERT` statement.</span></span>  
  
```  
REVERT;  
GO  
```  
  
 <span data-ttu-id="b46a1-141">Дополнительные сведения об инструкции REVERT см. в разделе [REVERT (Transact-SQL)](/sql/t-sql/statements/revert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b46a1-141">For more information about the REVERT statement, see [REVERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/revert-transact-sql).</span></span>  
  
## <a name="3-access-data-through-the-stored-procedure"></a><span data-ttu-id="b46a1-142">3. Доступ к данным через хранимую процедуру</span><span class="sxs-lookup"><span data-stu-id="b46a1-142">3. Access Data Through the Stored Procedure</span></span>  
 <span data-ttu-id="b46a1-143">`TestEmployeeUser` не обладает разрешениями на объекты базы данных [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] , кроме разрешения на вход в систему и прав, присвоенных роли базы данных public.</span><span class="sxs-lookup"><span data-stu-id="b46a1-143">`TestEmployeeUser` has no permissions on the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] database objects other than a login and the rights assigned to the public database role.</span></span> <span data-ttu-id="b46a1-144">Следующий код возвращает ошибку при попытке обращения `TestEmployeeUser` к базовым таблицам.</span><span class="sxs-lookup"><span data-stu-id="b46a1-144">The following code returns an error when `TestEmployeeUser` attempts to access base tables.</span></span>  
  
```  
EXECUTE AS LOGIN = 'TestEmployeeUser'  
GO  
SELECT CURRENT_USER AS 'Current User Name';  
GO  
/* This won't work */  
SELECT *  
FROM Purchasing.PurchaseOrderHeader;  
GO  
SELECT *  
FROM Purchasing.PurchaseOrderDetail;  
GO  
```  
  
 <span data-ttu-id="b46a1-145">Поскольку объекты, на которые ссылается процедура, созданная в предыдущем разделе, принадлежат `TestManagerUser` по причине владения схемой `Purchasing` , `TestEmployeeUser` может получить доступ к базовым таблицам через хранимую процедуру.</span><span class="sxs-lookup"><span data-stu-id="b46a1-145">Because the objects referenced by the stored procedure created in the last section are owned by `TestManagerUser` by virtue of the `Purchasing` schema ownership, `TestEmployeeUser` can access the base tables through the stored procedure.</span></span> <span data-ttu-id="b46a1-146">Следующий код, все еще в контексте `TestEmployeeUser` , проводит заказ на покупку 952 как параметр.</span><span class="sxs-lookup"><span data-stu-id="b46a1-146">The following code, still using the `TestEmployeeUser` context, passes purchase order 952 as a parameter.</span></span>  
  
```  
EXEC Purchasing.usp_ShowWaitingItems 952  
GO  
```  
  
## <a name="4-reset-the-environment"></a><span data-ttu-id="b46a1-147">4. Сброс среды</span><span class="sxs-lookup"><span data-stu-id="b46a1-147">4. Reset the Environment</span></span>  
 <span data-ttu-id="b46a1-148">Следующий код с помощью команды `REVERT` изменяет контекст текущей учетной записи обратно на `dbo`и затем выполняет сброс среды.</span><span class="sxs-lookup"><span data-stu-id="b46a1-148">The following code uses the `REVERT` command to return the context of the current account to `dbo`, and then resets the environment.</span></span>  
  
```  
REVERT;  
GO  
ALTER AUTHORIZATION   
ON SCHEMA::Purchasing TO dbo;  
GO  
DROP PROCEDURE Purchasing.usp_ShowWaitingItems;  
GO  
DROP USER TestEmployeeUser;  
GO  
DROP USER TestManagerUser;  
GO  
DROP LOGIN TestEmployeeUser;  
GO  
DROP LOGIN TestManagerUser;  
GO  
```  
  
##  <a name="complete-example"></a><a name="CompleteExample"></a><span data-ttu-id="b46a1-149">Полный пример</span><span class="sxs-lookup"><span data-stu-id="b46a1-149">Complete Example</span></span>  
 <span data-ttu-id="b46a1-150">В этом разделе приведен полный код примера.</span><span class="sxs-lookup"><span data-stu-id="b46a1-150">This section displays the complete example code.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b46a1-151">В этот код не включены две ошибки, которые иллюстрировали невозможность `TestEmployeeUser` получить данные из базовых таблиц.</span><span class="sxs-lookup"><span data-stu-id="b46a1-151">This code does not include the two expected errors that demonstrate the inability of `TestEmployeeUser` to select from base tables.</span></span>  
  
```  
/*   
Script:       UserContextTutorial.sql  
Author:       Microsoft  
Last Updated: Books Online  
Conditions:   Execute as DBO or sysadmin in the AdventureWorks database  
Section 1:    Configure the Environment   
*/  
USE AdventureWorks2012;  
GO  
SELECT CURRENT_USER AS 'Current User Name';  
GO  
/* Create server and database users */  
CREATE LOGIN TestManagerUser   
    WITH PASSWORD = '340$Uuxwp7Mcxo7Khx';  
  
GO  
  
CREATE USER TestManagerUser   
   FOR LOGIN TestManagerUser  
   WITH DEFAULT_SCHEMA = Purchasing;  
GO   
  
CREATE LOGIN TestEmployeeUser  
    WITH PASSWORD = '340$Uuxwp7Mcxo7Khy';  
GO  
CREATE USER TestEmployeeUser   
   FOR LOGIN TestEmployeeUser;  
GO   
  
/* Change owner of the Purchasing Schema to TestManagerUser */  
ALTER AUTHORIZATION   
   ON SCHEMA::Purchasing   
   TO TestManagerUser;  
GO  
  
GRANT CREATE PROCEDURE   
   TO TestManagerUser   
   WITH GRANT OPTION;  
GO  
  
/*   
Section 2: Switch Context and Create Objects  
*/  
EXECUTE AS LOGIN = 'TestManagerUser';  
GO  
SELECT CURRENT_USER AS 'Current User Name';  
GO  
  
/* Note: The user that calls the EXECUTE AS statement must have IMPERSONATE permissions on the target principal */  
CREATE PROCEDURE usp_ShowWaitingItems @ProductID int  
AS  
BEGIN   
   SELECT a.PurchaseOrderID, a.OrderDate, a.ShipDate  
      , b.ProductID, b.OrderQty, b.ReceivedQty  
   FROM Purchasing.PurchaseOrderHeader AS a  
      INNER JOIN Purchasing.PurchaseOrderDetail AS b  
         ON a.PurchaseOrderID = b.PurchaseOrderID  
   WHERE b.OrderQty > b.ReceivedQty  
      AND @ProductID = b.ProductID  
   ORDER BY b.ProductID ASC  
END;  
GO  
  
/* Give the employee the ability to run the procedure */  
GRANT EXECUTE   
   ON OBJECT::Purchasing.usp_ShowWaitingItems  
   TO TestEmployeeUser;  
GO   
  
/* Notice that the stored procedure is located in the Purchasing   
schema. This also demonstrates system catalogs */  
SELECT a.name AS 'Schema'  
   , b.name AS 'Object Name'  
   , b.type AS 'Object Type'  
FROM sys.schemas AS a  
   INNER JOIN sys.objects AS b  
      ON a.schema_id = b.schema_id   
WHERE b.name = 'usp_ShowWaitingItems';  
GO  
  
/* Go back to being the dbo user */  
REVERT;  
GO  
  
/*  
Section 3: Switch Context and Observe Security   
*/  
EXECUTE AS LOGIN = 'TestEmployeeUser';  
GO  
SELECT CURRENT_USER AS 'Current User Name';  
GO  
EXEC Purchasing.usp_ShowWaitingItems 952;  
GO  
  
/*   
Section 4: Clean Up Example  
*/  
REVERT;  
GO  
ALTER AUTHORIZATION   
ON SCHEMA::Purchasing TO dbo;  
GO  
DROP PROCEDURE Purchasing.usp_ShowWaitingItems;  
GO  
DROP USER TestEmployeeUser;  
GO  
DROP USER TestManagerUser;  
GO  
DROP LOGIN TestEmployeeUser;  
GO  
DROP LOGIN TestManagerUser;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="b46a1-152">См. также:</span><span class="sxs-lookup"><span data-stu-id="b46a1-152">See Also</span></span>  
 [<span data-ttu-id="b46a1-153">Центр безопасности для ядра СУБД SQL Server и Базы данных Azure SQL</span><span class="sxs-lookup"><span data-stu-id="b46a1-153">Security Center for SQL Server Database Engine and Azure SQL Database</span></span>](security/security-center-for-sql-server-database-engine-and-azure-sql-database.md)  
  
  
