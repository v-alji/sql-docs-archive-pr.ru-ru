---
title: Вставка данных в таблицу и их обновление (учебник) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- inserting and updating data
ms.assetid: 514dc87a-b829-43b5-8fc8-1a400a260284
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 0646019f166e1c2cc126a4cc7d2ed8f27a7bd2f3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665696"
---
# <a name="inserting-and-updating-data-in-a-table-tutorial"></a><span data-ttu-id="75ccf-102">Вставка данных в таблицу и их обновление (учебник)</span><span class="sxs-lookup"><span data-stu-id="75ccf-102">Inserting and Updating Data in a Table (Tutorial)</span></span>
  <span data-ttu-id="75ccf-103"> После создания таблицы **Products** в нее можно вставлять данные с помощью инструкции INSERT.</span><span class="sxs-lookup"><span data-stu-id="75ccf-103">Now that you have created the **Products** table, you are ready to insert data into the table by using the INSERT statement.</span></span> <span data-ttu-id="75ccf-104">После вставки данных содержимое строки изменяется с помощью инструкции UPDATE.</span><span class="sxs-lookup"><span data-stu-id="75ccf-104">After the data is inserted, you will change the content of a row by using an UPDATE statement.</span></span> <span data-ttu-id="75ccf-105">Предложение WHERE предназначено для ограничения числа строк, изменяемых в процессе выполнения инструкции UPDATE до одной строки.</span><span class="sxs-lookup"><span data-stu-id="75ccf-105">You will use the WHERE clause of the UPDATE statement to restrict the update to a single row.</span></span> <span data-ttu-id="75ccf-106">Чтобы ввести следующие данные, потребуется четыре инструкции.</span><span class="sxs-lookup"><span data-stu-id="75ccf-106">The four statements will enter the following data.</span></span>  
  
|<span data-ttu-id="75ccf-107">ProductID</span><span class="sxs-lookup"><span data-stu-id="75ccf-107">ProductID</span></span>|<span data-ttu-id="75ccf-108">ProductName</span><span class="sxs-lookup"><span data-stu-id="75ccf-108">ProductName</span></span>|<span data-ttu-id="75ccf-109">Price</span><span class="sxs-lookup"><span data-stu-id="75ccf-109">Price</span></span>|<span data-ttu-id="75ccf-110">ProductDescription</span><span class="sxs-lookup"><span data-stu-id="75ccf-110">ProductDescription</span></span>|  
|---------------|-----------------|-----------|------------------------|  
|<span data-ttu-id="75ccf-111">1</span><span class="sxs-lookup"><span data-stu-id="75ccf-111">1</span></span>|<span data-ttu-id="75ccf-112">Clamp</span><span class="sxs-lookup"><span data-stu-id="75ccf-112">Clamp</span></span>|<span data-ttu-id="75ccf-113">12,48</span><span class="sxs-lookup"><span data-stu-id="75ccf-113">12.48</span></span>|<span data-ttu-id="75ccf-114">Workbench clamp</span><span class="sxs-lookup"><span data-stu-id="75ccf-114">Workbench clamp</span></span>|  
|<span data-ttu-id="75ccf-115">50</span><span class="sxs-lookup"><span data-stu-id="75ccf-115">50</span></span>|<span data-ttu-id="75ccf-116">Screwdriver</span><span class="sxs-lookup"><span data-stu-id="75ccf-116">Screwdriver</span></span>|<span data-ttu-id="75ccf-117">3,17</span><span class="sxs-lookup"><span data-stu-id="75ccf-117">3.17</span></span>|<span data-ttu-id="75ccf-118">Flat head</span><span class="sxs-lookup"><span data-stu-id="75ccf-118">Flat head</span></span>|  
|<span data-ttu-id="75ccf-119">75</span><span class="sxs-lookup"><span data-stu-id="75ccf-119">75</span></span>|<span data-ttu-id="75ccf-120">Tire Bar</span><span class="sxs-lookup"><span data-stu-id="75ccf-120">Tire Bar</span></span>||<span data-ttu-id="75ccf-121">Tool for changing tires.</span><span class="sxs-lookup"><span data-stu-id="75ccf-121">Tool for changing tires.</span></span>|  
|<span data-ttu-id="75ccf-122">3000</span><span class="sxs-lookup"><span data-stu-id="75ccf-122">3000</span></span>|<span data-ttu-id="75ccf-123">3mm Bracket</span><span class="sxs-lookup"><span data-stu-id="75ccf-123">3mm Bracket</span></span>|<span data-ttu-id="75ccf-124">0,52</span><span class="sxs-lookup"><span data-stu-id="75ccf-124">.52</span></span>||  
  
 <span data-ttu-id="75ccf-125">Базовый синтаксис: INSERT, имя таблицы, список столбцов, VALUES, а затем список добавляемых значений.</span><span class="sxs-lookup"><span data-stu-id="75ccf-125">The basic syntax is: INSERT, table name, column list, VALUES, and then a list of the values to be inserted.</span></span> <span data-ttu-id="75ccf-126">Два дефиса в начале строки означают, что строка является примечанием и текст не будет обрабатываться компилятором.</span><span class="sxs-lookup"><span data-stu-id="75ccf-126">The two hyphens in front of a line indicate that the line is a comment and the text will be ignored by the compiler.</span></span> <span data-ttu-id="75ccf-127">В этом случае примечание описывает возможные варианты синтаксиса.</span><span class="sxs-lookup"><span data-stu-id="75ccf-127">In this case, the comment describes a permissible variation of the syntax.</span></span>  
  
