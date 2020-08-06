---
title: Выражения запросов и унифицированные имена ресурсов | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: scripting
ms.topic: conceptual
helpviewer_keywords:
- query expressions
- unique resource names
- URN
ms.assetid: e0d30dbe-7daf-47eb-8412-1b96792b6fb9
author: stevestein
ms.author: sstein
ms.openlocfilehash: db6e311dd7d8a824b0e2f22e538e15eefa9fd9ab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658869"
---
# <a name="query-expressions-and-uniform-resource-names"></a><span data-ttu-id="04c3c-102">Выражения запросов и универсальные имена ресурсов</span><span class="sxs-lookup"><span data-stu-id="04c3c-102">Query Expressions and Uniform Resource Names</span></span>
  <span data-ttu-id="04c3c-103">В моделях объектов SMO [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] и оснастках [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] PowerShell используется два типа строк выражений, которые похожи на выражения XPath.</span><span class="sxs-lookup"><span data-stu-id="04c3c-103">The [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Management Object (SMO) models and [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] PowerShell snap-ins use two types of expression strings that are similar to XPath expressions.</span></span> <span data-ttu-id="04c3c-104">Выражения запроса — это строки, которые указывают набор условий, используемых для перечисления одного или нескольких объектов в иерархии объектной модели.</span><span class="sxs-lookup"><span data-stu-id="04c3c-104">Query expressions are strings that specify a set of criteria used to enumerate one or more objects in an object model hierarchy.</span></span> <span data-ttu-id="04c3c-105">Универсальное имя ресурса (URN) — это конкретный тип строки выражения запроса, который уникально определяет один объект.</span><span class="sxs-lookup"><span data-stu-id="04c3c-105">A Uniform Resource Name (URN) is a specific type of query expression string that uniquely identifies a single object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04c3c-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="04c3c-106">Syntax</span></span>  
  
```
      Object1  
      [<FilterExpression1>]/ ... /ObjectN[<FilterExpressionN>]<FilterExpression>::=  
<PropertyExpression> [and <PropertyExpression>][...n]  
  
<PropertyExpression>::=@BooleanPropertyName=true()  
 | @BooleanPropertyName=false()  
 | contains(@StringPropertyName, 'PatternString')  
  | @StringPropertyName='String'  
 | @DatePropertyName=datetime('DateString')  
 | is_null(@PropertyName)  
 | not(<PropertyExpression>)  
```  
  
## <a name="arguments"></a><span data-ttu-id="04c3c-107">Аргументы</span><span class="sxs-lookup"><span data-stu-id="04c3c-107">Arguments</span></span>  
 <span data-ttu-id="04c3c-108">*Объект*</span><span class="sxs-lookup"><span data-stu-id="04c3c-108">*Object*</span></span>  
 <span data-ttu-id="04c3c-109">Указывает тип объекта, который представлен в узле строки выражения.</span><span class="sxs-lookup"><span data-stu-id="04c3c-109">Specifies the type of object that is represented at that node of the expression string.</span></span> <span data-ttu-id="04c3c-110">Каждый объект представляет класс коллекции из этих пространств имен объектной модели SMO.</span><span class="sxs-lookup"><span data-stu-id="04c3c-110">Each object represents a collection class from these SMO object model namespaces:</span></span>  
  
 <xref:Microsoft.SqlServer.Management.Smo>  
  
 <xref:Microsoft.SqlServer.Management.Smo.Agent>  
  
 <xref:Microsoft.SqlServer.Management.Smo.Broker>  
  
 <xref:Microsoft.SqlServer.Management.Smo.Mail>  
  
 <xref:Microsoft.SqlServer.Management.Dmf>  
  
 <xref:Microsoft.SqlServer.Management.Facets>  
  
 <xref:Microsoft.SqlServer.Management.RegisteredServers>  
  
 <xref:Microsoft.SqlServer.Management.Smo.RegSvrEnum>  
  
 <span data-ttu-id="04c3c-111">Например, укажите имя Server для класса **ServerCollection** и имя Database для класса **DatabaseCollection** .</span><span class="sxs-lookup"><span data-stu-id="04c3c-111">For example, specify Server for the **ServerCollection** class, Database for the **DatabaseCollection** class.</span></span>  
  
 <span data-ttu-id="04c3c-112">\@*PropertyName*</span><span class="sxs-lookup"><span data-stu-id="04c3c-112">\@*PropertyName*</span></span>  
 <span data-ttu-id="04c3c-113">Указывает имя одного из свойств класса, связанного с объектом, который задан в *Object*.</span><span class="sxs-lookup"><span data-stu-id="04c3c-113">Specifies the name of one of the properties of the class that is associated with the object specified in *Object*.</span></span> <span data-ttu-id="04c3c-114">Имя свойства должно начинаться с префикса \@.</span><span class="sxs-lookup"><span data-stu-id="04c3c-114">The name of the property must be prefixed with the \@ character.</span></span> <span data-ttu-id="04c3c-115">Например, укажите \@ isansinull класса Database для свойства **Isansinull класса Database**класса **базы данных** .</span><span class="sxs-lookup"><span data-stu-id="04c3c-115">For example, specify \@IsAnsiNull for the **Database** class property **IsAnsiNull**.</span></span>  
  
 <span data-ttu-id="04c3c-116">\@*Булеанпропертинаме*= true ()</span><span class="sxs-lookup"><span data-stu-id="04c3c-116">\@*BooleanPropertyName*=true()</span></span>  
 <span data-ttu-id="04c3c-117">Перечисляет все объекты, где указанное логическое свойство имеет значение TRUE.</span><span class="sxs-lookup"><span data-stu-id="04c3c-117">Enumerates all objects where the specified Boolean property is set to TRUE.</span></span>  
  
 <span data-ttu-id="04c3c-118">\@*Булеанпропертинаме*= false ()</span><span class="sxs-lookup"><span data-stu-id="04c3c-118">\@*BooleanPropertyName*=false()</span></span>  
 <span data-ttu-id="04c3c-119">Перечисляет все объекты, где указанное логическое свойство имеет значение FALSE.</span><span class="sxs-lookup"><span data-stu-id="04c3c-119">Enumerates all objects where the specified Boolean property is set to FALSE.</span></span>  
  
 <span data-ttu-id="04c3c-120">contains(\@*StringPropertyName*, '*PatternString*')</span><span class="sxs-lookup"><span data-stu-id="04c3c-120">contains(\@*StringPropertyName*, '*PatternString*')</span></span>  
 <span data-ttu-id="04c3c-121">Перечисляет все объекты, указанное строковое свойство которых содержит хотя бы одно вхождение набора символов, который указан в '*PatternString*'.</span><span class="sxs-lookup"><span data-stu-id="04c3c-121">Enumerates all objects where the specified string property contains at least one occurrence of the set of characters that is specified in '*PatternString*'.</span></span>  
  
 <span data-ttu-id="04c3c-122">\@*StringPropertyName*='*PatternString*'</span><span class="sxs-lookup"><span data-stu-id="04c3c-122">\@*StringPropertyName*='*PatternString*'</span></span>  
 <span data-ttu-id="04c3c-123">Перечисляет все объекты, значение указанного строкового свойства которых точно такое же, как комбинация символов, указанная в '*PatternString*'.</span><span class="sxs-lookup"><span data-stu-id="04c3c-123">Enumerates all objects where the value of the specified string property is exactly the same as the character pattern that is specified in '*PatternString*'.</span></span>  
  
 <span data-ttu-id="04c3c-124">\@*DatePropertyName*= datetime('*DateString*')</span><span class="sxs-lookup"><span data-stu-id="04c3c-124">\@*DatePropertyName*= datetime('*DateString*')</span></span>  
 <span data-ttu-id="04c3c-125">Перечисляет все объекты, значение указанного свойства даты которых соответствует дате, указанной в '*DateString*'.</span><span class="sxs-lookup"><span data-stu-id="04c3c-125">Enumerates all objects where the value of the specified date property matches the date that is specified in '*DateString*'.</span></span> <span data-ttu-id="04c3c-126">Значение*DateString* должно иметь формат гггг-мм-дд чч:ми:сс.ммм</span><span class="sxs-lookup"><span data-stu-id="04c3c-126">*DateString* must follow the format yyyy-mm-dd hh:mi:ss.mmm</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="04c3c-127">гггг</span><span class="sxs-lookup"><span data-stu-id="04c3c-127">yyyy</span></span>|<span data-ttu-id="04c3c-128">Год из четырех цифр.</span><span class="sxs-lookup"><span data-stu-id="04c3c-128">Four digit year.</span></span>|  
|<span data-ttu-id="04c3c-129">ММ</span><span class="sxs-lookup"><span data-stu-id="04c3c-129">mm</span></span>|<span data-ttu-id="04c3c-130">Месяц из двух цифр (от 01 до 12).</span><span class="sxs-lookup"><span data-stu-id="04c3c-130">Two digit month (01 through 12).</span></span>|  
|<span data-ttu-id="04c3c-131">дд</span><span class="sxs-lookup"><span data-stu-id="04c3c-131">dd</span></span>|<span data-ttu-id="04c3c-132">День из двух цифр (от 01 до 31).</span><span class="sxs-lookup"><span data-stu-id="04c3c-132">Two digit date (01 through 31).</span></span>|  
|<span data-ttu-id="04c3c-133">hh</span><span class="sxs-lookup"><span data-stu-id="04c3c-133">hh</span></span>|<span data-ttu-id="04c3c-134">Час из двух цифр в 24-часовом формате (от 01 до 23).</span><span class="sxs-lookup"><span data-stu-id="04c3c-134">Two digit hour using a 24 hour clock (01 through 23).</span></span>|  
|<span data-ttu-id="04c3c-135">ми</span><span class="sxs-lookup"><span data-stu-id="04c3c-135">mi</span></span>|<span data-ttu-id="04c3c-136">Минута из двух цифр (от 01 до 59).</span><span class="sxs-lookup"><span data-stu-id="04c3c-136">Two digit minutes (01 through 59).</span></span>|  
|<span data-ttu-id="04c3c-137">сс</span><span class="sxs-lookup"><span data-stu-id="04c3c-137">ss</span></span>|<span data-ttu-id="04c3c-138">Секунда из двух цифр (от 01 до 59).</span><span class="sxs-lookup"><span data-stu-id="04c3c-138">Two digit seconds (01 through 59).</span></span>|  
|<span data-ttu-id="04c3c-139">ммм</span><span class="sxs-lookup"><span data-stu-id="04c3c-139">mmm</span></span>|<span data-ttu-id="04c3c-140">Количество миллисекунд (от 001 до 999).</span><span class="sxs-lookup"><span data-stu-id="04c3c-140">Number of milliseconds (001 through 999).</span></span>|  
  
 <span data-ttu-id="04c3c-141">Даты, указанные в этом формате, можно вычислять с любым форматом даты, хранящимся в [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="04c3c-141">The dates that are specified in this format can be evaluated against any date format that is stored in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="04c3c-142">is_null(\@*PropertyName*)</span><span class="sxs-lookup"><span data-stu-id="04c3c-142">is_null(\@*PropertyName*)</span></span>  
 <span data-ttu-id="04c3c-143">Перечисляет все объекты, где указанное свойство имеет значение NULL.</span><span class="sxs-lookup"><span data-stu-id="04c3c-143">Enumerates all objects where the specified property has a value of NULL.</span></span>  
  
 <span data-ttu-id="04c3c-144">not ( \<*PropertyExpression*> )</span><span class="sxs-lookup"><span data-stu-id="04c3c-144">not(\<*PropertyExpression*>)</span></span>  
 <span data-ttu-id="04c3c-145">Инвертирует значение вычисленного выражения *PropertyExpression*, перечисляя все объекты, не соответствующие условию, заданному в *PropertyExpression*.</span><span class="sxs-lookup"><span data-stu-id="04c3c-145">Negates the evaluation value of the *PropertyExpression*, enumerating all objects that do not match the condition specified in *PropertyExpression*.</span></span> <span data-ttu-id="04c3c-146">Например, not(contains(\@Name, 'xyz')) перечисляет все объекты, в именах которых нет строки xyz.</span><span class="sxs-lookup"><span data-stu-id="04c3c-146">For example, not(contains(\@Name, 'xyz')) enumerates all objects that do not have the string xyz in their names.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="04c3c-147">Remarks</span><span class="sxs-lookup"><span data-stu-id="04c3c-147">Remarks</span></span>  
 <span data-ttu-id="04c3c-148">Выражения запроса — это строки, которые перечисляют узлы в иерархии моделей SMO.</span><span class="sxs-lookup"><span data-stu-id="04c3c-148">Query expressions are strings that enumerate the nodes in an SMO model hierarchy.</span></span> <span data-ttu-id="04c3c-149">У каждого узла есть критерий фильтра, задающий условие для определения того, какие объекты в этом узле будут перечисляться.</span><span class="sxs-lookup"><span data-stu-id="04c3c-149">Each node has a filter expression that specifies the criteria for determining which objects at that node are enumerated.</span></span> <span data-ttu-id="04c3c-150">Выражения запроса моделируются на языке выражений XPath.</span><span class="sxs-lookup"><span data-stu-id="04c3c-150">Query expressions are modeled on the XPath expression language.</span></span> <span data-ttu-id="04c3c-151">Выражения запроса представляют собой небольшое подмножество выражений XPath, кроме того, в них есть некоторые выражения, которых нет в XPath.</span><span class="sxs-lookup"><span data-stu-id="04c3c-151">Query expressions implement a small subset of the expressions that are supported by XPath, and also have some extensions that are not found in XPath.</span></span> <span data-ttu-id="04c3c-152">Выражения XPath — это строки, которые указывают набор критериев, используемых для перечисления одного или нескольких тегов в XML-документе.</span><span class="sxs-lookup"><span data-stu-id="04c3c-152">XPath expressions are strings that specify a set of criteria that are used to enumerate one or more of the tags in an XML document.</span></span> <span data-ttu-id="04c3c-153">Дополнительные сведения об XPath см. в разделе [Язык W3C XPath](http://www.w3.org/TR/xpath20/).</span><span class="sxs-lookup"><span data-stu-id="04c3c-153">For more information about XPath, see [W3C XPath Language](http://www.w3.org/TR/xpath20/).</span></span>  
  
 <span data-ttu-id="04c3c-154">Выражения запроса должны начинаться с абсолютной ссылки на объект сервера.</span><span class="sxs-lookup"><span data-stu-id="04c3c-154">Query expressions must start with an absolute reference to the Server object.</span></span> <span data-ttu-id="04c3c-155">Относительные выражения, начинающиеся с символа /, не допустимы.</span><span class="sxs-lookup"><span data-stu-id="04c3c-155">Relative expressions with a leading / are not allowed.</span></span> <span data-ttu-id="04c3c-156">Последовательность объектов, указанных в выражении запроса, должна соответствовать иерархии коллекции объектов в связанной модели объекта.</span><span class="sxs-lookup"><span data-stu-id="04c3c-156">The sequence of objects that are specified in a query expression must follow the hierarchy of collection objects in the associated object model.</span></span> <span data-ttu-id="04c3c-157">Например, выражение запроса, которое ссылается на объекты в пространстве имен Microsoft.SqlServer.Management.Smo, должно начинаться с узла сервера, за которым идет узел базы данных, и так далее.</span><span class="sxs-lookup"><span data-stu-id="04c3c-157">For example, a query expression that references objects in the Microsoft.SqlServer.Management.Smo namespace must start with a Server node followed by a Database node, and so on.</span></span>  
  
 <span data-ttu-id="04c3c-158">Если *\<FilterExpression>* для объекта не указано значение, перечисляются все объекты в этом узле.</span><span class="sxs-lookup"><span data-stu-id="04c3c-158">If a *\<FilterExpression>* is not specified for an object, all the objects at that node are enumerated.</span></span>  
  
## <a name="uniform-resource-names-urn"></a><span data-ttu-id="04c3c-159">Универсальные имена ресурсов (URN)</span><span class="sxs-lookup"><span data-stu-id="04c3c-159">Uniform Resource Names (URN)</span></span>  
 <span data-ttu-id="04c3c-160">Имена URN представляют собой подмножество выражений запроса.</span><span class="sxs-lookup"><span data-stu-id="04c3c-160">URNs are a subset of query expressions.</span></span> <span data-ttu-id="04c3c-161">Каждое имя URN является полной ссылкой на один объект.</span><span class="sxs-lookup"><span data-stu-id="04c3c-161">Each URN forms a fully-qualified reference to a single object.</span></span> <span data-ttu-id="04c3c-162">В обычном имени URN свойство «Имя» используется для определения одного объекта в каждом узле.</span><span class="sxs-lookup"><span data-stu-id="04c3c-162">A typical URN uses the Name property to identify a single object at each node.</span></span> <span data-ttu-id="04c3c-163">Например, данное имя URN ссылается на определенный столбец:</span><span class="sxs-lookup"><span data-stu-id="04c3c-163">For example, this URN refers to a specific column:</span></span>  
  
```  
Server[@Name='MYCOMPUTER']/Database[@Name='AdventureWorks2012']/Table[@Name='SalesPerson' and @Schema='Sales']/Column[@Name='SalesPersonID']  
```  
  
## <a name="examples"></a><span data-ttu-id="04c3c-164">Примеры</span><span class="sxs-lookup"><span data-stu-id="04c3c-164">Examples</span></span>  
  
### <a name="a-enumerating-objects-using-false"></a><span data-ttu-id="04c3c-165">A.</span><span class="sxs-lookup"><span data-stu-id="04c3c-165">A.</span></span> <span data-ttu-id="04c3c-166">Перечисление объектов при помощи функции false()</span><span class="sxs-lookup"><span data-stu-id="04c3c-166">Enumerating objects using false()</span></span>  
 <span data-ttu-id="04c3c-167">Приведенное ниже выражение запроса перечисляет все базы данных в экземпляре по умолчанию в **MyComputer** , атрибут **AutoClose**которых имеет значение false.</span><span class="sxs-lookup"><span data-stu-id="04c3c-167">This query expression enumerates all the databases that have the **AutoClose** attribute set to false in the default instance on **MyComputer**.</span></span>  
  
```  
Server[@Name='MYCOMPUTER']/Database[@AutoClose=false()]  
```  
  
### <a name="b-enumerating-objects-using-contains"></a><span data-ttu-id="04c3c-168">Б.</span><span class="sxs-lookup"><span data-stu-id="04c3c-168">B.</span></span> <span data-ttu-id="04c3c-169">Перечисление объектов при помощи функции contains</span><span class="sxs-lookup"><span data-stu-id="04c3c-169">Enumerating objects using contains</span></span>  
 <span data-ttu-id="04c3c-170">Следующее выражение запроса перечисляет все базы данных, в которых учитывается регистр и в имени которых имеется символ «m».</span><span class="sxs-lookup"><span data-stu-id="04c3c-170">This query expression enumerates all the databases that are case-insensitive and have the character 'm' in their name.</span></span>  
  
```  
Server[@Name='MYCOMPUTER']/Database[@CaseSensitive=false() and contains(@Name, 'm')]   
```  
  
### <a name="c-enumerating-objects-using-not"></a><span data-ttu-id="04c3c-171">В.</span><span class="sxs-lookup"><span data-stu-id="04c3c-171">C.</span></span> <span data-ttu-id="04c3c-172">Перечисление объектов при помощи функции not</span><span class="sxs-lookup"><span data-stu-id="04c3c-172">Enumerating objects using not</span></span>  
 <span data-ttu-id="04c3c-173">Следующее выражение запроса перечисляет все таблицы базы данных [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] , которые не находятся в схеме **Production** и содержат в имени таблицы слово "History":</span><span class="sxs-lookup"><span data-stu-id="04c3c-173">This query expression enumerates all of [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] tables that are not in the **Production** schema and contain the word History in the table name:</span></span>  
  
```  
Server[@Name='MYCOMPUTER']/Database[@Name='AdventureWorks2012']/Table[not(@Schema='Production') and contains(@Name, 'History')]  
```  
  
### <a name="d-not-supplying-a-filter-expression-for-the-final-node"></a><span data-ttu-id="04c3c-174">Г.</span><span class="sxs-lookup"><span data-stu-id="04c3c-174">D.</span></span> <span data-ttu-id="04c3c-175">Отсутствие критерия фильтра для итогового узла</span><span class="sxs-lookup"><span data-stu-id="04c3c-175">Not supplying a filter expression for the final node</span></span>  
 <span data-ttu-id="04c3c-176">Следующее выражение запроса перечисляет все столбцы в таблице **AdventureWorks2012.Sales.SalesPerson** :</span><span class="sxs-lookup"><span data-stu-id="04c3c-176">This query expression enumerates all the columns in the **AdventureWorks2012.Sales.SalesPerson** table:</span></span>  
  
```  
Server[@Name='MYCOMPUTER']/Database[@Name='AdventureWorks2012"]/Table[@Schema='Sales' and @Name='SalesPerson']/Columns  
```  
  
### <a name="e-enumerating-objects-using-datetime"></a><span data-ttu-id="04c3c-177">Д.</span><span class="sxs-lookup"><span data-stu-id="04c3c-177">E.</span></span> <span data-ttu-id="04c3c-178">Перечисление объектов при помощи функции datetime</span><span class="sxs-lookup"><span data-stu-id="04c3c-178">Enumerating objects using datetime</span></span>  
 <span data-ttu-id="04c3c-179">Следующее выражение запроса перечисляет все таблицы, созданные в базе данных [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] в определенное время:</span><span class="sxs-lookup"><span data-stu-id="04c3c-179">This query expression enumerates all the tables that are created in the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] database at a specific time:</span></span>  
  
```  
Server[@Name='MYCOMPUTER']/Database[@Name='AdventureWorks2012"]/Table[@CreateDate=datetime('2008-03-21 19:49:32.647')]  
```  
  
### <a name="f-enumerating-objects-using-is_null"></a><span data-ttu-id="04c3c-180">Е.</span><span class="sxs-lookup"><span data-stu-id="04c3c-180">F.</span></span> <span data-ttu-id="04c3c-181">Перечисление объектов при помощи функции is_null</span><span class="sxs-lookup"><span data-stu-id="04c3c-181">Enumerating objects using is_null</span></span>  
 <span data-ttu-id="04c3c-182">Следующее выражение запроса перечисляет все таблицы в базе данных [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] , значение свойства «Дата последнего изменения» в которых не равно NULL:</span><span class="sxs-lookup"><span data-stu-id="04c3c-182">This query expression enumerates all the tables in the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] database that do not have NULL for their date last modified property:</span></span>  
  
```  
Server[@Name='MYCOMPUTER']/Database[@Name='AdventureWorks2012"]/Table[Not(is_null(@DateLastModified))]  
```  
  
## <a name="see-also"></a><span data-ttu-id="04c3c-183">См. также:</span><span class="sxs-lookup"><span data-stu-id="04c3c-183">See Also</span></span>  
 <span data-ttu-id="04c3c-184">[Командлет Invoke-PolicyEvaluation](../database-engine/invoke-policyevaluation-cmdlet.md) </span><span class="sxs-lookup"><span data-stu-id="04c3c-184">[Invoke-PolicyEvaluation cmdlet](../database-engine/invoke-policyevaluation-cmdlet.md) </span></span>  
 [<span data-ttu-id="04c3c-185">Подсистема аудита SQL Server (компонент Database Engine)</span><span class="sxs-lookup"><span data-stu-id="04c3c-185">SQL Server Audit &#40;Database Engine&#41;</span></span>](../relational-databases/security/auditing/sql-server-audit-database-engine.md)  
