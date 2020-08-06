---
title: Просмотр определения хранимой процедуры | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.technology: stored-procedures
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- stored procedures [SQL Server], viewing
- definition of stored procedure
- viewing stored procedures
- displaying stored procedures
ms.assetid: 93318587-a0c5-4788-946f-3b5dc8372ea9
author: stevestein
ms.author: sstein
ms.openlocfilehash: 4da455d38f984b08ee1f396f26cd4cc85411be92
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664097"
---
# <a name="view-the-definition-of-a-stored-procedure"></a><span data-ttu-id="a940f-102">Просмотр определения хранимой процедуры</span><span class="sxs-lookup"><span data-stu-id="a940f-102">View the Definition of a Stored Procedure</span></span>
    
##  <a name="you-can-view-the-definition-of-a-stored-procedure-in-ssmanstudiofull-using-object-explorer-menu-options-or-in-the-query-editor-using-tsql-this-topic-describes-how-to-view-the-definition-of-procedure-in-object-explorer-and-by-using-a-system-stored-procedure-system-function-and-object-catalog-view-in-the-query-editor"></a><a name="Top"></a> <span data-ttu-id="a940f-103">Определение хранимой процедуры можно просмотреть в [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , воспользовавшись параметрами меню обозревателя объектов, а также с помощью редактора запросов и языка [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a940f-103">You can view the definition of a stored procedure in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] using Object Explorer menu options or in the Query Editor using [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="a940f-104">В данном разделе описывается процесс просмотра определения хранимой процедуры в обозревателе объектов и с помощью хранимой в системе процедуры, системной функции и в представлении каталога объектов в редакторе запросов.</span><span class="sxs-lookup"><span data-stu-id="a940f-104">This topic describes how to view the definition of procedure in Object Explorer and by using a system stored procedure, system function, and object catalog view in the Query Editor.</span></span>  
  
