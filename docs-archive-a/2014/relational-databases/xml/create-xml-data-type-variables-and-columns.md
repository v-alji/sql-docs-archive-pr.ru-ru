---
title: Создание переменных и столбцов типа данных XML | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- xml data type [SQL Server], variables
- xml data type [SQL Server], columns
ms.assetid: 8994ab6e-5519-4ba2-97a1-fac8af6f72db
author: rothja
ms.author: jroth
ms.openlocfilehash: 08b79888eb47634deaccc910b2ea3c93800b7c78
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87738072"
---
# <a name="create-xml-data-type-variables-and-columns"></a><span data-ttu-id="d3e56-102">Создание переменных и столбцов типа данных XML</span><span class="sxs-lookup"><span data-stu-id="d3e56-102">Create XML Data Type Variables and Columns</span></span>
  <span data-ttu-id="d3e56-103">Тип данных `xml` — это встроенный в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] тип данных, несколько напоминающий другие встроенные типы данных, такие как `int` и `varchar`.</span><span class="sxs-lookup"><span data-stu-id="d3e56-103">The `xml` data type is a built-in data type in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and is somewhat similar to other built-in types such as `int` and `varchar`.</span></span> <span data-ttu-id="d3e56-104">Как и в случае с другими встроенными типами, тип данных можно использовать в `xml` качестве типа столбца при создании таблицы в качестве типа переменной, типа параметра, типа возвращаемого функцией значения, а также в случае [приведения и преобразования](/sql/t-sql/functions/cast-and-convert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="d3e56-104">As with other built-in types, you can use the `xml` data type as a column type when you create a table as a variable type, a parameter type, a function-return type, or in [CAST and CONVERT](/sql/t-sql/functions/cast-and-convert-transact-sql).</span></span>  
  
## <a name="creating-columns-and-variables"></a><span data-ttu-id="d3e56-105">Создание столбцов и переменных</span><span class="sxs-lookup"><span data-stu-id="d3e56-105">Creating Columns and Variables</span></span>  
 <span data-ttu-id="d3e56-106">Чтобы создать в таблице столбец типа `xml` , воспользуйтесь инструкцией `CREATE TABLE` , приведенной в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="d3e56-106">To create an `xml` type column as part of a table, use a `CREATE TABLE` statement, as shown in the following example:</span></span>  
  
```  
CREATE TABLE T1(Col1 int primary key, Col2 xml)   
```  
  
 <span data-ttu-id="d3e56-107">Функция `DECLARE statement` , приведенная в следующем примере, позволяет создать переменную типа `xml` .</span><span class="sxs-lookup"><span data-stu-id="d3e56-107">You can use a `DECLARE statement` to create a variable of `xml` type, as the following example shows.</span></span>  
  
```  
DECLARE @x xml   
```  
  
 <span data-ttu-id="d3e56-108">Создайте типизированную переменную `xml` , указав коллекцию XML-схем, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="d3e56-108">Create a typed `xml` variable by specifying an XML schema collection, as shown in the following example.</span></span>  
  
```  
DECLARE @x xml (Sales.StoreSurveySchemaCollection)  
```  
  
 <span data-ttu-id="d3e56-109">Чтобы передать параметр типа `xml` хранимой процедуре, воспользуйтесь инструкцией `CREATE PROCEDURE` , как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="d3e56-109">To pass an `xml` type parameter to a stored procedure, use a `CREATE PROCEDURE` statement, as shown in the following example.</span></span>  
  
```  
CREATE PROCEDURE SampleProc(@XmlDoc xml) AS ...   
```  
  
 <span data-ttu-id="d3e56-110">Чтобы выполнять запросы к экземплярам XML, хранимым в столбцах, параметрах и переменных, можно использовать XQuery.</span><span class="sxs-lookup"><span data-stu-id="d3e56-110">You can use XQuery to query XML instances stored in columns, parameters, or variables.</span></span> <span data-ttu-id="d3e56-111">Чтобы обновлять экземпляры XML, также можно использовать язык XML DML.</span><span class="sxs-lookup"><span data-stu-id="d3e56-111">You can also use the XML Data Manipulation Language (XML DML) to apply updates to the XML instances.</span></span> <span data-ttu-id="d3e56-112">Поскольку стандарт XQuery на момент разработки не определял язык XQuery DML, в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] были введены расширения [языка XML DML](/sql/t-sql/xml/xml-data-modification-language-xml-dml) к XQuery.</span><span class="sxs-lookup"><span data-stu-id="d3e56-112">Because the XQuery standard did not define XQuery DML at the time of development, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] introduces [XML Data Modification Language](/sql/t-sql/xml/xml-data-modification-language-xml-dml) extensions to XQuery.</span></span> <span data-ttu-id="d3e56-113">Эти расширения позволяют выполнять операции вставки, обновления и удаления.</span><span class="sxs-lookup"><span data-stu-id="d3e56-113">These extensions allow you to perform insert, update, and delete operations.</span></span>  
  
