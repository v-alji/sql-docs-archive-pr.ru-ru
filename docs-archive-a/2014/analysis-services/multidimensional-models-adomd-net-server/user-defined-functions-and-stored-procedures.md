---
title: Определяемые пользователем функции и хранимые процедуры | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- stored procedures [ADOMD.NET]
- ADOMD.NET, user defined functions
- user defined functions [ADOMD.NET]
- ADOMD.NET, UDFs
- ADOMD.NET, stored procedures
ms.assetid: 07e8aa47-37d4-4bbc-8bff-49e422d12897
author: minewiskan
ms.author: owend
ms.openlocfilehash: a49aa41d158bf2c9fd1ebb1a711d6ff35c0df98b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727442"
---
# <a name="user-defined-functions-and-stored-procedures"></a><span data-ttu-id="bbc34-102">Определяемые пользователем функции и хранимые процедуры</span><span class="sxs-lookup"><span data-stu-id="bbc34-102">User Defined Functions and Stored Procedures</span></span>
  <span data-ttu-id="bbc34-103">С помощью объектов ADOMD.NET Server можно создать определяемую пользователем функцию (UDF) или хранимые процедуры для [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] взаимодействия с метаданными и данными с сервера.</span><span class="sxs-lookup"><span data-stu-id="bbc34-103">With ADOMD.NET server objects, you can create user defined function (UDF) or stored procedures for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] that interact with metadata and data from the server.</span></span> <span data-ttu-id="bbc34-104">Эти внутрипроцессные методы вызываются при помощи инструкций на языке MDX или DMX для предоставления дополнительных функциональных возможностей без задержек, связанных с обменом данными по сети.</span><span class="sxs-lookup"><span data-stu-id="bbc34-104">These in-process methods are called through Multidimensional Expressions (MDX) or Data Mining Extensions (DMX) statements to provide added functionality without the latencies associated with network communications.</span></span>  
  
## <a name="udf-examples"></a><span data-ttu-id="bbc34-105">Примеры определяемых пользователем функций</span><span class="sxs-lookup"><span data-stu-id="bbc34-105">UDF Examples</span></span>  
 <span data-ttu-id="bbc34-106">Определяемая пользователем функция — это метод, который можно вызывать в контексте инструкции MDX или DMX; он может принимать любое количество параметров и возвращать данные любого типа.</span><span class="sxs-lookup"><span data-stu-id="bbc34-106">A UDF is a method that can be called in the context of an MDX or DMX statement, can take any number of parameters, and can return any type of data.</span></span>  
  
 <span data-ttu-id="bbc34-107">Определяемая пользователем функция, созданная при помощи языка MDX, похожа на функцию, созданную на языке DMX.</span><span class="sxs-lookup"><span data-stu-id="bbc34-107">A UDF created using MDX is similar to one created for DMX.</span></span> <span data-ttu-id="bbc34-108">Основное отличие состоит в том, что определенные свойства объекта [Microsoft. AnalysisServices. того объектная AdomdServer. Context](/previous-versions/sql/sql-server-2014/ms143353(v=sql.120)) , такие как свойства [Microsoft. AnalysisServices. того объектная AdomdServer. Context. CURRENTCUBE \*](/previous-versions/sql/sql-server-2014/ms137081(v=sql.120)) и [Microsoft. AnalysisServices. того объектная AdomdServer. Context. куррентминингмодел \*](/previous-versions/sql/sql-server-2014/ms137178(v=sql.120)) , доступны только для одного языка сценариев или другого.</span><span class="sxs-lookup"><span data-stu-id="bbc34-108">The main difference is that certain properties of the [Microsoft.AnalysisServices.AdomdServer.Context](/previous-versions/sql/sql-server-2014/ms143353(v=sql.120)) object, such as the [Microsoft.AnalysisServices.AdomdServer.Context.CurrentCube\*](/previous-versions/sql/sql-server-2014/ms137081(v=sql.120)) and [Microsoft.AnalysisServices.AdomdServer.Context.CurrentMiningModel\*](/previous-versions/sql/sql-server-2014/ms137178(v=sql.120)) properties, are available only for one scripting language or the other.</span></span>  
  
 <span data-ttu-id="bbc34-109">Следующие примеры демонстрируют использование определяемой пользователем функции для возврата описания узла, фильтрации кортежей и применения фильтра к кортежу.</span><span class="sxs-lookup"><span data-stu-id="bbc34-109">The following examples show how to use a UDF to return a node description, filter tuples, and apply a filter to a tuple.</span></span>  
  
### <a name="returning-a-node-description"></a><span data-ttu-id="bbc34-110">Возврат описания узла</span><span class="sxs-lookup"><span data-stu-id="bbc34-110">Returning a Node Description</span></span>  
 <span data-ttu-id="bbc34-111">В следующем примере создается определяемая пользователем функция, которая возвращает описание указанного узла.</span><span class="sxs-lookup"><span data-stu-id="bbc34-111">The following example creates a UDF that returns the node description for a specified node.</span></span> <span data-ttu-id="bbc34-112">В этой определяемой пользователем функции используется текущий контекст, в котором она выполняется, а также предложение FROM языка DMX для извлечения узла из текущей модели интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="bbc34-112">The UDF uses the current context in which it is being run, and uses a DMX FROM clause to retrieve the node from the current mining model.</span></span>  
  