-   <span data-ttu-id="a940f-105">**Перед началом работы**  [Безопасность](#Security)</span><span class="sxs-lookup"><span data-stu-id="a940f-105">**Before you begin:**  [Security](#Security)</span></span>  
  
-   <span data-ttu-id="a940f-106">**Просмотр определения хранимой процедуры с помощью**  [среды SQL Server Management Studio](#SSMSProcedure), [Transact-SQL](#TsqlProcedure)</span><span class="sxs-lookup"><span data-stu-id="a940f-106">**To view the definition of a procedure, using:**  [SQL Server Management Studio](#SSMSProcedure), [Transact-SQL](#TsqlProcedure)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="a940f-107">Перед началом</span><span class="sxs-lookup"><span data-stu-id="a940f-107">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="a940f-108">безопасность</span><span class="sxs-lookup"><span data-stu-id="a940f-108">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="a940f-109">Permissions</span><span class="sxs-lookup"><span data-stu-id="a940f-109">Permissions</span></span>  
 <span data-ttu-id="a940f-110">Системная хранимая процедура: `sp_helptext`</span><span class="sxs-lookup"><span data-stu-id="a940f-110">System Stored Procedure: `sp_helptext`</span></span>  
 <span data-ttu-id="a940f-111">Необходимо быть членом роли **public**.</span><span class="sxs-lookup"><span data-stu-id="a940f-111">Requires membership in the **public** role.</span></span> <span data-ttu-id="a940f-112">Определения системных объектов видимы для всех.</span><span class="sxs-lookup"><span data-stu-id="a940f-112">System object definitions are publicly visible.</span></span> <span data-ttu-id="a940f-113">Определения пользовательских объектов видимы владельцу объекта или получателям, которым предоставлено одно из следующих разрешений: ALTER, CONTROL, TAKE OWNERSHIP или VIEW DEFINITION.</span><span class="sxs-lookup"><span data-stu-id="a940f-113">The definition of user objects is visible to the object owner or grantees that have any one of the following permissions: ALTER, CONTROL, TAKE OWNERSHIP, or VIEW DEFINITION.</span></span>  
  
 <span data-ttu-id="a940f-114">Системная функция: `OBJECT_DEFINITION`</span><span class="sxs-lookup"><span data-stu-id="a940f-114">System Function: `OBJECT_DEFINITION`</span></span>  
 <span data-ttu-id="a940f-115">Определения системных объектов видимы для всех.</span><span class="sxs-lookup"><span data-stu-id="a940f-115">System object definitions are publicly visible.</span></span> <span data-ttu-id="a940f-116">Определения пользовательских объектов видимы владельцу объекта или получателям, которым предоставлено одно из следующих разрешений: ALTER, CONTROL, TAKE OWNERSHIP или VIEW DEFINITION.</span><span class="sxs-lookup"><span data-stu-id="a940f-116">The definition of user objects is visible to the object owner or grantees that have any one of the following permissions: ALTER, CONTROL, TAKE OWNERSHIP, or VIEW DEFINITION.</span></span> <span data-ttu-id="a940f-117">Эти разрешения неявно предоставляются членам предопределенных ролей базы данных **db_owner**, **db_ddladmin**и **db_securityadmin** .</span><span class="sxs-lookup"><span data-stu-id="a940f-117">These permissions are implicitly held by members of the **db_owner**, **db_ddladmin**, and **db_securityadmin** fixed database roles.</span></span>  
  
 <span data-ttu-id="a940f-118">Представление каталога объектов: `sys.sql_modules`</span><span class="sxs-lookup"><span data-stu-id="a940f-118">Object Catalog View: `sys.sql_modules`</span></span>  
 <span data-ttu-id="a940f-119">Видимость метаданных в представлениях каталогов ограничивается защищаемыми объектами, которыми пользователь владеет или на которые ему были предоставлены разрешения.</span><span class="sxs-lookup"><span data-stu-id="a940f-119">The visibility of the metadata in catalog views is limited to securables that a user either owns or on which the user has been granted some permission.</span></span> <span data-ttu-id="a940f-120">Дополнительные сведения см. в разделе [Metadata Visibility Configuration](../security/metadata-visibility-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="a940f-120">For more information, see [Metadata Visibility Configuration](../security/metadata-visibility-configuration.md).</span></span>  
  
##  <a name="how-to-view-the-definition-of-a-stored-procedure"></a><a name="Procedures"></a> <span data-ttu-id="a940f-121">Просмотр определения хранимой процедуры</span><span class="sxs-lookup"><span data-stu-id="a940f-121">How to View the Definition of a Stored Procedure</span></span>  
 <span data-ttu-id="a940f-122">Можно использовать один из следующих способов:</span><span class="sxs-lookup"><span data-stu-id="a940f-122">You can use one of the following:</span></span>  
  
-   [<span data-ttu-id="a940f-123">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a940f-123">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
-   [<span data-ttu-id="a940f-124">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a940f-124">Transact-SQL</span></span>](#TsqlProcedure)  
  
###  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="a940f-125">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a940f-125">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="a940f-126">**Просмотр определения процедуры средствами обозревателя объектов**</span><span class="sxs-lookup"><span data-stu-id="a940f-126">**To view the definition a procedure in Object Explorer**</span></span>  
  
1.  <span data-ttu-id="a940f-127">В обозревателе объектов подключитесь к экземпляру [!INCLUDE[ssDE](../../includes/ssde-md.md)] и разверните его.</span><span class="sxs-lookup"><span data-stu-id="a940f-127">In Object Explorer, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="a940f-128">Последовательно разверните узел **Базы данных**, базу данных, которой принадлежит процедура, и узел **Программирование**.</span><span class="sxs-lookup"><span data-stu-id="a940f-128">Expand **Databases**, expand the database in which the procedure belongs, and then expand **Programmability**.</span></span>  
  
3.  <span data-ttu-id="a940f-129">Разверните пункт **Хранимые процедуры**, щелкните правой кнопкой процедуру, после чего щелкните пункт **Создать скрипт для хранимой процедуры как**, после чего щелкните один из следующих пунктов: **Создать в**, **Изменить на** или **Удалить и создать в**.</span><span class="sxs-lookup"><span data-stu-id="a940f-129">Expand **Stored Procedures**, right-click the procedure and then click **Script Stored Procedure as**, and then click one of the following: **Create To**, **Alter To**, or **Drop and Create To**.</span></span>  
  
4.  <span data-ttu-id="a940f-130">Выберите **New Query Editor Window** (Окно редактирования нового запроса).</span><span class="sxs-lookup"><span data-stu-id="a940f-130">Select **New Query Editor Window**.</span></span> <span data-ttu-id="a940f-131">При этом отобразится определение процедуры.</span><span class="sxs-lookup"><span data-stu-id="a940f-131">This will display the procedure definition.</span></span>  
  
###  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="a940f-132">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a940f-132">Using Transact-SQL</span></span>  
 <span data-ttu-id="a940f-133">**Просмотр определения процедуры в редакторе запросов**</span><span class="sxs-lookup"><span data-stu-id="a940f-133">**To view the definition of a procedure in Query Editor**</span></span>  
  
 <span data-ttu-id="a940f-134">Системная хранимая процедура: `sp_helptext`</span><span class="sxs-lookup"><span data-stu-id="a940f-134">System Stored Procedure: `sp_helptext`</span></span>  
 1.  <span data-ttu-id="a940f-135">В обозревателе объектов установите соединение с экземпляром компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a940f-135">In Object Explorer, connect to an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="a940f-136">На панели инструментов нажмите кнопку **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="a940f-136">On the toolbar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="a940f-137">В окне запроса введите следующую инструкцию, которая использует системную хранимую процедуру `sp_helptext`.</span><span class="sxs-lookup"><span data-stu-id="a940f-137">In the query window, enter the following statement that uses the `sp_helptext` system stored procedure.</span></span> <span data-ttu-id="a940f-138">Измените имя базы данных и имя хранимой процедуры для ссылки на нужную базу данных и хранимую процедуру.</span><span class="sxs-lookup"><span data-stu-id="a940f-138">Change the database name and stored procedure name to reference the database and stored procedure that you want.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    EXEC sp_helptext N'AdventureWorks2012.dbo.uspLogError';  
    ```  
  
 <span data-ttu-id="a940f-139">Системная функция: `OBJECT_DEFINITION`</span><span class="sxs-lookup"><span data-stu-id="a940f-139">System Function: `OBJECT_DEFINITION`</span></span>  
 1.  <span data-ttu-id="a940f-140">В обозревателе объектов установите соединение с экземпляром компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a940f-140">In Object Explorer, connect to an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="a940f-141">На панели инструментов нажмите кнопку **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="a940f-141">On the toolbar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="a940f-142">В окне запроса введите следующие инструкции, которые используют системную функцию `OBJECT_DEFINITION`.</span><span class="sxs-lookup"><span data-stu-id="a940f-142">In the query window, enter the following statements that use the `OBJECT_DEFINITION` system function.</span></span> <span data-ttu-id="a940f-143">Измените имя базы данных и имя хранимой процедуры для ссылки на нужную базу данных и хранимую процедуру.</span><span class="sxs-lookup"><span data-stu-id="a940f-143">Change the database name and stored procedure name to reference the database and stored procedure that you want.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SELECT OBJECT_DEFINITION (OBJECT_ID(N'AdventureWorks2012.dbo.uspLogError'));  
    ```  
  
 <span data-ttu-id="a940f-144">Представление каталога объектов: `sys.sql_modules`</span><span class="sxs-lookup"><span data-stu-id="a940f-144">Object Catalog View: `sys.sql_modules`</span></span>  
 1.  <span data-ttu-id="a940f-145">В обозревателе объектов установите соединение с экземпляром компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a940f-145">In Object Explorer, connect to an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="a940f-146">На панели инструментов нажмите кнопку **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="a940f-146">On the toolbar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="a940f-147">В окне запроса введите следующие инструкции, которые используют представление каталогов `sys.sql_modules`.</span><span class="sxs-lookup"><span data-stu-id="a940f-147">In the query window, enter the following statements that use the `sys.sql_modules` catalog view.</span></span> <span data-ttu-id="a940f-148">Измените имя базы данных и имя хранимой процедуры для ссылки на нужную базу данных и хранимую процедуру.</span><span class="sxs-lookup"><span data-stu-id="a940f-148">Change the database name and stored procedure name to reference the database and stored procedure that you want.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SELECT definition  
    FROM sys.sql_modules  
    WHERE object_id = (OBJECT_ID(N'AdventureWorks2012.dbo.uspLogError'));  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="a940f-149">См. также:</span><span class="sxs-lookup"><span data-stu-id="a940f-149">See Also</span></span>  
 <span data-ttu-id="a940f-150">[Создание хранимой процедуры](create-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="a940f-150">[Create a Stored Procedure](create-a-stored-procedure.md) </span></span>  
 <span data-ttu-id="a940f-151">[Изменение хранимой процедуры](modify-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="a940f-151">[Modify a Stored Procedure](modify-a-stored-procedure.md) </span></span>  
 <span data-ttu-id="a940f-152">[Удаление хранимой процедуры](delete-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="a940f-152">[Delete a Stored Procedure](delete-a-stored-procedure.md) </span></span>  
 <span data-ttu-id="a940f-153">[Изменение имени хранимой процедуры](rename-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="a940f-153">[Rename a Stored Procedure](rename-a-stored-procedure.md) </span></span>  
 <span data-ttu-id="a940f-154">[OBJECT_DEFINITION (Transact-SQL)](/sql/t-sql/functions/object-definition-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a940f-154">[OBJECT_DEFINITION &#40;Transact-SQL&#41;](/sql/t-sql/functions/object-definition-transact-sql) </span></span>  
 <span data-ttu-id="a940f-155">[sys.sql_modules (Transact-SQL)](/sql/relational-databases/system-catalog-views/sys-sql-modules-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a940f-155">[sys.sql_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-modules-transact-sql) </span></span>  
 <span data-ttu-id="a940f-156">[sp_helptext (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-helptext-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a940f-156">[sp_helptext &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helptext-transact-sql) </span></span>  
 [<span data-ttu-id="a940f-157">OBJECT_ID (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="a940f-157">OBJECT_ID &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/object-id-transact-sql)  
  
  
