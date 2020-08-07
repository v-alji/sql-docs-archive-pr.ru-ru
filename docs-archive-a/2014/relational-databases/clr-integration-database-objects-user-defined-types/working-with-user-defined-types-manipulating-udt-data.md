---
title: Управление данными определяемых пользователем типов | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
dev_langs:
- TSQL
helpviewer_keywords:
- CAST function
- data deletions [CLR integration]
- data insertions [CLR integration]
- CONVERT function
- data updates [CLR integration]
- comparing data
- updating data [CLR integration]
- removing data
- IsByteOrdered property
- variables [CLR integration]
- data manipulation [CLR integration]
- user-defined types [CLR integration], data manipulation
- deleting data
- UDTs [CLR integration], data manipulation
- invoking UDT methods
- inserting data
ms.assetid: 51b1a5f2-7591-4e11-bfe2-d88e0836403f
author: rothja
ms.author: jroth
ms.openlocfilehash: 75810a2ffd92130e45025f742d43ba7917d73992
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730746"
---
# <a name="manipulating-udt-data"></a><span data-ttu-id="3cb60-102">Работа с данными определяемого пользователем типа</span><span class="sxs-lookup"><span data-stu-id="3cb60-102">Manipulating UDT Data</span></span>
  <span data-ttu-id="3cb60-103">В [!INCLUDE[tsql](../../includes/tsql-md.md)] не используется специальный синтаксис для инструкций INSERT, UPDATE или DELETE при изменении данных в столбцах определяемого пользователем типа.</span><span class="sxs-lookup"><span data-stu-id="3cb60-103">[!INCLUDE[tsql](../../includes/tsql-md.md)] provides no specialized syntax for INSERT, UPDATE, or DELETE statements when modifying data in user-defined type (UDT) columns.</span></span> <span data-ttu-id="3cb60-104">Функции [!INCLUDE[tsql](../../includes/tsql-md.md)] CAST и CONVERT используются для приведения собственных типов данных к определяемому пользователем типу.</span><span class="sxs-lookup"><span data-stu-id="3cb60-104">The [!INCLUDE[tsql](../../includes/tsql-md.md)] CAST or CONVERT functions are used to cast native data types to the UDT type.</span></span>  
  
## <a name="inserting-data-in-a-udt-column"></a><span data-ttu-id="3cb60-105">Вставка данных в столбец определяемого пользователем типа</span><span class="sxs-lookup"><span data-stu-id="3cb60-105">Inserting Data in a UDT Column</span></span>  
 <span data-ttu-id="3cb60-106">Следующие [!INCLUDE[tsql](../../includes/tsql-md.md)] инструкции вставляют три строки образца данных в таблицу **points** .</span><span class="sxs-lookup"><span data-stu-id="3cb60-106">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] statements insert three rows of sample data into the **Points** table.</span></span> <span data-ttu-id="3cb60-107">Тип данных **Point** состоит из целочисленных значений X и Y, которые предоставляются как свойства определяемого пользователем типа.</span><span class="sxs-lookup"><span data-stu-id="3cb60-107">The **Point** data type consists of X and Y integer values that are exposed as properties of the UDT.</span></span> <span data-ttu-id="3cb60-108">Для приведения значений X и Y с разделителями-запятыми в тип **Point** необходимо использовать функцию CAST или Convert.</span><span class="sxs-lookup"><span data-stu-id="3cb60-108">You must use either the CAST or CONVERT function to cast the comma-delimited X and Y values to the **Point** type.</span></span> <span data-ttu-id="3cb60-109">Первые две инструкции используют функцию CONVERT для преобразования строкового значения в тип **Point** , а третья инструкция использует функцию CAST:</span><span class="sxs-lookup"><span data-stu-id="3cb60-109">The first two statements use the CONVERT function to convert a string value to the **Point** type, and the third statement uses the CAST function:</span></span>  
  