### <a name="to-insert-data-into-a-table"></a><span data-ttu-id="75ccf-128">Вставка данных в таблицу</span><span class="sxs-lookup"><span data-stu-id="75ccf-128">To insert data into a table</span></span>  
  
1.  <span data-ttu-id="75ccf-129">Выполните следующую инструкцию, чтобы добавить строку в таблицу `Products` , которая была создана в предыдущей задаче.</span><span class="sxs-lookup"><span data-stu-id="75ccf-129">Execute the following statement to insert a row into the `Products` table that was created in the previous task.</span></span> <span data-ttu-id="75ccf-130">Далее представлен базовый синтаксис.</span><span class="sxs-lookup"><span data-stu-id="75ccf-130">This is the basic syntax.</span></span>  
  
    ```  
    -- Standard syntax  
    INSERT dbo.Products (ProductID, ProductName, Price, ProductDescription)  
        VALUES (1, 'Clamp', 12.48, 'Workbench clamp')  
    GO  
  
    ```  
  
2.  <span data-ttu-id="75ccf-131">В следующей инструкции показано, как можно изменить порядок, в котором приведены параметры, изменив расположение `ProductID` и `ProductName` одновременно как в списке полей (в круглых скобках), так и в списке значений.</span><span class="sxs-lookup"><span data-stu-id="75ccf-131">The following statement shows how you can change the order in which the parameters are provided by switching the placement of the `ProductID` and `ProductName` in both the field list (in parentheses) and in the values list.</span></span>  
  
    ```  
    -- Changing the order of the columns  
    INSERT dbo.Products (ProductName, ProductID, Price, ProductDescription)  
        VALUES ('Screwdriver', 50, 3.17, 'Flat head')  
    GO  
  
    ```  
  
3.  <span data-ttu-id="75ccf-132">Следующая инструкция показывает, что имена столбцов перечислять не обязательно, если значения перечислены в нужном порядке.</span><span class="sxs-lookup"><span data-stu-id="75ccf-132">The following statement demonstrates that the names of the columns are optional, as long as the values are listed in the correct order.</span></span> <span data-ttu-id="75ccf-133">Этот синтаксис является стандартным, но не рекомендуется, поскольку другим будет трудно понять ваш код.</span><span class="sxs-lookup"><span data-stu-id="75ccf-133">This syntax is common but is not recommended because it might be harder for others to understand your code.</span></span> <span data-ttu-id="75ccf-134">`NULL` указано в столбце `Price` , так как цена этого товара пока неизвестна.</span><span class="sxs-lookup"><span data-stu-id="75ccf-134">`NULL` is specified for the `Price` column because the price for this product is not yet known.</span></span>  
  
    ```  
    -- Skipping the column list, but keeping the values in order  
    INSERT dbo.Products  
        VALUES (75, 'Tire Bar', NULL, 'Tool for changing tires.')  
    GO  
  
    ```  
  
4.  <span data-ttu-id="75ccf-135">Имя схемы указывать не обязательно, пока доступ и изменение таблицы осуществляются с помощью схемы по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="75ccf-135">The schema name is optional as long as you are accessing and changing a table in your default schema.</span></span> <span data-ttu-id="75ccf-136">Поскольку в столбце `ProductDescription` разрешены значения NULL и значение для столбца не приведено, имя и значение столбца `ProductDescription` в инструкции могут быть полностью опущены.</span><span class="sxs-lookup"><span data-stu-id="75ccf-136">Because the `ProductDescription` column allows null values and no value is being provided, the `ProductDescription` column name and value can be dropped from the statement completely.</span></span>  
  
    ```  
    -- Dropping the optional dbo and dropping the ProductDescription column  
    INSERT Products (ProductID, ProductName, Price)  
        VALUES (3000, '3mm Bracket', .52)  
    GO  
    ```  
  
### <a name="to-update-the-products-table"></a><span data-ttu-id="75ccf-137">Обновление таблицы продуктов</span><span class="sxs-lookup"><span data-stu-id="75ccf-137">To update the products table</span></span>  
  
1.  <span data-ttu-id="75ccf-138">Введите и выполните следующую инструкцию `UPDATE` , чтобы изменить значение `ProductName` второго продукта со значения `Screwdriver`на значение `Flat Head Screwdriver`.</span><span class="sxs-lookup"><span data-stu-id="75ccf-138">Type and execute the following `UPDATE` statement to change the `ProductName` of the second product from `Screwdriver`, to `Flat Head Screwdriver`.</span></span>  
  
    ```  
    UPDATE dbo.Products  
        SET ProductName = 'Flat Head Screwdriver'  
        WHERE ProductID = 50  
    GO  
    ```  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="75ccf-139">Следующая задача занятия</span><span class="sxs-lookup"><span data-stu-id="75ccf-139">Next Task in Lesson</span></span>  
 [<span data-ttu-id="75ccf-140">Чтение данных из таблицы (учебник)</span><span class="sxs-lookup"><span data-stu-id="75ccf-140">Reading the Data in a Table &#40;Tutorial&#41;</span></span>](lesson-1-4-reading-the-data-in-a-table.md)  
  
## <a name="see-also"></a><span data-ttu-id="75ccf-141">См. также:</span><span class="sxs-lookup"><span data-stu-id="75ccf-141">See Also</span></span>  
 <span data-ttu-id="75ccf-142">[INSERT (Transact-SQL)](/sql/t-sql/statements/insert-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="75ccf-142">[INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/insert-transact-sql) </span></span>  
 [<span data-ttu-id="75ccf-143">UPDATE (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="75ccf-143">UPDATE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/queries/update-transact-sql)  
  
  