## <a name="assigning-defaults"></a><span data-ttu-id="d3e56-114">Назначение значений по умолчанию</span><span class="sxs-lookup"><span data-stu-id="d3e56-114">Assigning Defaults</span></span>  
 <span data-ttu-id="d3e56-115">В таблице столбцу типа `xml` можно назначить экземпляр XML по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d3e56-115">In a table, you can assign a default XML instance to a column of `xml` type.</span></span> <span data-ttu-id="d3e56-116">Экземпляр XML по умолчанию можно указать двумя способами: при помощи константы XML или явного приведения к типу `xml`.</span><span class="sxs-lookup"><span data-stu-id="d3e56-116">You can provide the default XML in one of two ways: by using an XML constant, or by using an explicit cast to the `xml` type.</span></span>  
  
 <span data-ttu-id="d3e56-117">Чтобы указать в качестве экземпляра XML по умолчанию константу XML, воспользуйтесь синтаксической конструкцией из следующего примера.</span><span class="sxs-lookup"><span data-stu-id="d3e56-117">To provide the default XML as an XML constant, use syntax as shown in the following example.</span></span> <span data-ttu-id="d3e56-118">Обратите внимание, что строка неявно приведена к типу `xml`.</span><span class="sxs-lookup"><span data-stu-id="d3e56-118">Note that the string is implicitly CAST to `xml` type.</span></span>  
  
```  
CREATE TABLE T (XmlColumn xml default N'<element1/><element2/>')  
```  
  
 <span data-ttu-id="d3e56-119">Чтобы указать экземпляр XML по умолчанию посредством явного преобразования `CAST` в тип `xml`, воспользуйтесь синтаксической конструкцией из следующего примера.</span><span class="sxs-lookup"><span data-stu-id="d3e56-119">To provide the default XML as an explicit `CAST` to `xml`, use syntax as shown in the following example.</span></span>  
  
```  
CREATE TABLE T (XmlColumn xml   
                  default CAST(N'<element1/><element2/>' AS xml))  
```  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="d3e56-120">поддерживает ограничения NULL и NOT NULL для столбцов типа `xml`.</span><span class="sxs-lookup"><span data-stu-id="d3e56-120">also supports NULL and NOT NULL constraints on columns of `xml` type.</span></span> <span data-ttu-id="d3e56-121">Пример:</span><span class="sxs-lookup"><span data-stu-id="d3e56-121">For example:</span></span>  
  
```  
CREATE TABLE T (XmlColumn xml NOT NULL)  
```  
  
## <a name="specifying-constraints"></a><span data-ttu-id="d3e56-122">Указание ограничений</span><span class="sxs-lookup"><span data-stu-id="d3e56-122">Specifying Constraints</span></span>  
 <span data-ttu-id="d3e56-123">При создании столбцов типа `xml` можно устанавливать ограничения уровня столбца или уровня таблицы.</span><span class="sxs-lookup"><span data-stu-id="d3e56-123">When you create columns of `xml` type, you can define column-level or table-level constraints.</span></span> <span data-ttu-id="d3e56-124">Используйте ограничения в следующих ситуациях.</span><span class="sxs-lookup"><span data-stu-id="d3e56-124">Use constraints in the following situations:</span></span>  
  
-   <span data-ttu-id="d3e56-125">Бизнес-правила не могут быть выражены в XML-схемах.</span><span class="sxs-lookup"><span data-stu-id="d3e56-125">Your business rules cannot be expressed in XML schemas.</span></span> <span data-ttu-id="d3e56-126">Допустим, что адреса доставки заказов магазином цветов должны находиться не далее 90 километров от магазина.</span><span class="sxs-lookup"><span data-stu-id="d3e56-126">For example, the delivery address of a flower shop must be within 50 miles of its business location.</span></span> <span data-ttu-id="d3e56-127">Это требование можно выразить в форме ограничения XML-столбца.</span><span class="sxs-lookup"><span data-stu-id="d3e56-127">This can be written as a constraint on the XML column.</span></span> <span data-ttu-id="d3e56-128">Эти ограничения могут содержать методы для обработки данных типа `xml`.</span><span class="sxs-lookup"><span data-stu-id="d3e56-128">The constraint may involve `xml` data type methods.</span></span>  
  
