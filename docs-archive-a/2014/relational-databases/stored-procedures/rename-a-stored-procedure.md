---
title: Переименование хранимой процедуры | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.technology: stored-procedures
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- stored procedures [SQL Server], renaming
- renaming stored procedures
ms.assetid: 5d2e4c68-7e0b-4405-8919-f5b203e46770
author: stevestein
ms.author: sstein
ms.openlocfilehash: 02e1acb528a32ef242e160e0ce5dd0267237c876
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669372"
---
# <a name="rename-a-stored-procedure"></a><span data-ttu-id="6dd52-102">Изменение имени хранимой процедуры</span><span class="sxs-lookup"><span data-stu-id="6dd52-102">Rename a Stored Procedure</span></span>
  <span data-ttu-id="6dd52-103">В этом разделе описывается, как переименовать хранимую процедуру [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] при помощи среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6dd52-103">This topic describes how to rename a stored procedure in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="6dd52-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="6dd52-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="6dd52-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="6dd52-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="6dd52-106">Ограничения</span><span class="sxs-lookup"><span data-stu-id="6dd52-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="6dd52-107">Безопасность</span><span class="sxs-lookup"><span data-stu-id="6dd52-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="6dd52-108">**Для переименования хранимой процедуры используется:**</span><span class="sxs-lookup"><span data-stu-id="6dd52-108">**To rename a stored procedure, using:**</span></span>  
  
     [<span data-ttu-id="6dd52-109">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6dd52-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="6dd52-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="6dd52-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="6dd52-111">Перед началом</span><span class="sxs-lookup"><span data-stu-id="6dd52-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="6dd52-112">Ограничения</span><span class="sxs-lookup"><span data-stu-id="6dd52-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="6dd52-113">Имена процедур должны соответствовать правилам для [идентификаторов](../databases/database-identifiers.md).</span><span class="sxs-lookup"><span data-stu-id="6dd52-113">Procedure names must comply with the rules for [identifiers](../databases/database-identifiers.md).</span></span>  
  
-   <span data-ttu-id="6dd52-114">При переименовании хранимой процедуры не изменяется имя соответствующего объекта в столбце определения представления каталога **sys.sql_modules** .</span><span class="sxs-lookup"><span data-stu-id="6dd52-114">Renaming a stored procedure will not change the name of the corresponding object name in the definition column of the **sys.sql_modules** catalog view.</span></span> <span data-ttu-id="6dd52-115">Поэтому не рекомендуется переименовывать объекты этого типа.</span><span class="sxs-lookup"><span data-stu-id="6dd52-115">Therefore, we recommend that you do not rename this object type.</span></span> <span data-ttu-id="6dd52-116">Лучше удалить хранимую процедуру и создать ее повторно с новым именем.</span><span class="sxs-lookup"><span data-stu-id="6dd52-116">Instead, drop and re-create the stored procedure with its new name.</span></span>  
  
-   <span data-ttu-id="6dd52-117">Изменение имени или определения процедуры может привести к тому, что все зависящие от нее объекты при выполнении будут возвращать ошибку, если они не будут обновлены в соответствии с внесенными в процедуру изменениями.</span><span class="sxs-lookup"><span data-stu-id="6dd52-117">Changing the name or definition of a procedure can cause dependent objects to fail when the objects are not updated to reflect the changes that have been made to the procedure.</span></span> <span data-ttu-id="6dd52-118">Дополнительные сведения см. в разделе [Просмотр зависимостей хранимой процедуры](view-the-dependencies-of-a-stored-procedure.md).</span><span class="sxs-lookup"><span data-stu-id="6dd52-118">For more information, see [View the Dependencies of a Stored Procedure](view-the-dependencies-of-a-stored-procedure.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="6dd52-119">безопасность</span><span class="sxs-lookup"><span data-stu-id="6dd52-119">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="6dd52-120">Permissions</span><span class="sxs-lookup"><span data-stu-id="6dd52-120">Permissions</span></span>  
 <span data-ttu-id="6dd52-121">CREATE PROCEDURE</span><span class="sxs-lookup"><span data-stu-id="6dd52-121">CREATE PROCEDURE</span></span>  
 <span data-ttu-id="6dd52-122">Требуется разрешение CREATE PROCEDURE на базу данных и разрешение ALTER на схему, в которой создается процедура, либо членство в предопределенной роли базы данных **db_ddladmin**.</span><span class="sxs-lookup"><span data-stu-id="6dd52-122">Requires CREATE PROCEDURE permission in the database and ALTER permission on the schema in which the procedure is being created, or requires membership in the **db_ddladmin** fixed database role.</span></span>  
  
 <span data-ttu-id="6dd52-123">ALTER PROCEDURE</span><span class="sxs-lookup"><span data-stu-id="6dd52-123">ALTER PROCEDURE</span></span>  
 <span data-ttu-id="6dd52-124">Требуется разрешение ALTER на процедуру или членство в предопределенной роли базы данных **db_ddladmin** .</span><span class="sxs-lookup"><span data-stu-id="6dd52-124">Requires ALTER permission on the procedure or requires membership in the **db_ddladmin** fixed database role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="6dd52-125">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6dd52-125">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-rename-a-stored-procedure"></a><span data-ttu-id="6dd52-126">Изменение имени хранимой процедуры</span><span class="sxs-lookup"><span data-stu-id="6dd52-126">To rename a stored procedure</span></span>  
  
1.  <span data-ttu-id="6dd52-127">В обозревателе объектов подключитесь к экземпляру [!INCLUDE[ssDE](../../includes/ssde-md.md)] и разверните его.</span><span class="sxs-lookup"><span data-stu-id="6dd52-127">In Object Explorer, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="6dd52-128">Последовательно разверните узел **Базы данных**, базу данных, которой принадлежит процедура, и узел **Программирование**.</span><span class="sxs-lookup"><span data-stu-id="6dd52-128">Expand **Databases**, expand the database in which the procedure belongs, and then expand **Programmability**.</span></span>  
  
3.  <span data-ttu-id="6dd52-129">[Определите зависимости хранимой процедуры](view-the-dependencies-of-a-stored-procedure.md).</span><span class="sxs-lookup"><span data-stu-id="6dd52-129">[Determine the dependencies of the stored procedure](view-the-dependencies-of-a-stored-procedure.md).</span></span>  
  
4.  <span data-ttu-id="6dd52-130">Разверните узел **Хранимые процедуры**, щелкните процедуру правой кнопкой мыши и выберите команду **Переименовать**.</span><span class="sxs-lookup"><span data-stu-id="6dd52-130">Expand **Stored Procedures**, right-click the procedure to rename, and then click **Rename**.</span></span>  
  
5.  <span data-ttu-id="6dd52-131">Измените имя хранимой процедуры.</span><span class="sxs-lookup"><span data-stu-id="6dd52-131">Modify the procedure name.</span></span>  
  
6.  <span data-ttu-id="6dd52-132">Измените имя процедуры во всех зависимых от нее объектах и скриптах.</span><span class="sxs-lookup"><span data-stu-id="6dd52-132">Modify the procedure name referenced in any dependent objects or scripts.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="6dd52-133">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="6dd52-133">Using Transact-SQL</span></span>  
  
#### <a name="to-rename-a-stored-procedure"></a><span data-ttu-id="6dd52-134">Изменение имени хранимой процедуры</span><span class="sxs-lookup"><span data-stu-id="6dd52-134">To rename a stored procedure</span></span>  
  
1.  <span data-ttu-id="6dd52-135">Установите соединение с компонентом [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6dd52-135">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="6dd52-136">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="6dd52-136">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="6dd52-137">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="6dd52-137">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="6dd52-138">В этом примере показано, как переименовать процедуру путем ее удаления и повторного создания с новым именем.</span><span class="sxs-lookup"><span data-stu-id="6dd52-138">This example shows how to rename a procedure by dropping the procedure and re-creating the procedure with a new name.</span></span> <span data-ttu-id="6dd52-139">В первом примере создается хранимая процедура `'HumanResources.uspGetAllEmployeesTest`.</span><span class="sxs-lookup"><span data-stu-id="6dd52-139">The first example creates the stored procedure `'HumanResources.uspGetAllEmployeesTest`.</span></span> <span data-ttu-id="6dd52-140">Во втором примере имя хранимой процедуры меняется на `HumanResources.uspEveryEmployeeTest`.</span><span class="sxs-lookup"><span data-stu-id="6dd52-140">The second example renames the stored procedure to `HumanResources.uspEveryEmployeeTest`.</span></span>  
  
```sql  
--Create the stored procedure.  
USE AdventureWorks2012;  
GO  
IF OBJECT_ID ( 'HumanResources.uspGetAllEmployeesTest', 'P' ) IS NOT NULL   
    DROP PROCEDURE HumanResources.uspGetAllEmployeesTest;  
GO  
CREATE PROCEDURE HumanResources.uspGetAllEmployeesTest  
AS  
    SET NOCOUNT ON;  
    SELECT LastName, FirstName, Department  
    FROM HumanResources.vEmployeeDepartmentHistory;  
GO  
  
--Rename the stored procedure.  
USE AdventureWorks2012;  
GO  
IF OBJECT_ID ( 'HumanResources.uspGetAllEmployeesTest', 'P' ) IS NOT NULL   
    DROP PROCEDURE HumanResources.uspGetAllEmployeesTest;  
GO  
CREATE PROCEDURE HumanResources.uspEveryEmployeeTest  
AS  
    SET NOCOUNT ON;  
    SELECT LastName, FirstName, Department  
    FROM HumanResources.vEmployeeDepartmentHistory;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="6dd52-141">См. также:</span><span class="sxs-lookup"><span data-stu-id="6dd52-141">See Also</span></span>  
 <span data-ttu-id="6dd52-142">[ALTER PROCEDURE (Transact-SQL)](/sql/t-sql/statements/alter-procedure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="6dd52-142">[ALTER PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-procedure-transact-sql) </span></span>  
 <span data-ttu-id="6dd52-143">[CREATE PROCEDURE (Transact-SQL)](/sql/t-sql/statements/create-procedure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="6dd52-143">[CREATE PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-procedure-transact-sql) </span></span>  
 <span data-ttu-id="6dd52-144">[Создание хранимой процедуры](../stored-procedures/create-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="6dd52-144">[Create a Stored Procedure](../stored-procedures/create-a-stored-procedure.md) </span></span>  
 <span data-ttu-id="6dd52-145">[Изменение хранимой процедуры](../stored-procedures/modify-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="6dd52-145">[Modify a Stored Procedure](../stored-procedures/modify-a-stored-procedure.md) </span></span>  
 <span data-ttu-id="6dd52-146">[Удаление хранимой процедуры](../stored-procedures/delete-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="6dd52-146">[Delete a Stored Procedure](../stored-procedures/delete-a-stored-procedure.md) </span></span>  
 <span data-ttu-id="6dd52-147">[Просмотр определения хранимой процедуры](view-the-definition-of-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="6dd52-147">[View the Definition of a Stored Procedure](view-the-definition-of-a-stored-procedure.md) </span></span>  
 [<span data-ttu-id="6dd52-148">Просмотр зависимостей хранимой процедуры</span><span class="sxs-lookup"><span data-stu-id="6dd52-148">View the Dependencies of a Stored Procedure</span></span>](view-the-dependencies-of-a-stored-procedure.md)  
  
  