```  
INSERT INTO dbo.Points (PointValue) VALUES (CONVERT(Point, '3,4'));  
INSERT INTO dbo.Points (PointValue) VALUES (CONVERT(Point, '1,5'));  
INSERT INTO dbo.Points (PointValue) VALUES (CAST ('1,99' AS Point));  
```  
  
## <a name="selecting-data"></a><span data-ttu-id="3cb60-110">Выбор данных</span><span class="sxs-lookup"><span data-stu-id="3cb60-110">Selecting Data</span></span>  
 <span data-ttu-id="3cb60-111">Следующая инструкция SELECT выбирает двоичное значение определяемого пользователем типа.</span><span class="sxs-lookup"><span data-stu-id="3cb60-111">The following SELECT statement selects the binary value of the UDT.</span></span>  
  
```  
SELECT ID, PointValue FROM dbo.Points  
```  
  
 <span data-ttu-id="3cb60-112">Чтобы просмотреть выходные данные в удобочитаемом формате, вызовите `ToString` метод определяемого пользователем типа **Point** , который преобразует значение в строковое представление.</span><span class="sxs-lookup"><span data-stu-id="3cb60-112">To see the output displayed in a readable format, call the `ToString` method of the **Point** UDT, which converts the value to its string representation.</span></span>  
  
```  
SELECT ID, PointValue.ToString() AS PointValue   
FROM dbo.Points;  
```  
  
 <span data-ttu-id="3cb60-113">Получены следующие результаты.</span><span class="sxs-lookup"><span data-stu-id="3cb60-113">This produces the following results.</span></span>  
  
```  
IDPointValue  
----------  
13,4  
21,5  
31,99  
```  
  
 <span data-ttu-id="3cb60-114">Чтобы получить аналогичные результаты можно использовать функции [!INCLUDE[tsql](../../includes/tsql-md.md)] CAST и CONVERT.</span><span class="sxs-lookup"><span data-stu-id="3cb60-114">You can also use the [!INCLUDE[tsql](../../includes/tsql-md.md)] CAST and CONVERT functions to achieve the same results.</span></span>  
  
```  
SELECT ID, CAST(PointValue AS varchar)   
FROM dbo.Points;  
  
SELECT ID, CONVERT(varchar, PointValue)   
FROM dbo.Points;  
```  
  
 <span data-ttu-id="3cb60-115">Определяемый пользователем тип **Point** предоставляет свои координаты X и Y как свойства, которые затем можно выбрать по отдельности.</span><span class="sxs-lookup"><span data-stu-id="3cb60-115">The **Point** UDT exposes its X and Y coordinates as properties, which you can then select individually.</span></span> <span data-ttu-id="3cb60-116">Следующая инструкция [!INCLUDE[tsql](../../includes/tsql-md.md)] выбирает координаты X и Y отдельно:</span><span class="sxs-lookup"><span data-stu-id="3cb60-116">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement selects the X and Y coordinates separately:</span></span>  
  
```  
SELECT ID, PointValue.X AS xVal, PointValue.Y AS yVal   
FROM dbo.Points;  
```  
  
 <span data-ttu-id="3cb60-117">Свойства X и Y возвращают целочисленные значения, которые отображаются в результирующем наборе.</span><span class="sxs-lookup"><span data-stu-id="3cb60-117">The X and Y properties return an integer value, which is displayed in the result set.</span></span>  
  
```  
IDxValyVal  
----------  
134  
215  
3199  
```  
  
