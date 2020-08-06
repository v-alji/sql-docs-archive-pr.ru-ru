---
title: Определение назначений и других команд сценариев | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- empty scripts [Analysis Services]
- calculations [Analysis Services], scripts
- MDX [Analysis Services], scripts
- scripts [Analysis Services], calculations
ms.assetid: f28b9b22-3dc7-4a45-b4eb-2d023f2c94b8
author: minewiskan
ms.author: owend
ms.openlocfilehash: 184c998bb4bd27d077cca78e792a7e7712f87666
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666838"
---
# <a name="define-assignments-and-other-script-commands"></a><span data-ttu-id="87ce3-102">Определение назначений и других команд скриптов</span><span class="sxs-lookup"><span data-stu-id="87ce3-102">Define Assignments and Other Script Commands</span></span>
  <span data-ttu-id="87ce3-103">На вкладке **Вычисления** конструктора кубов щелкните значок **Создать команду скрипта** на панели инструментов для создания пустого скрипта.</span><span class="sxs-lookup"><span data-stu-id="87ce3-103">On the **Calculations** tab of Cube Designer, click the **New ScriptCommand** icon on the toolbar to create an empty script.</span></span> <span data-ttu-id="87ce3-104">При создании нового скрипта изначально он отображается с пустым заголовком на панели **Организатор скриптов** на вкладке вычисления. Символы, введенные на панели Выражения вычисления, будут отображаться как имя элемента в **организаторе скриптов**.</span><span class="sxs-lookup"><span data-stu-id="87ce3-104">When you create a new script, it initially is displayed with a blank title in the **Script Organizer** pane of the Calculations tab. The characters you type in the Calculation Expressions pane will be visible as the name of the item in **Script Organizer**.</span></span> <span data-ttu-id="87ce3-105">Следовательно, можно в первую строку ввести имя с комментарием для упрощения определения скрипта на панели **Организатор скриптов** .</span><span class="sxs-lookup"><span data-stu-id="87ce3-105">Therefore, you may want to type a commented name on the first line to more easily identify the script in the **Script Organizer** pane.</span></span> <span data-ttu-id="87ce3-106">Дополнительные сведения см. в разделе [Введение в сценарии многомерных выражений в Microsoft SQL Server 2005](https://go.microsoft.com/fwlink/?LinkId=81892).</span><span class="sxs-lookup"><span data-stu-id="87ce3-106">For more information, see [Introduction to MDX Scripting in Microsoft SQL Server 2005](https://go.microsoft.com/fwlink/?LinkId=81892).</span></span> <span data-ttu-id="87ce3-107">Дополнительные сведения о проблемах производительности, связанных с запросами и вычислениями многомерных выражений, см. в подразделе «написание эффективных многомерных выражений» [руководства по SQL Server 2005 Analysis Services](https://docsbay.net/Microsoft-SQL-Server-2005-Analysis-Services-Performance-Guide).</span><span class="sxs-lookup"><span data-stu-id="87ce3-107">For more information about performance issues related to MDX queries and calculations, see the section "Writing Efficient MDX" in the [SQL Server 2005 Analysis Services Performance Guide](https://docsbay.net/Microsoft-SQL-Server-2005-Analysis-Services-Performance-Guide).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="87ce3-108">Затем перейдите на вкладку **Вычисления** конструктора кубов, на панели **Организатор скриптов** содержится один скрипт с командой CALCULATE.</span><span class="sxs-lookup"><span data-stu-id="87ce3-108">When you initially switch to the **Calculations** tab of Cube Designer, the **Script Organizer** pane contains a single script with a CALCULATE command.</span></span> <span data-ttu-id="87ce3-109">Команда CALCULATE управляет статистическим вычислением ячеек куба, ее следует изменять только в том случае, если планируется вручную определять статистическое вычисление ячеек куба.</span><span class="sxs-lookup"><span data-stu-id="87ce3-109">The CALCULATE command controls the aggregation of the cells in the cube and should be edited only if you intend to manually specify how the cube is to be aggregated.</span></span>  
  
 <span data-ttu-id="87ce3-110">Для создания выражений с синтаксисом многомерных выражений можно использовать панель «Выражения вычисления».</span><span class="sxs-lookup"><span data-stu-id="87ce3-110">You can use the Calculation Expressions pane to build an expression in Multidimensional Expressions (MDX) syntax.</span></span> <span data-ttu-id="87ce3-111">При создании выражения с панели **Средства вычисления** можно перетаскивать или копировать компоненты куба, функции и шаблоны на панель «Выражения вычисления».</span><span class="sxs-lookup"><span data-stu-id="87ce3-111">While you build the expression, you can drag or copy cube components, functions, and templates from the **Calculation Tools** pane to the Calculation Expressions pane.</span></span> <span data-ttu-id="87ce3-112">При этом скрипт добавляется для элемента на панели «Выражения вычисления» в то место, куда элемент перемещается или вставляется.</span><span class="sxs-lookup"><span data-stu-id="87ce3-112">Doing so adds the script for the item to the Calculation Expressions pane in the location that you drop or paste it.</span></span> <span data-ttu-id="87ce3-113">Замените аргументы и их разделители (« и ») соответствующими значениями.</span><span class="sxs-lookup"><span data-stu-id="87ce3-113">Replace arguments and their delimiters (« and ») with the appropriate values.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="87ce3-114">При написании выражения, содержащего несколько инструкций, с помощью панели «Выражения вычисления» убедитесь, что все строки скрипта многомерных выражений, за исключением последней, заканчиваются точкой с запятой (;).</span><span class="sxs-lookup"><span data-stu-id="87ce3-114">When writing an expression that contains multiple statements using the Calculation Expressions pane, ensure that all lines except the last line of the MDX script end with a semi-colon (;).</span></span> <span data-ttu-id="87ce3-115">Вычисления объединяются в отдельный скрипт многомерных выражений, и к каждому скрипту добавляется точка с запятой.</span><span class="sxs-lookup"><span data-stu-id="87ce3-115">Calculations are concatenated into a single MDX script, and each script has a semi-colon appended to it to ensure that the MDX script compiles correctly.</span></span> <span data-ttu-id="87ce3-116">Если добавить точку с запятой к последней строке скрипта на панели «Вычисления выражения», то куб будет создан и развернут правильно, но к нему нельзя будет применять запросы.</span><span class="sxs-lookup"><span data-stu-id="87ce3-116">If you add a semi-colon to the last line of the script in the Calculation Expressions pane, the cube will build and deploy correctly but you will be unable to run queries against it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87ce3-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="87ce3-117">See Also</span></span>  
 [<span data-ttu-id="87ce3-118">Вычисления в многомерных моделях</span><span class="sxs-lookup"><span data-stu-id="87ce3-118">Calculations in Multidimensional Models</span></span>](calculations-in-multidimensional-models.md)  
  
  
