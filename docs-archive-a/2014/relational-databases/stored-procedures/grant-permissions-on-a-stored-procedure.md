---
title: Предоставление разрешений на хранимую процедуру | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.technology: stored-procedures
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- stored procedures [SQL Server], permissions
ms.assetid: a7d15816-a788-4099-ad91-dc4b26618299
author: stevestein
ms.author: sstein
ms.openlocfilehash: 23ea130b9d2033128adc99413c053d66936e3ccc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664787"
---
# <a name="grant-permissions-on-a-stored-procedure"></a><span data-ttu-id="0126f-102">Предоставление разрешений на хранимую процедуру</span><span class="sxs-lookup"><span data-stu-id="0126f-102">Grant Permissions on a Stored Procedure</span></span>
  <span data-ttu-id="0126f-103">В этом разделе описывается, как предоставить разрешения на хранимую процедуру в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] , используя среду [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0126f-103">This topic describes how to grant permissions on a stored procedure in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="0126f-104">Разрешения можно предоставить существующему пользователю, роли базы данных или роли приложения в базе данных.</span><span class="sxs-lookup"><span data-stu-id="0126f-104">Permissions can be granted to an existing user, database role, or application role in the database.</span></span>  
  
 <span data-ttu-id="0126f-105">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="0126f-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="0126f-106">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="0126f-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="0126f-107">Ограничения</span><span class="sxs-lookup"><span data-stu-id="0126f-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="0126f-108">Безопасность</span><span class="sxs-lookup"><span data-stu-id="0126f-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="0126f-109">**Для предоставления разрешений на хранимую процедуру используется:**</span><span class="sxs-lookup"><span data-stu-id="0126f-109">**To grant permissions on a stored procedure, using:**</span></span>  
  
     [<span data-ttu-id="0126f-110">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="0126f-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="0126f-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="0126f-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="0126f-112">Перед началом</span><span class="sxs-lookup"><span data-stu-id="0126f-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="0126f-113">Ограничения</span><span class="sxs-lookup"><span data-stu-id="0126f-113">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="0126f-114">Нельзя использовать среду [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] для предоставления разрешений на системные процедуры или системные функции.</span><span class="sxs-lookup"><span data-stu-id="0126f-114">You cannot use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to grant permissions on system procedures or system functions.</span></span> <span data-ttu-id="0126f-115">Вместо этого используйте [Разрешения объекта GRANT](/sql/t-sql/statements/grant-object-permissions-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="0126f-115">Use [GRANT Object Permissions](/sql/t-sql/statements/grant-object-permissions-transact-sql) instead.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="0126f-116">безопасность</span><span class="sxs-lookup"><span data-stu-id="0126f-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="0126f-117">Permissions</span><span class="sxs-lookup"><span data-stu-id="0126f-117">Permissions</span></span>  
 <span data-ttu-id="0126f-118">Объект, предоставляющий разрешение (или участник, указанный параметром AS), должен иметь либо само разрешение, выданное с помощью параметра GRANT OPTION, либо разрешение более высокого уровня, которое неявно включает предоставляемое.</span><span class="sxs-lookup"><span data-stu-id="0126f-118">The grantor (or the principal specified with the AS option) must have either the permission itself with GRANT OPTION, or a higher permission that implies the permission being granted.</span></span> <span data-ttu-id="0126f-119">Необходимо разрешение ALTER на схему, которой принадлежит процедура, или разрешение CONTROL на процедуру.</span><span class="sxs-lookup"><span data-stu-id="0126f-119">Requires ALTER permission on the schema to which the procedure belongs, or CONTROL permission on the procedure.</span></span> <span data-ttu-id="0126f-120">Дополнительные сведения см. в разделе [GRANT, предоставление разрешений на объект (Transact-SQL)](/sql/t-sql/statements/grant-object-permissions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="0126f-120">For more information, see [GRANT Object Permissions &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-object-permissions-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="0126f-121">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="0126f-121">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-grant-permissions-on-a-stored-procedure"></a><span data-ttu-id="0126f-122">Предоставление разрешений на хранимую процедуру</span><span class="sxs-lookup"><span data-stu-id="0126f-122">To grant permissions on a stored procedure</span></span>  
  
1.  <span data-ttu-id="0126f-123">В обозревателе объектов подключитесь к экземпляру [!INCLUDE[ssDE](../../../includes/ssde-md.md)] и разверните его.</span><span class="sxs-lookup"><span data-stu-id="0126f-123">In Object Explorer, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="0126f-124">Последовательно разверните узел **Базы данных**, базу данных, которой принадлежит процедура, и узел **Программирование**.</span><span class="sxs-lookup"><span data-stu-id="0126f-124">Expand **Databases**, expand the database in which the procedure belongs, and then expand **Programmability**.</span></span>  
  
3.  <span data-ttu-id="0126f-125">Разверните узел **Хранимые процедуры**, щелкните правой кнопкой мыши процедуру для предоставления разрешений и выберите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="0126f-125">Expand **Stored Procedures**, right-click the procedure to grant permissions on, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="0126f-126">В пункте **Свойства хранимой процедуры**выберите страницу **Разрешения** .</span><span class="sxs-lookup"><span data-stu-id="0126f-126">From **Stored Procedure Properties**, select the **Permissions** page.</span></span>  
  
5.  <span data-ttu-id="0126f-127">Для предоставления разрешений пользователю, роли базы данных или роли приложения нажмите кнопку **Поиск**.</span><span class="sxs-lookup"><span data-stu-id="0126f-127">To grant permissions to a user, database role, or application role, click **Search**.</span></span>  
  
6.  <span data-ttu-id="0126f-128">В пункте **Выбрать пользователей или ролей**нажмите **Типы объектов** для необходимого добавления или исключения пользователей и ролей.</span><span class="sxs-lookup"><span data-stu-id="0126f-128">In **Select Users or Roles**, click **Object Types** to add or clear the users and roles you want.</span></span>  
  
7.  <span data-ttu-id="0126f-129">Нажмите кнопку **Обзор** , чтобы показать список пользователей или ролей.</span><span class="sxs-lookup"><span data-stu-id="0126f-129">Click **Browse** to display the list of users or roles.</span></span> <span data-ttu-id="0126f-130">Выберите пользователей или роли, которым следует предоставить разрешения.</span><span class="sxs-lookup"><span data-stu-id="0126f-130">Select the users or roles to whom permissions should be granted.</span></span>  
  
8.  <span data-ttu-id="0126f-131">В сетке **Явно указанные разрешения** выберите разрешения для предоставления определенному пользователю или роли.</span><span class="sxs-lookup"><span data-stu-id="0126f-131">In the **Explicit Permissions** grid, select the permissions to grant to the specified user or role.</span></span> <span data-ttu-id="0126f-132">Описание разрешений см. в разделе [Разрешения (компонент Database Engine)](../security/permissions-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="0126f-132">For a description of the permissions, see [Permissions &#40;Database Engine&#41;](../security/permissions-database-engine.md).</span></span>  
  
 <span data-ttu-id="0126f-133">Выбор **Предоставить** означает, что получателю разрешения предоставляется указанное разрешение.</span><span class="sxs-lookup"><span data-stu-id="0126f-133">Selecting **Grant** indicates the grantee will be given the specified permission.</span></span> <span data-ttu-id="0126f-134">Выбор параметра **Право передачи** означает, что получатель разрешения имеет возможность предоставить указанное разрешение другим участникам.</span><span class="sxs-lookup"><span data-stu-id="0126f-134">Selecting **Grant With** indicates that the grantee will also be able to grant the specified permission to other principals.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="0126f-135">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="0126f-135">Using Transact-SQL</span></span>  
  
#### <a name="to-grant-permissions-on-a-stored-procedure"></a><span data-ttu-id="0126f-136">Предоставление разрешений на хранимую процедуру</span><span class="sxs-lookup"><span data-stu-id="0126f-136">To grant permissions on a stored procedure</span></span>  
  
1.  <span data-ttu-id="0126f-137">Установите соединение с компонентом [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0126f-137">Connect to the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="0126f-138">На панели «Стандартная» нажмите **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="0126f-138">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="0126f-139">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="0126f-139">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="0126f-140">В этом примере предоставляется разрешение `EXECUTE` на хранимую процедуру `HumanResources.uspUpdateEmployeeHireInfo` роли приложения с именем `Recruiting11`.</span><span class="sxs-lookup"><span data-stu-id="0126f-140">This example grants `EXECUTE` permission on the stored procedure `HumanResources.uspUpdateEmployeeHireInfo` to an application role named `Recruiting11`.</span></span>  
  
```sql  
USE AdventureWorks2012;   
GRANT EXECUTE ON OBJECT::HumanResources.uspUpdateEmployeeHireInfo  
    TO Recruiting11;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="0126f-141">См. также:</span><span class="sxs-lookup"><span data-stu-id="0126f-141">See Also</span></span>  
 <span data-ttu-id="0126f-142">[sys.fn_builtin_permissions (Transact-SQL)](/sql/relational-databases/system-functions/sys-fn-builtin-permissions-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="0126f-142">[sys.fn_builtin_permissions &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-builtin-permissions-transact-sql) </span></span>  
 <span data-ttu-id="0126f-143">[GRANT, предоставление разрешений на объект (Transact-SQL)](/sql/t-sql/statements/grant-object-permissions-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="0126f-143">[GRANT Object Permissions &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-object-permissions-transact-sql) </span></span>  
 <span data-ttu-id="0126f-144">[Создание хранимой процедуры](../stored-procedures/create-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="0126f-144">[Create a Stored Procedure](../stored-procedures/create-a-stored-procedure.md) </span></span>  
 <span data-ttu-id="0126f-145">[Изменение хранимой процедуры](modify-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="0126f-145">[Modify a Stored Procedure](modify-a-stored-procedure.md) </span></span>  
 <span data-ttu-id="0126f-146">[Удаление хранимой процедуры](../stored-procedures/delete-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="0126f-146">[Delete a Stored Procedure](../stored-procedures/delete-a-stored-procedure.md) </span></span>  
 [<span data-ttu-id="0126f-147">Изменение имени хранимой процедуры</span><span class="sxs-lookup"><span data-stu-id="0126f-147">Rename a Stored Procedure</span></span>](rename-a-stored-procedure.md)  
  
  
