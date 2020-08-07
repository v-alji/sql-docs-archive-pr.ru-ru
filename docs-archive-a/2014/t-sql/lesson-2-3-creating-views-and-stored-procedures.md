---
title: Создание представлений и хранимых процедур | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- creating views and stored procedures
ms.assetid: 53a0426d-07d8-4b7c-aa21-22632753bad8
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 76f6ecec446536191e8be4b05547ba5fd44c9d8d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727730"
---
# <a name="creating-views-and-stored-procedures"></a><span data-ttu-id="e1efd-102">Создание представлений и хранимых процедур</span><span class="sxs-lookup"><span data-stu-id="e1efd-102">Creating Views and Stored Procedures</span></span>
  <span data-ttu-id="e1efd-103">После того как Мэри предоставлен доступ к базе данных **TestData** , можно создать некоторые объекты базы данных, такие как представление или хранимая процедура, а затем предоставить Мэри доступ к ним.</span><span class="sxs-lookup"><span data-stu-id="e1efd-103">Now that Mary can access the **TestData** database, you may want to create some database objects, such as a view and a stored procedure, and then grant Mary access to them.</span></span> <span data-ttu-id="e1efd-104">Представление является хранимой инструкцией SELECT, а хранимая процедура представляет собой одну или более инструкций [!INCLUDE[tsql](../includes/tsql-md.md)] , выполняемых в виде пакета.</span><span class="sxs-lookup"><span data-stu-id="e1efd-104">A view is a stored SELECT statement, and a stored procedure is one or more [!INCLUDE[tsql](../includes/tsql-md.md)] statements that execute as a batch.</span></span>  
  
 <span data-ttu-id="e1efd-105">Представления запрашиваются так же, как таблицы, и не принимают параметры.</span><span class="sxs-lookup"><span data-stu-id="e1efd-105">Views are queried like tables and do not accept parameters.</span></span> <span data-ttu-id="e1efd-106">Хранимые процедуры сложнее, чем представления.</span><span class="sxs-lookup"><span data-stu-id="e1efd-106">Stored procedures are more complex than views.</span></span> <span data-ttu-id="e1efd-107">Хранимые процедуры содержат как входные, так и выходные параметры и могут содержать инструкции, которые управляют потоком кода, например IF и WHILE.</span><span class="sxs-lookup"><span data-stu-id="e1efd-107">Stored procedures can have both input and output parameters and can contain statements to control the flow of the code, such as IF and WHILE statements.</span></span> <span data-ttu-id="e1efd-108">Использование хранимых процедур для всех повторяющихся действий в базе данных является хорошим стилем программирования.</span><span class="sxs-lookup"><span data-stu-id="e1efd-108">It is good programming practice to use stored procedures for all repetitive actions in the database.</span></span>  
  
 <span data-ttu-id="e1efd-109">В этом примере используется инструкция CREATE VIEW, чтобы создать представление, которое выбирает только два столбца в таблице **Products** .</span><span class="sxs-lookup"><span data-stu-id="e1efd-109">For this example, you will use CREATE VIEW to create a view that selects only two of the columns in the **Products** table.</span></span> <span data-ttu-id="e1efd-110">Затем с помощью инструкции CREATE PROCEDURE создается хранимая процедура, которая принимает цену в качестве параметра и возвращает только те продукты, цена которых меньше значения, указанного в качестве параметра.</span><span class="sxs-lookup"><span data-stu-id="e1efd-110">Then, you will use CREATE PROCEDURE to create a stored procedure that accepts a price parameter and returns only those products that cost less than the specified parameter value.</span></span>  
  
### <a name="to-create-a-view"></a><span data-ttu-id="e1efd-111">Создание представления</span><span class="sxs-lookup"><span data-stu-id="e1efd-111">To create a view</span></span>  
  
1.  <span data-ttu-id="e1efd-112">Выполните следующую инструкцию, создающую очень простое представление, которое выполняет инструкцию select и возвращает названия и цены продуктов пользователю.</span><span class="sxs-lookup"><span data-stu-id="e1efd-112">Execute the following statement to create a very simple view that executes a select statement, and returns the names and prices of our products to the user.</span></span>  
  
    ```  
    CREATE VIEW vw_Names  
       AS  
       SELECT ProductName, Price FROM Products;  
    GO  
  
    ```  
  
### <a name="test-the-view"></a><span data-ttu-id="e1efd-113">Тестирование представления</span><span class="sxs-lookup"><span data-stu-id="e1efd-113">Test the view</span></span>  
  