-   <span data-ttu-id="d3e56-129">В ограничении фигурируют другие столбцы таблицы, имеющие тип XML или другой тип.</span><span class="sxs-lookup"><span data-stu-id="d3e56-129">Your constraint involves other XML or non-XML columns in the table.</span></span> <span data-ttu-id="d3e56-130">В качестве примера можно привести требование, согласно которому идентификатор заказчика (`/Customer/@CustId`), хранимый в экземпляре XML, должен соответствовать значению из реляционного столбца CustomerID.</span><span class="sxs-lookup"><span data-stu-id="d3e56-130">An example is the enforcement of the ID of a Customer (`/Customer/@CustId`) found in an XML instance to match the value in a relational CustomerID column.</span></span>  
  
 <span data-ttu-id="d3e56-131">Ограничения можно указать для типизированных и нетипизированных столбцов `xml`.</span><span class="sxs-lookup"><span data-stu-id="d3e56-131">You can specify constraints for typed or untyped `xml` data type columns.</span></span> <span data-ttu-id="d3e56-132">Однако использование [методов типа данных xml](/sql/t-sql/xml/xml-data-type-methods) при указании ограничений невозможно.</span><span class="sxs-lookup"><span data-stu-id="d3e56-132">However, you cannot use the [XML data type methods](/sql/t-sql/xml/xml-data-type-methods) when you specify constraints.</span></span> <span data-ttu-id="d3e56-133">Кроме того, обратите внимание, что тип данных `xml` не поддерживает следующие ограничения столбцов и таблиц:</span><span class="sxs-lookup"><span data-stu-id="d3e56-133">Also, note that the `xml` data type does not support the following column and table constraints:</span></span>  
  
-   <span data-ttu-id="d3e56-134">PRIMARY KEY и FOREIGN KEY</span><span class="sxs-lookup"><span data-stu-id="d3e56-134">PRIMARY KEY/ FOREIGN KEY</span></span>  
  
-   <span data-ttu-id="d3e56-135">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="d3e56-135">UNIQUE</span></span>  
  
-   <span data-ttu-id="d3e56-136">COLLATE</span><span class="sxs-lookup"><span data-stu-id="d3e56-136">COLLATE</span></span>  
  
     <span data-ttu-id="d3e56-137">XML использует свою собственную кодировку.</span><span class="sxs-lookup"><span data-stu-id="d3e56-137">XML provides its own encoding.</span></span> <span data-ttu-id="d3e56-138">Параметры сортировки применимы только к строковым типам.</span><span class="sxs-lookup"><span data-stu-id="d3e56-138">Collations apply to string types only.</span></span> <span data-ttu-id="d3e56-139">Тип данных `xml` к таковым не относится.</span><span class="sxs-lookup"><span data-stu-id="d3e56-139">The `xml` data type is not a string type.</span></span> <span data-ttu-id="d3e56-140">Однако у него есть строковое представление, и его можно приводить к строковым типам данных и обратно.</span><span class="sxs-lookup"><span data-stu-id="d3e56-140">However, it does have string representation and allows casting to and from string data types.</span></span>  
  
-   <span data-ttu-id="d3e56-141">RULE</span><span class="sxs-lookup"><span data-stu-id="d3e56-141">RULE</span></span>  
  
 <span data-ttu-id="d3e56-142">Помимо использования ограничений, можно создать оболочку, то есть определяемую пользователем функцию, являющуюся интерфейсом к методу типа данных `xml`, и указать определяемую пользователем функцию в проверочном ограничении, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="d3e56-142">An alternative to using constraints is to create a wrapper, user-defined function to wrap the `xml` data type method and specify user-defined function in the check constraint as shown in the following example.</span></span>  
  
 <span data-ttu-id="d3e56-143">В этом примере ограничение на столбец `Col2` указывает, что каждый хранимый в этом столбце экземпляр XML должен иметь элемент `<ProductDescription>` , содержащий атрибут `ProductID` .</span><span class="sxs-lookup"><span data-stu-id="d3e56-143">In the following example, the constraint on `Col2` specifies that each XML instance stored in this column must have a `<ProductDescription>` element that contains a `ProductID` attribute.</span></span> <span data-ttu-id="d3e56-144">Это ограничение принудительно применяется с помощью пользовательской функции:</span><span class="sxs-lookup"><span data-stu-id="d3e56-144">This constraint is enforced by this user-defined function:</span></span>  
  
```  
CREATE FUNCTION my_udf(@var xml) returns bit  
AS BEGIN   
RETURN @var.exist('/ProductDescription/@ProductID')  
END  
GO  
```  
  
 <span data-ttu-id="d3e56-145">Обратите внимание, что метод `exist()` типа данных `xml` возвращает значение `1` , если элемент `<ProductDescription>` в экземпляре содержит атрибут `ProductID` .</span><span class="sxs-lookup"><span data-stu-id="d3e56-145">Note that the `exist()` method of the `xml` data type returns `1` if the `<ProductDescription>` element in the instance contains the `ProductID` attribute.</span></span> <span data-ttu-id="d3e56-146">В противном случае возвращается значение `0`.</span><span class="sxs-lookup"><span data-stu-id="d3e56-146">Otherwise, it returns `0`.</span></span>  
  
 <span data-ttu-id="d3e56-147">Теперь возможно создание таблицы с ограничениями на уровне столбцов, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="d3e56-147">Now, you can create a table with a column-level constraint as follows:</span></span>  
  