```  
public string GetNodeDescription(string nodeUniqueName)  
{  
   return Context.CurrentMiningModel.GetNodeFromUniqueName(nodeUniqueName).Description;  
}  
```  
  
 <span data-ttu-id="bbc34-113">После развертывания описанный выше пример определяемой пользователем функции можно вызвать следующей инструкцией DMX, которая извлекает наиболее вероятный узел прогнозирования.</span><span class="sxs-lookup"><span data-stu-id="bbc34-113">Once deployed, the previous UDF example can be called by the following DMX expression, which retrieves the most-likely prediction node.</span></span> <span data-ttu-id="bbc34-114">В описании приводятся сведения, характеризующие условия, из которых состоит узел прогнозирования.</span><span class="sxs-lookup"><span data-stu-id="bbc34-114">The description contains information that describes the conditions that make up the prediction node.</span></span>  
  
```  
select Cluster(), SampleAssembly.GetNodeDescription( PredictNodeId(Cluster()) ) FROM [Customer Clusters]  
```  
  
### <a name="returning-tuples"></a><span data-ttu-id="bbc34-115">Возврат кортежей</span><span class="sxs-lookup"><span data-stu-id="bbc34-115">Returning Tuples</span></span>  
 <span data-ttu-id="bbc34-116">В следующем примере показано, как получить набор и количество возвращаемых значений, а также случайным образом извлечь кортежи из набора, возвращая конечное подмножество.</span><span class="sxs-lookup"><span data-stu-id="bbc34-116">The following example takes a set and a return count, and randomly retrieves tuples from the set, returning a final subset:</span></span>  
  
```  
public Set RandomSample(Set set, int returnCount)  
{  
   //Return the original set if there are fewer tuples  
   //in the set than the number requested.  
   if (set.Tuples.Count <= returnCount)  
      return set;  
  
   System.Random r = new System.Random();  
   SetBuilder returnSet = new SetBuilder();  
  
   //Retrieve random tuples until the return set is filled.  
   int i = set.Tuples.Count;  
   foreach (Tuple t in set.Tuples)  
   {  
      if (r.Next(i) < returnCount)  
      {  
         returnCount--;  
         returnSet.Add(t);  
      }  
      i--;  
      //Stop the loop if we have enough tuples.  
      if (returnCount == 0)  
         break;  
   }  
   return returnSet.ToSet();  
}  
```  
  
 <span data-ttu-id="bbc34-117">Описанная выше функция вызывается в следующем примере многомерного выражения (MDX).</span><span class="sxs-lookup"><span data-stu-id="bbc34-117">The previous example is called in the following MDX example.</span></span> <span data-ttu-id="bbc34-118">В этом примере многомерных выражений из базы данных **Adventure Works** извлекаются пять случайных состояний или провинции.</span><span class="sxs-lookup"><span data-stu-id="bbc34-118">In this MDX example, five random states or provinces are retrieved from the **Adventure Works** database.</span></span>  
  
```  
SELECT SampleAssembly.RandomSample([Geography].[State-Province].Members, 5) on ROWS,   
[Date].[Calendar].[Calendar Year] on COLUMNS  
FROM [Adventure Works]  
WHERE [Measures].[Reseller Freight Cost]  
```  
  
### <a name="applying-a-filter-to-a-tuple"></a><span data-ttu-id="bbc34-119">Применение фильтра к кортежу</span><span class="sxs-lookup"><span data-stu-id="bbc34-119">Applying a Filter to a Tuple</span></span>  
 <span data-ttu-id="bbc34-120">В следующем примере создается определяемая пользователем функция, которая принимает набор и при помощи объекта Expression применяет фильтр к каждому кортежу в наборе.</span><span class="sxs-lookup"><span data-stu-id="bbc34-120">In the following example, a UDF is defined that takes a set, and applies a filter to each tuple in the set, using the Expression object.</span></span> <span data-ttu-id="bbc34-121">В возвращаемый набор будут добавлены все кортежи, соответствующие фильтру.</span><span class="sxs-lookup"><span data-stu-id="bbc34-121">Any tuples that conform to the filter will be added to a set that is returned.</span></span>  
  
 [!code-csharp[Adomd.NetServer#FilterSet](../../snippets/csharp/SQL14/adomd.net/adomd.netserver/cs/class1.cs#filterset)]  
  
 <span data-ttu-id="bbc34-122">Описанная выше функция вызывается в следующем примере многомерного выражения, где набор фильтруется по городам, название которых начинается с «А».</span><span class="sxs-lookup"><span data-stu-id="bbc34-122">The previous example is called in the following MDX example, which filters the set to cities with names beginning with 'A'.</span></span>  
  
```  
Select Measures.Members on Rows,  
SampleAssembly.FilterSet([Customer].[Customer Geography].[City], "[Customer].[Customer Geography].[City].CurrentMember.Name < 'B'") on Columns  
From [Adventure Works]  
```  
  
## <a name="stored-procedure-example"></a><span data-ttu-id="bbc34-123">Пример хранимой процедуры</span><span class="sxs-lookup"><span data-stu-id="bbc34-123">Stored Procedure Example</span></span>  
 <span data-ttu-id="bbc34-124">В следующем примере показано, как в хранимой процедуре, основанной на многомерном выражении, по мере необходимости используется объект AMO для создания секций для узла «Продажи через Интернет».</span><span class="sxs-lookup"><span data-stu-id="bbc34-124">In the following example, an MDX-based stored procedure uses AMO to create partitions, if needed, for Internet Sales.</span></span>  
  
 [!code-csharp[Adomd.NetServer#CreateInternetSalesMeasureGroupPartitions](../../snippets/csharp/SQL14/adomd.net/adomd.netserver/cs/class1.cs#createinternetsalesmeasuregrouppartitions)]  
  
  
