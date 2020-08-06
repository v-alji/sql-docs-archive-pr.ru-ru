---
title: Вызов хранимых процедур | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- calling stored procedures
- stored procedures [Analysis Services], calling
- MDX queries [Analysis Services]
- CALL statement
ms.assetid: 96a9660d-875b-4ee4-b339-90020b1d9895
author: minewiskan
ms.author: owend
ms.openlocfilehash: 5c9da6edef576a6ab25c183cbc87ff95cc056845
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732169"
---
# <a name="calling-stored-procedures"></a><span data-ttu-id="af3df-102">Вызов хранимых процедур</span><span class="sxs-lookup"><span data-stu-id="af3df-102">Calling Stored Procedures</span></span>
  <span data-ttu-id="af3df-103">Хранимые процедуры можно вызывать на сервере или из клиентского приложения.</span><span class="sxs-lookup"><span data-stu-id="af3df-103">Stored procedures can be called on the server or from client application.</span></span> <span data-ttu-id="af3df-104">В любом случае хранимые процедуры всегда выполняются на сервере либо в контексте сервера, либо в контексте базы данных.</span><span class="sxs-lookup"><span data-stu-id="af3df-104">In either case, stored procedures always run on the server, either the context of the server or of a database.</span></span> <span data-ttu-id="af3df-105">Для выполнения хранимой процедуры не нужны специальные разрешения.</span><span class="sxs-lookup"><span data-stu-id="af3df-105">There are no special permissions required to execute a stored procedure.</span></span> <span data-ttu-id="af3df-106">После того как хранимая процедура добавлена сборкой к контексту сервера или базы данных, любой пользователь может выполнить эту хранимую процедуру, если только роль для этого пользователя разрешает действия, выполняемые этой хранимой процедурой.</span><span class="sxs-lookup"><span data-stu-id="af3df-106">Once a stored procedure is added by an assembly to the server or database context, any user can execute the stored procedure as long as the role for the user permits the actions performed by the stored procedure.</span></span>  
  
 <span data-ttu-id="af3df-107">Вызов хранимой процедуры в многомерном выражении осуществляется аналогично вызову внутренней функции многомерного выражения.</span><span class="sxs-lookup"><span data-stu-id="af3df-107">Calling a stored procedure in MDX is done in the same manner as calling an intrinsic MDX function.</span></span> <span data-ttu-id="af3df-108">Для хранимой процедуры, не принимающей параметров, используется имя процедуры и пустая пара скобок, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="af3df-108">For a stored procedure that takes no parameters, the name of the procedure and an empty pair of parentheses are used, as shown here:</span></span>  
  
```  
MyStoredProcedure()  
```  
  
 <span data-ttu-id="af3df-109">Если хранимая процедура принимает один или несколько параметров, то параметры вводятся по порядку и разделены запятыми.</span><span class="sxs-lookup"><span data-stu-id="af3df-109">If the stored procedure takes one or more parameters, then the parameters are supplied, in order, separated by commas.</span></span> <span data-ttu-id="af3df-110">В следующем примере демонстрируется образец хранимой процедуры с тремя параметрами:</span><span class="sxs-lookup"><span data-stu-id="af3df-110">The following example demonstrates a sample stored procedure with three parameters:</span></span>  
  
```  
MyStoredProcedure("Parameter1", 2, 800)  
```  
  
## <a name="calling-stored-procedures-in-mdx-queries"></a><span data-ttu-id="af3df-111">Вызов хранимых процедур в запросах многомерных выражений</span><span class="sxs-lookup"><span data-stu-id="af3df-111">Calling Stored Procedures in MDX Queries</span></span>  
 <span data-ttu-id="af3df-112">Во всех запросах многомерных выражений хранимая процедура должна возвращать синтаксически корректный тип, требуемый многомерным выражением.</span><span class="sxs-lookup"><span data-stu-id="af3df-112">In all MDX queries, the stored procedure must return the syntactically correct type required by an MDX expression.</span></span> <span data-ttu-id="af3df-113">Если хранимая процедура не возвращает корректный тип, то возникает ошибка многомерного выражения.</span><span class="sxs-lookup"><span data-stu-id="af3df-113">If a stored procedure does not return the correct type, an MDX error occurs.</span></span> <span data-ttu-id="af3df-114">В следующем примере демонстрируются хранимые процедуры, возвращающие набор, элемент и результат математической операции.</span><span class="sxs-lookup"><span data-stu-id="af3df-114">The following examples demonstrate stored procedures that return a set, a member, and the result of a mathematical operation.</span></span>  
  