## <a name="working-with-variables"></a><span data-ttu-id="3cb60-118">Работа с переменными</span><span class="sxs-lookup"><span data-stu-id="3cb60-118">Working with Variables</span></span>  
 <span data-ttu-id="3cb60-119">Можно также работать с переменными с помощью инструкции DECLARE, чтобы присвоить значение переменной определяемому пользователем типу.</span><span class="sxs-lookup"><span data-stu-id="3cb60-119">You can work with variables using the DECLARE statement to assign a variable to a UDT type.</span></span> <span data-ttu-id="3cb60-120">Следующие инструкции присваивают значение с помощью инструкции [!INCLUDE[tsql](../../includes/tsql-md.md)] SET и отображают результаты путем вызова метода `ToString` определяемого пользователем типа для переменной:</span><span class="sxs-lookup"><span data-stu-id="3cb60-120">The following statements assign a value using the [!INCLUDE[tsql](../../includes/tsql-md.md)] SET statement and display the results by calling the UDT's `ToString` method on the variable:</span></span>  
  
```  
DECLARE @PointValue Point;  
SET @PointValue = (SELECT PointValue FROM dbo.Points  
    WHERE ID = 2);  
SELECT @PointValue.ToString() AS PointValue;  
```  
  
 <span data-ttu-id="3cb60-121">Результирующий набор отображает значение переменной:</span><span class="sxs-lookup"><span data-stu-id="3cb60-121">The result set displays the variable value:</span></span>  
  
```  
PointValue  
----------  
-1,5  
```  
  
 <span data-ttu-id="3cb60-122">Следующие инструкции [!INCLUDE[tsql](../../includes/tsql-md.md)] достигают такого же результата, используя инструкцию SELECT вместо SET, чтобы присвоить значение переменной:</span><span class="sxs-lookup"><span data-stu-id="3cb60-122">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] statements achieve the same result using SELECT rather than SET for the variable assignment:</span></span>  
  
```  
DECLARE @PointValue Point;  
SELECT @PointValue = PointValue FROM dbo.Points  
    WHERE ID = 2;  
SELECT @PointValue.ToString() AS PointValue;  
```  
  
 <span data-ttu-id="3cb60-123">Различие между использованием инструкций SELECT и SET для присваиваний значений переменных состоит в том, что SELECT позволяет присваивать значения нескольких переменных в одной инструкции SELECT, в то время как синтаксис SET требует для каждого присваивания переменной отдельной инструкции SET.</span><span class="sxs-lookup"><span data-stu-id="3cb60-123">The difference between using SELECT and SET for variable assignment is that SELECT allows you to assign multiple variables in one SELECT statement, whereas the SET syntax requires each variable assignment to have its own SET statement.</span></span>  
  
## <a name="comparing-data"></a><span data-ttu-id="3cb60-124">Сравнение данных</span><span class="sxs-lookup"><span data-stu-id="3cb60-124">Comparing Data</span></span>  
 <span data-ttu-id="3cb60-125">Можно использовать операторы сравнения, чтобы сравнить значения в определяемом пользователем типе, если при определении класса для свойства `IsByteOrdered` задано значение `true`.</span><span class="sxs-lookup"><span data-stu-id="3cb60-125">You can use comparison operators to compare values in your UDT if you have set the `IsByteOrdered` property to `true` when defining the class.</span></span> <span data-ttu-id="3cb60-126">Дополнительные сведения см. [в разделе Создание определяемого пользователем типа](creating-user-defined-types.md).</span><span class="sxs-lookup"><span data-stu-id="3cb60-126">For more information, see [Creating a User-Defined Type](creating-user-defined-types.md).</span></span>  
  
```  
SELECT ID, PointValue.ToString() AS Points   
FROM dbo.Points  
WHERE PointValue > CONVERT(Point, '2,2');  
```  
  
 <span data-ttu-id="3cb60-127">Можно сравнить внутренние значения определяемого пользователем типа независимо от значения свойства `IsByteOrdered`, если значения сами по себе сравнимы.</span><span class="sxs-lookup"><span data-stu-id="3cb60-127">You can compare internal values of the UDT regardless of the `IsByteOrdered` setting if the values themselves are comparable.</span></span> <span data-ttu-id="3cb60-128">Следующая инструкция [!INCLUDE[tsql](../../includes/tsql-md.md)] выбирает строки, в которых X больше, чем Y:</span><span class="sxs-lookup"><span data-stu-id="3cb60-128">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement selects rows where X is greater than Y:</span></span>  
  
