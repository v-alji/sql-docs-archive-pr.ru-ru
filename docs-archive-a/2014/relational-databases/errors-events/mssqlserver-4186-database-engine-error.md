---
title: MSSQLSERVER_4186 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 4186 (Database Engine error)
ms.assetid: 1ae88554-f291-45bc-a186-6f41d9cd0fca
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 525c1c3bd6e631044b8bc7f17b2c2a01aeb1ef8b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655236"
---
# <a name="mssqlserver_4186"></a><span data-ttu-id="6a7f9-102">MSSQLSERVER_4186</span><span class="sxs-lookup"><span data-stu-id="6a7f9-102">MSSQLSERVER_4186</span></span>
    
## <a name="details"></a><span data-ttu-id="6a7f9-103">Сведения</span><span class="sxs-lookup"><span data-stu-id="6a7f9-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6a7f9-104">Название продукта</span><span class="sxs-lookup"><span data-stu-id="6a7f9-104">Product Name</span></span>|<span data-ttu-id="6a7f9-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="6a7f9-105">SQL Server</span></span>|  
|<span data-ttu-id="6a7f9-106">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="6a7f9-106">Event ID</span></span>|<span data-ttu-id="6a7f9-107">4186</span><span class="sxs-lookup"><span data-stu-id="6a7f9-107">4186</span></span>|  
|<span data-ttu-id="6a7f9-108">Источник события</span><span class="sxs-lookup"><span data-stu-id="6a7f9-108">Event Source</span></span>|<span data-ttu-id="6a7f9-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="6a7f9-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="6a7f9-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="6a7f9-110">Component</span></span>|<span data-ttu-id="6a7f9-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="6a7f9-111">SQLEngine</span></span>|  
|<span data-ttu-id="6a7f9-112">Символическое имя</span><span class="sxs-lookup"><span data-stu-id="6a7f9-112">Symbolic Name</span></span>||  
|<span data-ttu-id="6a7f9-113">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="6a7f9-113">Message Text</span></span>|<span data-ttu-id="6a7f9-114">Нельзя ссылаться на столбец «%ls.%.\*ls» из предложения OUTPUT, так как определение столбца содержит вложенный запрос или ссылку на функцию, которая выполняет доступ к системным данным или данным пользователя.</span><span class="sxs-lookup"><span data-stu-id="6a7f9-114">Column '%ls.%.\*ls' cannot be referenced in the OUTPUT clause because the column definition contains a subquery or references a function that performs user or system data access.</span></span> <span data-ttu-id="6a7f9-115">По умолчанию предполагается, что функция выполняет доступ к данным, если она не привязана к схеме.</span><span class="sxs-lookup"><span data-stu-id="6a7f9-115">A function is assumed by default to perform data access if it is not schemabound.</span></span> <span data-ttu-id="6a7f9-116">Рассмотрите возможность удаления вложенного запроса или функции из определения столбца либо удаления столбца из предложения OUTPUT.</span><span class="sxs-lookup"><span data-stu-id="6a7f9-116">Consider removing the subquery or function from the column definition or removing the column from the OUTPUT clause.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="6a7f9-117">Объяснение</span><span class="sxs-lookup"><span data-stu-id="6a7f9-117">Explanation</span></span>  
 <span data-ttu-id="6a7f9-118">Во избежание недетерминированного поведения в предложении OUTPUT запрещено ссылаться на столбец из представления или встроенной функции, возвращающей табличное значение, если этот столбец определен одним из следующих методов.</span><span class="sxs-lookup"><span data-stu-id="6a7f9-118">To prevent nondeterministic behavior, the OUTPUT clause cannot reference a column from a view or inline table-valued function when that column is defined by one of the following methods:</span></span>  
  
-   <span data-ttu-id="6a7f9-119">вложенный запрос.</span><span class="sxs-lookup"><span data-stu-id="6a7f9-119">A subquery.</span></span>  
  
-   <span data-ttu-id="6a7f9-120">Определяемая пользователем функция, которая осуществляет или может осуществлять доступ к пользовательским или системным данным.</span><span class="sxs-lookup"><span data-stu-id="6a7f9-120">A user-defined function that performs user or system data access, or is assumed to perform such access.</span></span>  
  
-   <span data-ttu-id="6a7f9-121">Вычисляемый столбец, содержащий определяемую пользователем функцию, которая осуществляет доступ к пользовательским или системным данным в своем определении.</span><span class="sxs-lookup"><span data-stu-id="6a7f9-121">A computed column that contains a user-defined function that performs user or system data access in its definition.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="6a7f9-122">Примеры</span><span class="sxs-lookup"><span data-stu-id="6a7f9-122">Examples</span></span>  
 <span data-ttu-id="6a7f9-123">**Просмотр столбца, определенного вложенным запросом**</span><span class="sxs-lookup"><span data-stu-id="6a7f9-123">**View Column Defined by a Subquery**</span></span>  
  
 <span data-ttu-id="6a7f9-124">В следующем примере создается представление, которое использует вложенный запрос в списке выбора, чтобы определить столбец `State`.</span><span class="sxs-lookup"><span data-stu-id="6a7f9-124">The following example creates a view that uses a subquery in the select list to define the column `State`.</span></span> <span data-ttu-id="6a7f9-125">После этого инструкция UPDATE ссылается на столбец `State` в предложении OUTPUT и происходит ошибка из-за вложенного запроса в списке выбора.</span><span class="sxs-lookup"><span data-stu-id="6a7f9-125">An UPDATE statement then references the `State` column in the OUTPUT clause and fails because ob the subquery in the select list.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
