---
title: Создание хранимой процедуры | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.technology: stored-procedures
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- new stored procedures
- stored procedures [SQL Server], creating
- creating stored procedures
ms.assetid: 76e8a6ba-1381-4620-b356-4311e1331ca7
author: stevestein
ms.author: sstein
ms.openlocfilehash: f6781840e6a6c84773f40a6cd0557ccb79b676eb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667618"
---
# <a name="create-a-stored-procedure"></a><span data-ttu-id="8e81b-102">Создание хранимой процедуры</span><span class="sxs-lookup"><span data-stu-id="8e81b-102">Create a Stored Procedure</span></span>
  <span data-ttu-id="8e81b-103">В этом разделе описывается, как можно создать хранимую процедуру [!INCLUDE[tsql](../../includes/tsql-md.md)] в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] с использованием инструкции [!INCLUDE[tsql](../../includes/tsql-md.md)] CREATE PROCEDURE.</span><span class="sxs-lookup"><span data-stu-id="8e81b-103">This topic describes how to create a [!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedure by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] and by using the [!INCLUDE[tsql](../../includes/tsql-md.md)] CREATE PROCEDURE statement.</span></span>  
  
##  <a name="Top"></a>   
-   <span data-ttu-id="8e81b-104">**Перед началом работы**  [Разрешения](#Permissions)</span><span class="sxs-lookup"><span data-stu-id="8e81b-104">**Before you begin:**  [Permissions](#Permissions)</span></span>  
  
-   <span data-ttu-id="8e81b-105">**Создание процедуры с использованием:**  [среды SQL Server Management Studio](#SSMSProcedure), [Transact-SQL](#TsqlProcedure)</span><span class="sxs-lookup"><span data-stu-id="8e81b-105">**To create a procedure, using:**  [SQL Server Management Studio](#SSMSProcedure), [Transact-SQL](#TsqlProcedure)</span></span>  
  
##  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="8e81b-106">Permissions</span><span class="sxs-lookup"><span data-stu-id="8e81b-106">Permissions</span></span>  
 <span data-ttu-id="8e81b-107">Для выполнения этой инструкции требуется разрешение CREATE PROCEDURE в отношении базы данных и разрешение ALTER в отношении схемы, в которой создается процедура.</span><span class="sxs-lookup"><span data-stu-id="8e81b-107">Requires CREATE PROCEDURE permission in the database and ALTER permission on the schema in which the procedure is being created.</span></span>  
  
##  <a name="how-to-create-a-stored-procedure"></a><a name="Procedures"></a> <span data-ttu-id="8e81b-108">Создание хранимой процедуры</span><span class="sxs-lookup"><span data-stu-id="8e81b-108">How to Create a Stored Procedure</span></span>  
 <span data-ttu-id="8e81b-109">Можно использовать один из следующих способов:</span><span class="sxs-lookup"><span data-stu-id="8e81b-109">You can use one of the following:</span></span>  
  
-   [<span data-ttu-id="8e81b-110">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8e81b-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
-   [<span data-ttu-id="8e81b-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8e81b-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
###  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="8e81b-112">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8e81b-112">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="8e81b-113">**Создание процедуры в обозревателе объектов**</span><span class="sxs-lookup"><span data-stu-id="8e81b-113">**To create a procedure in Object Explorer**</span></span>  
  
1.  <span data-ttu-id="8e81b-114">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] и разверните его.</span><span class="sxs-lookup"><span data-stu-id="8e81b-114">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="8e81b-115">Последовательно разверните узел **Базы данных**, базу данных [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] и узел **Программирование**.</span><span class="sxs-lookup"><span data-stu-id="8e81b-115">Expand **Databases**, expand the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database, and then expand **Programmability**.</span></span>  
  
3.  <span data-ttu-id="8e81b-116">Щелкните правой кнопкой мыши элемент **Хранимые процедуры**и выберите пункт **Создать хранимую процедуру**.</span><span class="sxs-lookup"><span data-stu-id="8e81b-116">Right-click **Stored Procedures**, and then click **New Stored Procedure**.</span></span>  
  
4.  <span data-ttu-id="8e81b-117">В меню **Запрос** выберите пункт **Указать значения для параметров шаблона**.</span><span class="sxs-lookup"><span data-stu-id="8e81b-117">On the **Query** menu, click **Specify Values for Template Parameters**.</span></span>  
  
5.  <span data-ttu-id="8e81b-118">В диалоговом окне **Задание значений для параметров шаблона** введите для показанных параметров следующие значения.</span><span class="sxs-lookup"><span data-stu-id="8e81b-118">In the **Specify Values for Template Parameters** dialog box, enter the following values for the parameters shown.</span></span>  
  
    |<span data-ttu-id="8e81b-119">Параметр</span><span class="sxs-lookup"><span data-stu-id="8e81b-119">Parameter</span></span>|<span data-ttu-id="8e81b-120">Значение</span><span class="sxs-lookup"><span data-stu-id="8e81b-120">Value</span></span>|  
    |---------------|-----------|  
    |<span data-ttu-id="8e81b-121">Автор</span><span class="sxs-lookup"><span data-stu-id="8e81b-121">Author</span></span>|<span data-ttu-id="8e81b-122">*Ваше имя*</span><span class="sxs-lookup"><span data-stu-id="8e81b-122">*Your name*</span></span>|  
    |<span data-ttu-id="8e81b-123">Дата создания</span><span class="sxs-lookup"><span data-stu-id="8e81b-123">Create Date</span></span>|<span data-ttu-id="8e81b-124">*Сегодняшняя дата*</span><span class="sxs-lookup"><span data-stu-id="8e81b-124">*Today's date*</span></span>|  
    |<span data-ttu-id="8e81b-125">Описание</span><span class="sxs-lookup"><span data-stu-id="8e81b-125">Description</span></span>|<span data-ttu-id="8e81b-126">Возвращает данные о сотрудниках.</span><span class="sxs-lookup"><span data-stu-id="8e81b-126">Returns employee data.</span></span>|  
    |<span data-ttu-id="8e81b-127">Procedure_name</span><span class="sxs-lookup"><span data-stu-id="8e81b-127">Procedure_name</span></span>|<span data-ttu-id="8e81b-128">HumanResources.uspGetEmployeesTest</span><span class="sxs-lookup"><span data-stu-id="8e81b-128">HumanResources.uspGetEmployeesTest</span></span>|  
    |@Param1|@LastName|  
    |@Datatype_For_Param1|<span data-ttu-id="8e81b-129">`nvarchar`(50)</span><span class="sxs-lookup"><span data-stu-id="8e81b-129">`nvarchar`(50)</span></span>|  
    |<span data-ttu-id="8e81b-130">Default_Value_For_Param1</span><span class="sxs-lookup"><span data-stu-id="8e81b-130">Default_Value_For_Param1</span></span>|<span data-ttu-id="8e81b-131">NULL</span><span class="sxs-lookup"><span data-stu-id="8e81b-131">NULL</span></span>|  
    |@Param2|@FirstName|  
    |@Datatype_For_Param2|<span data-ttu-id="8e81b-132">`nvarchar`(50)</span><span class="sxs-lookup"><span data-stu-id="8e81b-132">`nvarchar`(50)</span></span>|  
    |<span data-ttu-id="8e81b-133">Default_Value_For_Param2</span><span class="sxs-lookup"><span data-stu-id="8e81b-133">Default_Value_For_Param2</span></span>|<span data-ttu-id="8e81b-134">NULL</span><span class="sxs-lookup"><span data-stu-id="8e81b-134">NULL</span></span>|  
  
6.  <span data-ttu-id="8e81b-135">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="8e81b-135">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="8e81b-136">В **редакторе запросов**замените инструкцию SELECT следующей инструкцией:</span><span class="sxs-lookup"><span data-stu-id="8e81b-136">In the **Query Editor**, replace the SELECT statement with the following statement:</span></span>  
  
    ```sql  
    SELECT FirstName, LastName, Department  
    FROM HumanResources.vEmployeeDepartmentHistory  
    WHERE FirstName = @FirstName AND LastName = @LastName  
        AND EndDate IS NULL;  
    ```  
  
8.  <span data-ttu-id="8e81b-137">Для проверки синтаксиса выберите пункт **Выполнить анализ** в меню **Запрос**.</span><span class="sxs-lookup"><span data-stu-id="8e81b-137">To test the syntax, on the **Query** menu, click **Parse**.</span></span> <span data-ttu-id="8e81b-138">Если возвращается сообщение об ошибке, сравните инструкции с приведенными выше и при необходимости внесите исправления.</span><span class="sxs-lookup"><span data-stu-id="8e81b-138">If an error message is returned, compare the statements with the information above and correct as needed.</span></span>  
  
9. <span data-ttu-id="8e81b-139">Чтобы создать процедуру, в меню **Запрос** выберите пункт **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="8e81b-139">To create the procedure, from  the **Query** menu, click **Execute**.</span></span> <span data-ttu-id="8e81b-140">Процедура создается как объект в базе данных.</span><span class="sxs-lookup"><span data-stu-id="8e81b-140">The procedure is created as an object in the database.</span></span>  
  
10. <span data-ttu-id="8e81b-141">Чтобы увидеть процедуру в обозревателе объектов, щелкните правой кнопкой мыши элемент **Хранимые процедуры** и выберите пункт **Обновить**.</span><span class="sxs-lookup"><span data-stu-id="8e81b-141">To see the procedure listed in Object Explorer, right-click **Stored Procedures** and select **Refresh**.</span></span>  
  
11. <span data-ttu-id="8e81b-142">Чтобы выполнить процедуру, в обозревателе объектов щелкните правой кнопкой мыши имя хранимой процедуры **HumanResources.uspGetEmployeesTest** и выберите пункт **Выполнение хранимой процедуры**.</span><span class="sxs-lookup"><span data-stu-id="8e81b-142">To run the procedure, in Object Explorer, right-click the stored procedure name **HumanResources.uspGetEmployeesTest** and select **Execute Stored Procedure**.</span></span>  
  
12. <span data-ttu-id="8e81b-143">В окне **Выполнение процедуры** введите Margheim в качестве значения для параметра @LastName и Diane в качестве значения для параметра @FirstName.</span><span class="sxs-lookup"><span data-stu-id="8e81b-143">In the **Execute Procedure** window, enter Margheim as the value for the parameter @LastName and enter the value Diane as the value for the parameter @FirstName.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="8e81b-144">Проверяйте все данные, вводимые пользователем.</span><span class="sxs-lookup"><span data-stu-id="8e81b-144">Validate all user input.</span></span> <span data-ttu-id="8e81b-145">Не включайте их в сценарий, не выполнив проверку.</span><span class="sxs-lookup"><span data-stu-id="8e81b-145">Do not concatenate user input before you validate it.</span></span> <span data-ttu-id="8e81b-146">Никогда не выполняйте команду, построенную на основании непроверенных пользовательских входных данных.</span><span class="sxs-lookup"><span data-stu-id="8e81b-146">Never execute a command constructed from unvalidated user input.</span></span>  
  
###  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="8e81b-147">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8e81b-147">Using Transact-SQL</span></span>  
 <span data-ttu-id="8e81b-148">**Создание процедуры в редакторе запросов**</span><span class="sxs-lookup"><span data-stu-id="8e81b-148">**To create a procedure in Query Editor**</span></span>  
  
1.  <span data-ttu-id="8e81b-149">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8e81b-149">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="8e81b-150">В меню **Файл** выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="8e81b-150">From the **File** menu, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="8e81b-151">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="8e81b-151">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="8e81b-152">В данном примере создается та же хранимая процедура, что и раньше, но с другим именем процедуры.</span><span class="sxs-lookup"><span data-stu-id="8e81b-152">This example creates the same stored procedure as above using a different procedure name.</span></span>  
  
    ```sql
    USE AdventureWorks2012;  
    GO  
    CREATE PROCEDURE HumanResources.uspGetEmployeesTest2   
        @LastName nvarchar(50),   
        @FirstName nvarchar(50)   
    AS
  
        SET NOCOUNT ON;  
        SELECT FirstName, LastName, Department  
        FROM HumanResources.vEmployeeDepartmentHistory  
        WHERE FirstName = @FirstName AND LastName = @LastName  
        AND EndDate IS NULL;  
    GO
    ```  
  
4.  <span data-ttu-id="8e81b-153">Чтобы выполнить процедуру, скопируйте следующий пример в окно создаваемого запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="8e81b-153">To run the procedure, copy and paste the following example into a new query window and click **Execute**.</span></span> <span data-ttu-id="8e81b-154">Показаны различные методы задания значений параметров.</span><span class="sxs-lookup"><span data-stu-id="8e81b-154">Notice that different methods of specifying the parameter values are shown.</span></span>  
  
    ```sql
    EXECUTE HumanResources.uspGetEmployeesTest2 N'Ackerman', N'Pilar';  
    -- Or  
    EXEC HumanResources.uspGetEmployeesTest2 @LastName = N'Ackerman', @FirstName = N'Pilar';  
    GO  
    -- Or  
    EXECUTE HumanResources.uspGetEmployeesTest2 @FirstName = N'Pilar', @LastName = N'Ackerman';  
    GO
    ```  
  
## <a name="see-also"></a><span data-ttu-id="8e81b-155">См. также:</span><span class="sxs-lookup"><span data-stu-id="8e81b-155">See Also</span></span>  
 [<span data-ttu-id="8e81b-156">CREATE PROCEDURE (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="8e81b-156">CREATE PROCEDURE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-procedure-transact-sql)  
  