### <a name="returning-a-set"></a><span data-ttu-id="af3df-115">Возврат набора</span><span class="sxs-lookup"><span data-stu-id="af3df-115">Returning a Set</span></span>  
 <span data-ttu-id="af3df-116">В следующих примерах реализуется хранимая процедура, имеющая имя MySproc, которая возвращает набор.</span><span class="sxs-lookup"><span data-stu-id="af3df-116">The following examples implement a stored procedure, called MySproc, that returns a set.</span></span> <span data-ttu-id="af3df-117">В первом примере MySproc возвращает набор непосредственно в выражении SELECT.</span><span class="sxs-lookup"><span data-stu-id="af3df-117">In the first example, MySproc returns the set directly in the SELECT expression.</span></span> <span data-ttu-id="af3df-118">В следующих двух примерах MySproc возвращает набор в качестве аргумента для функций Crossjoin и DrilldownLevel.</span><span class="sxs-lookup"><span data-stu-id="af3df-118">In the second two examples, MySproc returns the set as an argument for the Crossjoin and DrilldownLevel functions.</span></span>  
  
```  
SELECT MySetProcedure(a,b,c) ON 0 FROM Sales  
SELECT Crossjoin(MySetProcedure(a,b,c)) ON 0 FROM Sales  
SELECT DrilldownLevel(MySetProcedure(a,b,c)) ON 0 FROM Sales  
```  
  
### <a name="returning-a-member"></a><span data-ttu-id="af3df-119">Возврат элемента</span><span class="sxs-lookup"><span data-stu-id="af3df-119">Returning a Member</span></span>  
 <span data-ttu-id="af3df-120">В следующем примере показана функция MySproc, возвращающая элемент:</span><span class="sxs-lookup"><span data-stu-id="af3df-120">The following example shows a function MySproc function that returns a member:</span></span>  
  
```  
SELECT Descendants(MySproc(a,b,c),3) ON 0 FROM Sales  
```  
  
### <a name="returning-the-result-of-a-math-operation"></a><span data-ttu-id="af3df-121">Возврат результата математической операции</span><span class="sxs-lookup"><span data-stu-id="af3df-121">Returning the Result of a Math Operation</span></span>  
  
```  
SELECT Country.Members on 0, MySproc(Measures.Sales) ON 1 FROM Sales  
```  
  
## <a name="calling-stored-procedures-with-the-call-statement"></a><span data-ttu-id="af3df-122">Вызов хранимых процедур с использованием инструкции Call</span><span class="sxs-lookup"><span data-stu-id="af3df-122">Calling Stored Procedures with the Call Statement</span></span>  
 <span data-ttu-id="af3df-123">Хранимые процедуры можно вызывать вне контекста запроса многомерного выражения, используя инструкцию `Call` многомерного выражения.</span><span class="sxs-lookup"><span data-stu-id="af3df-123">Stored procedures can be called outside of the context of an MDX query using the MDX `Call` statement.</span></span>  
  
 <span data-ttu-id="af3df-124">Этот метод можно использовать либо для создания экземпляра побочных эффектов хранимого запроса, либо для получения приложением результатов хранимого запроса.</span><span class="sxs-lookup"><span data-stu-id="af3df-124">You can use this method to either instantiate the side effects of a stored query or for the application to get the results of a stored query.</span></span> <span data-ttu-id="af3df-125">Часто инструкция `Call` применяется для использования объектов AMO для выполнения административных функций, которые необязательно возвращают результат.</span><span class="sxs-lookup"><span data-stu-id="af3df-125">A common use of the `Call` statement would be to use Analysis Management Objects (AMO) to perform administrative functions that do not have a return result.</span></span> <span data-ttu-id="af3df-126">Например, следующая команда вызывает хранимую процедуру:</span><span class="sxs-lookup"><span data-stu-id="af3df-126">For example, the following command calls a stored procedure:</span></span>  
  