CREATE VIEW dbo.V1  
AS  
    SELECT City,  
-- subquery to return the State name  
           (SELECT Name FROM Person.StateProvince AS sp   
            WHERE sp.StateProvinceID = a.StateProvinceID) AS State  
    FROM Person.Address AS a;  
GO  
--Reference the State column in the OUTPUT clause of an UPDATE statement  
UPDATE dbo.V1   
SET City = City + 'Test'   
OUTPUT deleted.City, deleted.State, inserted.City, inserted.State  
WHERE State = 'Texas';  
GO  
```  
  
 <span data-ttu-id="6a7f9-126">**Просмотр столбца, определенного функцией**</span><span class="sxs-lookup"><span data-stu-id="6a7f9-126">**View Column Defined by a Function**</span></span>  
  
 <span data-ttu-id="6a7f9-127">В следующем примере создается представление, которое использует в списке выбора скалярную функцию `dbo.ufnGetStock` доступа к данным, чтобы определить столбец `CurrentInventory`.</span><span class="sxs-lookup"><span data-stu-id="6a7f9-127">The following example creates a view that uses the data accessing, scalar function `dbo.ufnGetStock` in the select list to define the column `CurrentInventory`.</span></span> <span data-ttu-id="6a7f9-128">Затем инструкция UPDATE ссылается на столбец `CurrentInventory` в предложении OUTPUT.</span><span class="sxs-lookup"><span data-stu-id="6a7f9-128">An UPDATE statement then references the `CurrentInventory` column in the OUTPUT clause .</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
CREATE VIEW Production.ReorderLevels  
AS  
    SELECT ProductID, ProductModelID, ReorderPoint,  
           dbo.ufnGetStock(ProductID) AS CurrentInventory  
    FROM Production.Product;  
GO  
  
UPDATE Production.ReorderLevels  
SET ReorderPoint += CurrentInventory  
OUTPUT deleted.ReorderPoint, deleted.CurrentInventory,  
       inserted.ReorderPoint, inserted.CurrentInventory  
WHERE ProductModelID BETWEEN 75 and 80;  
```  
  
## <a name="user-action"></a><span data-ttu-id="6a7f9-129">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="6a7f9-129">User Action</span></span>  
 <span data-ttu-id="6a7f9-130">Ошибку 4186 можно исправить одним из следующих способов.</span><span class="sxs-lookup"><span data-stu-id="6a7f9-130">Error 4186 can be corrected in one of the following ways:</span></span>  
  
-   <span data-ttu-id="6a7f9-131">Используйте соединения вместо вложенных запросов, чтобы определить столбец в представлении или функции.</span><span class="sxs-lookup"><span data-stu-id="6a7f9-131">Use joins instead of subqueries to define the column in the view or function.</span></span> <span data-ttu-id="6a7f9-132">Например, можно перезаписать представление `dbo.V1` следующим образом.</span><span class="sxs-lookup"><span data-stu-id="6a7f9-132">For example, you can rewrite the view `dbo.V1` as follows.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    CREATE VIEW dbo.V1  
    AS  
        SELECT City, sp.Name AS State  
        FROM Person.Address AS a   
        JOIN Person.StateProvince AS sp   
        ON sp.StateProvinceID = a.StateProvinceID;  
    ```  
  
-   <span data-ttu-id="6a7f9-133">Изучите определение определяемой пользователем функции.</span><span class="sxs-lookup"><span data-stu-id="6a7f9-133">Examine the definition of the user-defined function.</span></span> <span data-ttu-id="6a7f9-134">Если функция не осуществляет доступ к пользовательским или системным данным, измените функцию, включив в нее предложение WITH SCHEMABINDING.</span><span class="sxs-lookup"><span data-stu-id="6a7f9-134">If the function does not perform user or system data access, alter the function to include the WITH SCHEMABINDING clause.</span></span>  
  
-   <span data-ttu-id="6a7f9-135">Удалите столбец из предложения OUTPUT.</span><span class="sxs-lookup"><span data-stu-id="6a7f9-135">Remove the column from the OUTPUT clause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a7f9-136">См. также:</span><span class="sxs-lookup"><span data-stu-id="6a7f9-136">See Also</span></span>  
 [<span data-ttu-id="6a7f9-137">Предложение OUTPUT (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="6a7f9-137">OUTPUT Clause &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/queries/output-clause-transact-sql)  
  
  