```  
CREATE TABLE T (  
    Col1 int primary key,   
    Col2 xml check(dbo.my_udf(Col2)=1))  
GO  
```  
  
 <span data-ttu-id="d3e56-148">Эта операция вставки выполняется успешно:</span><span class="sxs-lookup"><span data-stu-id="d3e56-148">The following insert succeeds:</span></span>  
  
```  
INSERT INTO T values(1,'<ProductDescription ProductID="1" />')  
```  
  
 <span data-ttu-id="d3e56-149">Из-за ограничения следующая операция вставки не будет выполнена:</span><span class="sxs-lookup"><span data-stu-id="d3e56-149">Because of the constraint, the following insert fails:</span></span>  
  
```  
INSERT INTO T values(1,'<Product />')  
```  
  
## <a name="same-or-different-table"></a><span data-ttu-id="d3e56-150">Та же таблица или другая</span><span class="sxs-lookup"><span data-stu-id="d3e56-150">Same or Different Table</span></span>  
 <span data-ttu-id="d3e56-151">`xml`Столбец типа данных может быть создан в таблице, содержащей другие реляционные столбцы, или в отдельной таблице с отношением внешнего ключа к главной таблице.</span><span class="sxs-lookup"><span data-stu-id="d3e56-151">An `xml` data type column can be created in a table that contains other relational columns, or in a separate table with a foreign key relationship to a main table.</span></span>  
  
 <span data-ttu-id="d3e56-152">Создайте `xml` столбец типа данных в той же таблице, если выполняется одно из следующих условий.</span><span class="sxs-lookup"><span data-stu-id="d3e56-152">Create an `xml` data type column in the same table when one of the following conditions is true:</span></span>  
  
-   <span data-ttu-id="d3e56-153">Приложение извлекает данные из XML-столбца и не нуждается в том, чтобы для него был создан XML-индекс.</span><span class="sxs-lookup"><span data-stu-id="d3e56-153">Your application performs data retrieval on the XML column and does not require an XML index on the XML column.</span></span>  
  
-   <span data-ttu-id="d3e56-154">Для столбца типа `xml` требуется создание XML-индекса, причем первичный ключ главной таблицы идентичен ее ключу кластеризации.</span><span class="sxs-lookup"><span data-stu-id="d3e56-154">You want to build an XML index on the `xml` data type column and the primary key of the main table is the same as its clustering key.</span></span> <span data-ttu-id="d3e56-155">Дополнительные сведения см в разделе [XML-индексы (SQL Server)](xml-indexes-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="d3e56-155">For more information, see [XML Indexes &#40;SQL Server&#41;](xml-indexes-sql-server.md).</span></span>  
  
 <span data-ttu-id="d3e56-156">Столбец типа `xml` следует создавать в отдельной таблице, если выполняются перечисленные ниже условия.</span><span class="sxs-lookup"><span data-stu-id="d3e56-156">Create the `xml` data type column in a separate table if the following conditions are true:</span></span>  
  
-   <span data-ttu-id="d3e56-157">Для столбца типа `xml` требуется создание XML-индекса, но первичный ключ главной таблицы отличается от ее ключа кластеризации, главная таблица не имеет первичного ключа или главная таблица является кучей (нет ключа кластеризации).</span><span class="sxs-lookup"><span data-stu-id="d3e56-157">You want to build an XML index on the `xml` data type column, but the primary key of the main table is different from its clustering key, or the main table does not have a primary key, or the main table is a heap (no clustering key).</span></span> <span data-ttu-id="d3e56-158">Это может иметь место, если главная таблица уже существует.</span><span class="sxs-lookup"><span data-stu-id="d3e56-158">This may be true if the main table already exists.</span></span>  
  
-   <span data-ttu-id="d3e56-159">Не требуется замедлять просмотр таблицы из-за наличия в ней XML-столбца.</span><span class="sxs-lookup"><span data-stu-id="d3e56-159">You do not want table scans to slow down because of the presence of the XML column in the table.</span></span> <span data-ttu-id="d3e56-160">Он занимает место независимо от того, хранится ли он в строке или вне строки.</span><span class="sxs-lookup"><span data-stu-id="d3e56-160">This uses space whether it is stored in-row or out-of-row.</span></span>  
  
  
