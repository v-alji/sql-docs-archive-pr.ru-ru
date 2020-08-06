---
title: Использование ДЕТАЛИЗАЦИи для получения исходных данных (многомерные выражения) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- DRILLTHROUGH statement
- retrieving data
- queries [MDX], DRILLTHROUGH statement
- data retrieval [MDX]
ms.assetid: fe0ab170-25a9-45a8-a377-f71a67f77018
author: minewiskan
ms.author: owend
ms.openlocfilehash: 5601a3ddfa7075ed53330e12c260af88648db990
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664575"
---
# <a name="using-drillthrough-to-retrieve-source-data-mdx"></a><span data-ttu-id="955a7-102">Извлечение данных из источника с помощью функции DRILLTHROUGH (многомерные выражения)</span><span class="sxs-lookup"><span data-stu-id="955a7-102">Using DRILLTHROUGH to Retrieve Source Data (MDX)</span></span>
  <span data-ttu-id="955a7-103">В языке многомерных выражений для извлечения набора строк из источника данных для ячейки куба используется инструкция [DRILLTHROUGH](/sql/mdx/mdx-data-manipulation-drillthrough).</span><span class="sxs-lookup"><span data-stu-id="955a7-103">Multidimensional Expressions (MDX) uses the [DRILLTHROUGH](/sql/mdx/mdx-data-manipulation-drillthrough)statement to retrieve a rowset from the source data for a cube cell.</span></span>  
  
 <span data-ttu-id="955a7-104">Чтобы в кубе можно было выполнять инструкцию `DRILLTHROUGH`, для него следует определить действие детализации.</span><span class="sxs-lookup"><span data-stu-id="955a7-104">In order to run a `DRILLTHROUGH` statement on a cube, a drillthrough action must be defined for that cube.</span></span> <span data-ttu-id="955a7-105">Чтобы определить действие детализации, в конструкторе кубов в среде [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)]на панели **Действия** выберите на панели инструментов пункт **Создать действие детализации**.</span><span class="sxs-lookup"><span data-stu-id="955a7-105">To define a drillthrough action, in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], in Cube Designer, on the **Actions** pane, on the toolbar, click **New Drillthrough Action**.</span></span> <span data-ttu-id="955a7-106">Для действия детализации укажите имя, цель и условие действия, а также столбцы, возвращаемые инструкцией `DRILLTHROUGH`.</span><span class="sxs-lookup"><span data-stu-id="955a7-106">In the new drillthrough action, specify the action name, target, condition, and the columns that are returned by a `DRILLTHROUGH` statement.</span></span>  
  
## <a name="drillthrough-statement-syntax"></a><span data-ttu-id="955a7-107">Синтаксис инструкции DRILLTHROUGH</span><span class="sxs-lookup"><span data-stu-id="955a7-107">DRILLTHROUGH Statement Syntax</span></span>  
 <span data-ttu-id="955a7-108">Синтаксис инструкции `DRILLTHROUGH`:</span><span class="sxs-lookup"><span data-stu-id="955a7-108">The `DRILLTHROUGH` statement uses the following syntax:</span></span>  
  
```  
<drillthrough> ::= DRILLTHROUGH [<Max_Rows>] [<First_Rowset>] <MDX select> [<Return_Columns>]  
   < Max_Rows> ::= MAXROWS <positive number>  
   <First_Rowset> ::= FIRSTROWSET <positive number>  
   <Return_Columns> ::= RETURN <member or attribute> [, <member or attribute>]  
```  
  
 <span data-ttu-id="955a7-109">Предложение `SELECT` определяет ячейку куба, содержащую извлекаемые исходные данные.</span><span class="sxs-lookup"><span data-stu-id="955a7-109">The `SELECT` clause identifies the cube cell that contains the source data to be retrieved.</span></span> <span data-ttu-id="955a7-110">Это предложение `SELECT` эквивалентно обычной инструкции многомерных выражений `SELECT`, за исключением того, что в предложении `SELECT` на каждой оси можно указывать только один элемент.</span><span class="sxs-lookup"><span data-stu-id="955a7-110">This `SELECT` clause is the same to an ordinary MDX `SELECT` statement, except that in the `SELECT` clause only one member can be specified on each axis.</span></span> <span data-ttu-id="955a7-111">Если на оси указано несколько элементов, возникает ошибка.</span><span class="sxs-lookup"><span data-stu-id="955a7-111">If more than one member is specified on an axis, an error occurs.</span></span>  
  
 <span data-ttu-id="955a7-112">Синтаксическая конструкция `<Max_Rows>` задает максимальное количество строк в каждом возвращаемом наборе строк.</span><span class="sxs-lookup"><span data-stu-id="955a7-112">The `<Max_Rows>` syntax specifies the maximum number of the rows in each returned rowset.</span></span> <span data-ttu-id="955a7-113">Если поставщик OLE DB, используемый для соединения с источником данных, не поддерживает параметр `DBPROP_MAXROWS`, аргумент `<Max_Rows>` не учитывается.</span><span class="sxs-lookup"><span data-stu-id="955a7-113">If the OLE DB provider that is used to connect to the data source does not support `DBPROP_MAXROWS`, the `<Max_Rows>` setting is ignored.</span></span>  
  
 <span data-ttu-id="955a7-114">Синтаксическая конструкция `<First_Rowset>` определяет секцию, набор строк которой возвращается первым.</span><span class="sxs-lookup"><span data-stu-id="955a7-114">The `<First_Rowset>` syntax identifies the partition whose rowset is returned first.</span></span>  
  
 <span data-ttu-id="955a7-115">Синтаксическая конструкция `<Return_Columns>` определяет возвращаемые столбцы базовой базы данных.</span><span class="sxs-lookup"><span data-stu-id="955a7-115">The `<Return_Columns>` syntax identifies the underlying database columns to be returned.</span></span>  
  
## <a name="drillthrough-statement-example"></a><span data-ttu-id="955a7-116">Пример инструкции DRILLTHROUGH</span><span class="sxs-lookup"><span data-stu-id="955a7-116">DRILLTHROUGH Statement Example</span></span>  
 <span data-ttu-id="955a7-117">В следующем примере иллюстрируется использование инструкции `DRILLTHROUGH`.</span><span class="sxs-lookup"><span data-stu-id="955a7-117">The following example demonstrates the use of the `DRILLTHROUGH` statement.</span></span> <span data-ttu-id="955a7-118">В этом примере инструкция DRILLTHROUGH обращается с запросом к концевым элементам измерений Store, Product и Time вдоль измерения Stores (ось среза) и возвращает группу мер Department, идентификатор отдела и имя сотрудника.</span><span class="sxs-lookup"><span data-stu-id="955a7-118">In this example, the DRILLTHROUGH statement queries the leaves of the Store, Product, and Time dimensions along the Stores dimension (the slicer axis), and then returns the department measure group, department ID, and employee's first name.</span></span>  
  
```  
DRILLTHROUGH  
Select {Leaves(Store), Leaves(Product), Leaves(Time),*} on 0  
From Stores  
RETURN [Department MeasureGroup].[Department Id], [Employee].[First Name]  
```  
  
## <a name="see-also"></a><span data-ttu-id="955a7-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="955a7-119">See Also</span></span>  
 [<span data-ttu-id="955a7-120">Манипулирование данными (многомерные выражения)</span><span class="sxs-lookup"><span data-stu-id="955a7-120">Manipulating Data &#40;MDX&#41;</span></span>](mdx-data-manipulation-manipulating-data.md)  
  
  