```  
SELECT ID, PointValue.ToString() AS PointValue   
FROM dbo.Points  
WHERE PointValue.X < PointValue.Y;  
```  
  
 <span data-ttu-id="3cb60-129">Можно также использовать операторы сравнения с переменными, как показано в данном запросе, который ищет совпадения с PointValue.</span><span class="sxs-lookup"><span data-stu-id="3cb60-129">You can also use comparison operators with variables, as shown in this query that searches for a matching PointValue.</span></span>  
  
```  
DECLARE @ComparePoint Point;  
SET @ComparePoint = CONVERT(Point, '3,4');  
SELECT ID, PointValue.ToString() AS MatchingPoint   
FROM dbo.Points  
WHERE PointValue = @ComparePoint;  
```  
  
## <a name="invoking-udt-methods"></a><span data-ttu-id="3cb60-130">Вызов методов определяемого пользователем типа</span><span class="sxs-lookup"><span data-stu-id="3cb60-130">Invoking UDT Methods</span></span>  
 <span data-ttu-id="3cb60-131">Можно также вызывать методы, которые определены в определяемом пользователем типе [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3cb60-131">You can also invoke methods that are defined in your UDT in [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="3cb60-132">Класс **Point** содержит три метода: `Distance` , `DistanceFrom` и `DistanceFromXY` .</span><span class="sxs-lookup"><span data-stu-id="3cb60-132">The **Point** class contains three methods, `Distance`, `DistanceFrom`, and `DistanceFromXY`.</span></span> <span data-ttu-id="3cb60-133">Примеры кода, определяющие эти три метода, см. в разделе [программирование определяемых пользователем типов](creating-user-defined-types-coding.md).</span><span class="sxs-lookup"><span data-stu-id="3cb60-133">For the code listings defining these three methods, see [Coding User-Defined Types](creating-user-defined-types-coding.md).</span></span>  
  
 <span data-ttu-id="3cb60-134">Следующая инструкция [!INCLUDE[tsql](../../includes/tsql-md.md)] вызывает метод `PointValue.Distance`:</span><span class="sxs-lookup"><span data-stu-id="3cb60-134">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement calls the `PointValue.Distance` method:</span></span>  
  
```  
SELECT ID, PointValue.X AS [Point.X],   
    PointValue.Y AS [Point.Y],  
    PointValue.Distance() AS DistanceFromZero   
FROM dbo.Points;  
```  
  
 <span data-ttu-id="3cb60-135">Результаты отображаются в `Distance` столбце:</span><span class="sxs-lookup"><span data-stu-id="3cb60-135">The results are displayed in the `Distance` column:</span></span>  
  
```  
IDXYDistance  
------------------------  
1345  
2155.09901951359278  
319999.0050503762308  
```  
  
 <span data-ttu-id="3cb60-136">`DistanceFrom`Метод принимает аргумент типа данных **Point** и отображает расстояние от указанной точки до PointValue:</span><span class="sxs-lookup"><span data-stu-id="3cb60-136">The `DistanceFrom` method takes an argument of **Point** data type, and displays the distance from the specified point to the PointValue:</span></span>  
  
```  
SELECT ID, PointValue.ToString() AS Pnt,  
   PointValue.DistanceFrom(CONVERT(Point, '1,99')) AS DistanceFromPoint  
FROM dbo.Points;  
```  
  
 <span data-ttu-id="3cb60-137">Отображаются результаты работы метода `DistanceFrom` для каждой строки таблицы:</span><span class="sxs-lookup"><span data-stu-id="3cb60-137">The results display the results of the `DistanceFrom` method for each row in the table:</span></span>  
  
```  
ID PntDistanceFromPoint  
---------------------  
13,495.0210502993942  
21,594  
31,990  
```  
  
 <span data-ttu-id="3cb60-138">Метод `DistanceFromXY` принимает в качестве аргументов отдельно две точки:</span><span class="sxs-lookup"><span data-stu-id="3cb60-138">The `DistanceFromXY` method takes the points individually as arguments:</span></span>  
  
```  
SELECT ID, PointValue.X as X, PointValue.Y as Y,   
PointValue.DistanceFromXY(1, 99) AS DistanceFromXY   
FROM dbo.Points  
```  
  
 <span data-ttu-id="3cb60-139">Результирующий набор аналогичен результату работы метода `DistanceFrom`.</span><span class="sxs-lookup"><span data-stu-id="3cb60-139">The result set is the same as the `DistanceFrom` method.</span></span>  
  
## <a name="updating-data-in-a-udt-column"></a><span data-ttu-id="3cb60-140">Обновление данных в столбце определяемого пользователем типа</span><span class="sxs-lookup"><span data-stu-id="3cb60-140">Updating Data in a UDT Column</span></span>  
 <span data-ttu-id="3cb60-141">Чтобы обновлять данные в столбце определяемого пользователем типа, используется инструкция [!INCLUDE[tsql](../../includes/tsql-md.md)] UPDATE.</span><span class="sxs-lookup"><span data-stu-id="3cb60-141">To update data in a UDT column, use the [!INCLUDE[tsql](../../includes/tsql-md.md)] UPDATE statement.</span></span> <span data-ttu-id="3cb60-142">Также можно использовать метод определяемого пользователем типа, чтобы обновить состояние объекта.</span><span class="sxs-lookup"><span data-stu-id="3cb60-142">You can also use a method of the UDT to update the state of the object.</span></span> <span data-ttu-id="3cb60-143">Следующая инструкция [!INCLUDE[tsql](../../includes/tsql-md.md)] обновляет одну строку в таблице:</span><span class="sxs-lookup"><span data-stu-id="3cb60-143">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement updates a single row in the table:</span></span>  
  
```  
UPDATE dbo.Points  
SET PointValue = CAST('1,88' AS Point)  
WHERE ID = 3  
```  
  
 <span data-ttu-id="3cb60-144">Также можно обновлять элементы определяемого пользователем типа отдельно.</span><span class="sxs-lookup"><span data-stu-id="3cb60-144">You can also update UDT elements separately.</span></span> <span data-ttu-id="3cb60-145">Следующая инструкция [!INCLUDE[tsql](../../includes/tsql-md.md)] обновляет только координату Y:</span><span class="sxs-lookup"><span data-stu-id="3cb60-145">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement updates only the Y coordinate:</span></span>  
  
```  
UPDATE dbo.Points  
SET PointValue.Y = 99  
WHERE ID = 3  
```  
  
 <span data-ttu-id="3cb60-146">Если определяемый пользователем тип был определен с упорядочением байт, установленным в значение `true`, [!INCLUDE[tsql](../../includes/tsql-md.md)] может оценить столбец определяемого пользователем типа в предложении WHERE.</span><span class="sxs-lookup"><span data-stu-id="3cb60-146">If the UDT has been defined with byte ordering set to `true`, [!INCLUDE[tsql](../../includes/tsql-md.md)] can evaluate the UDT column in a WHERE clause.</span></span>  
  
```  
UPDATE dbo.Points  
SET PointValue = '4,5'  
WHERE PointValue = '3,4';  
```  
  
### <a name="updating-limitations"></a><span data-ttu-id="3cb60-147">Ограничения обновлений</span><span class="sxs-lookup"><span data-stu-id="3cb60-147">Updating Limitations</span></span>  
 <span data-ttu-id="3cb60-148">Нельзя обновить несколько свойств за раз с помощью инструкций [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3cb60-148">You cannot update multiple properties at once using [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="3cb60-149">Например, следующая инструкция UPDATE выполняется с ошибкой, так как нельзя использовать одно и то же имя столбца дважды в одной инструкции UDATE.</span><span class="sxs-lookup"><span data-stu-id="3cb60-149">For example, the following UPDATE statement fails with an error because you cannot use the same column name twice in one UDATE statement.</span></span>  
  
```  
UPDATE dbo.Points  
SET PointValue.X = 5, PointValue.Y = 99  
WHERE ID = 3  
```  
  
 <span data-ttu-id="3cb60-150">Чтобы обновить каждую точку отдельно, необходимо создать метод мутатора в сборке определяемого пользователем типа Point.</span><span class="sxs-lookup"><span data-stu-id="3cb60-150">To update each point individually, you would need to create a mutator method in the Point UDT assembly.</span></span> <span data-ttu-id="3cb60-151">Можно затем обратиться к методу мутатора в инструкции [!INCLUDE[tsql](../../includes/tsql-md.md)] UPDATE для обновления объекта, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="3cb60-151">You can then invoke the mutator method to update the object in a [!INCLUDE[tsql](../../includes/tsql-md.md)] UPDATE statement, as in the following:</span></span>  
  
```  
UPDATE dbo.Points  
SET PointValue.SetXY(5, 99)  
WHERE ID = 3  
```  
  
## <a name="deleting-data-in-a-udt-column"></a><span data-ttu-id="3cb60-152">Удаление данных из столбца определяемого пользователем типа</span><span class="sxs-lookup"><span data-stu-id="3cb60-152">Deleting Data in a UDT Column</span></span>  
 <span data-ttu-id="3cb60-153">Чтобы удалить данные в определяемом пользователем типе, используется инструкция [!INCLUDE[tsql](../../includes/tsql-md.md)] DELETE.</span><span class="sxs-lookup"><span data-stu-id="3cb60-153">To delete data in a UDT, use the [!INCLUDE[tsql](../../includes/tsql-md.md)] DELETE statement.</span></span> <span data-ttu-id="3cb60-154">Следующая инструкция удаляет все строки из таблицы, которые удовлетворяют критерию, указанному в предложении WHERE.</span><span class="sxs-lookup"><span data-stu-id="3cb60-154">The following statement deletes all rows in the table that match the criteria specified in the WHERE clause.</span></span> <span data-ttu-id="3cb60-155">Если предложение WHERE пропущено в инструкции DELETE, будут удалены все строки таблицы.</span><span class="sxs-lookup"><span data-stu-id="3cb60-155">If you omit the WHERE clause in a DELETE statement, all rows in the table will be deleted.</span></span>  
  
```  
DELETE FROM dbo.Points  
WHERE PointValue = CAST('1,99' AS Point)  
```  
  
 <span data-ttu-id="3cb60-156">Инструкция UPDATE используется, если необходимо удалить значения в столбце определяемого пользователем типа и оставить другие значения строки без изменений.</span><span class="sxs-lookup"><span data-stu-id="3cb60-156">Use the UPDATE statement if you want to remove the values in a UDT column while leaving other row values intact.</span></span> <span data-ttu-id="3cb60-157">Этот пример задает столбцу PointValue значение NULL.</span><span class="sxs-lookup"><span data-stu-id="3cb60-157">This example sets the PointValue to null.</span></span>  
  
```  
UPDATE dbo.Points  
SET PointValue = null  
WHERE ID = 2  
```  
  
## <a name="see-also"></a><span data-ttu-id="3cb60-158">См. также:</span><span class="sxs-lookup"><span data-stu-id="3cb60-158">See Also</span></span>  
 [<span data-ttu-id="3cb60-159">Работа с определяемыми пользователем типами в SQL Server</span><span class="sxs-lookup"><span data-stu-id="3cb60-159">Working with User-Defined Types in SQL Server</span></span>](working-with-user-defined-types-in-sql-server.md)  
  
  
