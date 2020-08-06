---
title: Чтение данных в таблице (учебник) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- reading data in a table
ms.assetid: 532232c9-3d41-45cd-9150-de67a1cbfcf5
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 4bdaaeeddf8f35792c536624abfe6ff11b2dbd2e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665697"
---
# <a name="reading-the-data-in-a-table-tutorial"></a><span data-ttu-id="046f9-102">Чтение данных из таблицы (учебник)</span><span class="sxs-lookup"><span data-stu-id="046f9-102">Reading the Data in a Table (Tutorial)</span></span>
  <span data-ttu-id="046f9-103">Для чтения данных в таблице используется инструкция SELECT.</span><span class="sxs-lookup"><span data-stu-id="046f9-103">Use the SELECT statement to read the data in a table.</span></span> <span data-ttu-id="046f9-104">Инструкция SELECT является одной из наиболее важных инструкций [!INCLUDE[tsql](../includes/tsql-md.md)] , и для нее существует много разновидностей синтаксиса.</span><span class="sxs-lookup"><span data-stu-id="046f9-104">The SELECT statement is one of the most important [!INCLUDE[tsql](../includes/tsql-md.md)] statements, and there are many variations in the syntax.</span></span> <span data-ttu-id="046f9-105">В этом учебнике будет показана работа с пятью простыми вариантами.</span><span class="sxs-lookup"><span data-stu-id="046f9-105">For this tutorial, you will work with five simple versions.</span></span>  
  
### <a name="to-read-the-data-in-a-table"></a><span data-ttu-id="046f9-106">Чтение данных из таблицы</span><span class="sxs-lookup"><span data-stu-id="046f9-106">To read the data in a table</span></span>  
  
1.  <span data-ttu-id="046f9-107">Чтобы прочитать данные из таблицы `Products` , введите и выполните следующие инструкции.</span><span class="sxs-lookup"><span data-stu-id="046f9-107">Type and execute the following statements to read the data in the `Products` table.</span></span>  
  
    ```  
    -- The basic syntax for reading data from a single table  
    SELECT ProductID, ProductName, Price, ProductDescription  
        FROM dbo.Products  
    GO  
  
    ```  
  
2.  <span data-ttu-id="046f9-108">Чтобы выбрать все столбцы в таблице, можно использовать звездочку.</span><span class="sxs-lookup"><span data-stu-id="046f9-108">You can use an asterisk to select all the columns in the table.</span></span> <span data-ttu-id="046f9-109">Такой способ часто используется в нерегламентированных запросах.</span><span class="sxs-lookup"><span data-stu-id="046f9-109">This is often used in ad hoc queries.</span></span> <span data-ttu-id="046f9-110">Необходимо предоставить список всех столбцов в постоянном коде, чтобы инструкция возвращала нужные столбцы, даже если какой-то столбец будет добавлен в таблицу позднее.</span><span class="sxs-lookup"><span data-stu-id="046f9-110">You should provide the column list in you permanent code so that the statement will return the predicted columns, even if a new column is added to the table later.</span></span>  
  
    ```  
    -- Returns all columns in the table  
    -- Does not use the optional schema, dbo  
    SELECT * FROM Products  
    GO  
  
    ```  
  
3.  <span data-ttu-id="046f9-111">Если нет необходимости возвращать определенные столбцы, их можно опустить.</span><span class="sxs-lookup"><span data-stu-id="046f9-111">You can omit columns that you do not want to return.</span></span> <span data-ttu-id="046f9-112">Столбцы возвращаются в том порядке, в котором они перечислены.</span><span class="sxs-lookup"><span data-stu-id="046f9-112">The columns will be returned in the order that they are listed.</span></span>  
  
    ```  
    -- Returns only two of the columns from the table  
    SELECT ProductName, Price  
        FROM dbo.Products  
    GO  
  
    ```  
  
4.  <span data-ttu-id="046f9-113">Чтобы ограничить количество строк, возвращаемых пользователю, используйте предложение `WHERE` .</span><span class="sxs-lookup"><span data-stu-id="046f9-113">Use a `WHERE` clause to limit the rows that are returned to the user.</span></span>  
  
    ```  
    -- Returns only two of the records in the table  
    SELECT ProductID, ProductName, Price, ProductDescription  
        FROM dbo.Products  
        WHERE ProductID < 60  
    GO  
  
    ```  
  
5.  <span data-ttu-id="046f9-114">Можно работать со значениями столбцов, по мере того как столбцы возвращаются.</span><span class="sxs-lookup"><span data-stu-id="046f9-114">You can work with the values in the columns as they are returned.</span></span> <span data-ttu-id="046f9-115">В следующем примере выполняется математическая операция над столбцом `Price` .</span><span class="sxs-lookup"><span data-stu-id="046f9-115">The following example performs a mathematical operation on the `Price` column.</span></span> <span data-ttu-id="046f9-116">Столбцы, изменяемые подобным образом, не имеют имени, если только имя не указывается с использованием ключевого слова `AS` .</span><span class="sxs-lookup"><span data-stu-id="046f9-116">Columns that have been changed in this way will not have a name unless you provide one by using the `AS` keyword.</span></span>  
  
    ```  
    -- Returns ProductName and the Price including a 7% tax  
    -- Provides the name CustomerPays for the calculated column  
    SELECT ProductName, Price * 1.07 AS CustomerPays  
        FROM dbo.Products  
    GO  
    ```  
  
## <a name="functions-that-are-useful-in-a-select-statement"></a><span data-ttu-id="046f9-117">Функции, используемые в инструкции SELECT</span><span class="sxs-lookup"><span data-stu-id="046f9-117">Functions That Are Useful in a SELECT Statement</span></span>  
 <span data-ttu-id="046f9-118">Сведения о работе с функциями, которые используются в инструкциях SELECT, см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="046f9-118">For information about some functions that you can use to work with data in SELECT statements, see the following topics:</span></span>  
  
|||  
|-|-|  
|[<span data-ttu-id="046f9-119">Строковые функции (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="046f9-119">String Functions &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/string-functions-transact-sql)|[<span data-ttu-id="046f9-120">Типы данных и функции даты и времени (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="046f9-120">Date and Time Data Types and Functions &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/date-and-time-data-types-and-functions-transact-sql)|  
|[<span data-ttu-id="046f9-121">Математические функции (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="046f9-121">Mathematical Functions &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/mathematical-functions-transact-sql)|[<span data-ttu-id="046f9-122">Функции для работы с изображениями и текстом (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="046f9-122">Text and Image Functions &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/text-and-image-functions-textptr-transact-sql)|  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="046f9-123">Следующая задача занятия</span><span class="sxs-lookup"><span data-stu-id="046f9-123">Next Task in Lesson</span></span>  
 [<span data-ttu-id="046f9-124">Сводка. Создание объектов базы данных</span><span class="sxs-lookup"><span data-stu-id="046f9-124">Summary: Creating Database Objects</span></span>](lesson-1-5-summary-creating-database-objects.md)  
  
## <a name="see-also"></a><span data-ttu-id="046f9-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="046f9-125">See Also</span></span>  
 [<span data-ttu-id="046f9-126">SELECT (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="046f9-126">SELECT &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/queries/select-transact-sql)  
  
  