1.  <span data-ttu-id="e1efd-114">С представлениями обращаются так же, как с таблицами.</span><span class="sxs-lookup"><span data-stu-id="e1efd-114">Views are treated just like tables.</span></span> <span data-ttu-id="e1efd-115">Используйте инструкцию `SELECT` , чтобы получить доступ к представлению.</span><span class="sxs-lookup"><span data-stu-id="e1efd-115">Use a `SELECT` statement to access a view.</span></span>  
  
    ```  
    SELECT * FROM vw_Names;  
    GO  
  
    ```  
  
### <a name="to-create-a-stored-procedure"></a><span data-ttu-id="e1efd-116">Создание хранимой процедуры</span><span class="sxs-lookup"><span data-stu-id="e1efd-116">To create a stored procedure</span></span>  
  
1.  <span data-ttu-id="e1efd-117">В следующем примере создается хранимая процедура `pr_Names`с входным параметром `@VarPrice` типа `money`.</span><span class="sxs-lookup"><span data-stu-id="e1efd-117">The following statement creates a stored procedure name `pr_Names`, accepts an input parameter named `@VarPrice` of data type `money`.</span></span> <span data-ttu-id="e1efd-118">Эта хранимая процедура печатает инструкцию `Products less than` , соединенную операцией сцепления с входным параметром, тип которого преобразуется из `money` в `varchar(10)` .</span><span class="sxs-lookup"><span data-stu-id="e1efd-118">The stored procedure prints the statement `Products less than` concatenated with the input parameter that is changed from the `money` data type into a `varchar(10)` character data type.</span></span> <span data-ttu-id="e1efd-119">Затем процедура выполняет инструкцию `SELECT` на представлении, передавая входной параметр в предложение `WHERE` .</span><span class="sxs-lookup"><span data-stu-id="e1efd-119">Then, the procedure executes a `SELECT` statement on the view, passing the input parameter as part of the `WHERE` clause.</span></span> <span data-ttu-id="e1efd-120">Возвращаются все продукты, цена которых меньше значения входного параметра.</span><span class="sxs-lookup"><span data-stu-id="e1efd-120">This returns all products that cost less than the input parameter value.</span></span>  
  
    ```  
    CREATE PROCEDURE pr_Names @VarPrice money  
       AS  
       BEGIN  
          -- The print statement returns text to the user  
          PRINT 'Products less than ' + CAST(@VarPrice AS varchar(10));  
          -- A second statement starts here  
          SELECT ProductName, Price FROM vw_Names  
                WHERE Price < @varPrice;  
       END  
    GO  
  
    ```  
  
### <a name="test-the-stored-procedure"></a><span data-ttu-id="e1efd-121">Тестирование хранимой процедуры</span><span class="sxs-lookup"><span data-stu-id="e1efd-121">Test the stored procedure</span></span>  
  
1.  <span data-ttu-id="e1efd-122">Чтобы выполнить хранимую процедуру, введите и выполните следующую инструкцию.</span><span class="sxs-lookup"><span data-stu-id="e1efd-122">To test the stored procedure, type and execute the following statement.</span></span> <span data-ttu-id="e1efd-123">Эта процедура должна возвратить названия двух продуктов, введенных в таблицу `Products` на занятии 1, цена которых меньше `10.00`.</span><span class="sxs-lookup"><span data-stu-id="e1efd-123">The procedure should return the names of the two products entered into the `Products` table in Lesson 1 with a price that is less than `10.00`.</span></span>  
  
    ```  
    EXECUTE pr_Names 10.00;  
    GO  
  
    ```  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="e1efd-124">Следующая задача занятия</span><span class="sxs-lookup"><span data-stu-id="e1efd-124">Next Task in Lesson</span></span>  
 [<span data-ttu-id="e1efd-125">Предоставление доступа к объекту базы данных</span><span class="sxs-lookup"><span data-stu-id="e1efd-125">Granting Access to a Database Object</span></span>](lesson-2-4-granting-access-to-a-database-object.md)  
  
## <a name="see-also"></a><span data-ttu-id="e1efd-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="e1efd-126">See Also</span></span>  
 <span data-ttu-id="e1efd-127">[CREATE VIEW (Transact-SQL)](/sql/t-sql/statements/create-view-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e1efd-127">[CREATE VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-view-transact-sql) </span></span>  
 [<span data-ttu-id="e1efd-128">CREATE PROCEDURE (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="e1efd-128">CREATE PROCEDURE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-procedure-transact-sql)  
  
  