```  
Call MyStoredProcedure(a,b,c)  
```  
  
 <span data-ttu-id="af3df-127">Единственным поддерживаемым типом, возвращаемым из хранимой процедуры в инструкции `Call`, является набор строк.</span><span class="sxs-lookup"><span data-stu-id="af3df-127">The only supported type returned from stored procedure in a `Call` statement is a rowset.</span></span> <span data-ttu-id="af3df-128">Упорядочивание для набора строк определяется XML для аналитики.</span><span class="sxs-lookup"><span data-stu-id="af3df-128">The serialization for a rowset is defined by XML for Analysis.</span></span> <span data-ttu-id="af3df-129">Если хранимая процедура в инструкции `Call` возвращает любой другой тип, то он игнорируется и не возвращается в XML вызывающему приложению.</span><span class="sxs-lookup"><span data-stu-id="af3df-129">If a stored procedure in a `Call` statement returns any other type, it is ignored and not returned in XML to the calling application.</span></span> <span data-ttu-id="af3df-130">Дополнительные сведения о наборах строк XML для аналитики см. в разделе «Наборы строк схемы XML для аналитики».</span><span class="sxs-lookup"><span data-stu-id="af3df-130">For more information about XML for Analysis rowsets, see, XML for Analysis Schema Rowsets.</span></span>  
  
 <span data-ttu-id="af3df-131">Если хранимая процедура возвращает набор строк платформы .NET, то службы [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] преобразуют результат на сервере в набор строк XML для аналитики.</span><span class="sxs-lookup"><span data-stu-id="af3df-131">If a stored procedure returns a .NET rowset, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] converts the result on the server to an XML for Analysis rowset.</span></span> <span data-ttu-id="af3df-132">Набор строк XML для аналитики всегда возвращается хранимой процедурой в функции `Call`.</span><span class="sxs-lookup"><span data-stu-id="af3df-132">The XML for Analysis rowset is always returned by a stored procedure in the `Call` function.</span></span> <span data-ttu-id="af3df-133">Если набор данных содержит элементы, которые нельзя выразить в наборе строк XML для аналитики, то происходит сбой.</span><span class="sxs-lookup"><span data-stu-id="af3df-133">If a dataset contains features that cannot be expressed in the XML for Analysis rowset, a failure results.</span></span>  
  
 <span data-ttu-id="af3df-134">Процедуры, возвращающие значения void (например, подпрограммы языка Visual Basic), также могут использоваться с ключевым словом CALL.</span><span class="sxs-lookup"><span data-stu-id="af3df-134">Procedures that return void values (for example, subroutines in Visual Basic) can also be employed with the CALL keyword.</span></span> <span data-ttu-id="af3df-135">Например, если необходимо использовать функцию MyVoidFunction() в инструкции многомерного выражения, то нужно применить следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="af3df-135">If, for example, you wanted to use the function MyVoidFunction() in an MDX statement, the following syntax would be employed:</span></span>  
  
```  
CALL(MyVoidFunction)  
```  
  
## <a name="see-also"></a><span data-ttu-id="af3df-136">См. также:</span><span class="sxs-lookup"><span data-stu-id="af3df-136">See Also</span></span>  
 <span data-ttu-id="af3df-137">[Управление сборками многомерной модели](../multidimensional-models/multidimensional-model-assemblies-management.md) </span><span class="sxs-lookup"><span data-stu-id="af3df-137">[Multidimensional Model Assemblies Management](../multidimensional-models/multidimensional-model-assemblies-management.md) </span></span>  
 [<span data-ttu-id="af3df-138">Определение хранимых процедур</span><span class="sxs-lookup"><span data-stu-id="af3df-138">Defining Stored Procedures</span></span>](../multidimensional-models-extending-olap-stored-procedures/defining-stored-procedures.md)  
  
  
