---
title: Управление областью и контекстом (многомерные выражения) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- scripts [MDX], context
- scope [MDX]
- CALCULATE statement
- This function [MDX]
- SCOPE statement
- scripts [MDX], scope
ms.assetid: 631e7c20-8be9-4c35-8609-76516aef19d1
author: minewiskan
ms.author: owend
ms.openlocfilehash: f7cf1e6cea8df00b632e114a5a8756373738ca6e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658455"
---
# <a name="managing-scope-and-context-mdx"></a><span data-ttu-id="b3ba3-102">Управление областью и контекстом (многомерные выражения)</span><span class="sxs-lookup"><span data-stu-id="b3ba3-102">Managing Scope and Context (MDX)</span></span>
  <span data-ttu-id="b3ba3-103">В службах [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] скрипты многомерных выражений могут применяться ко всему кубу или к конкретным частям куба в конкретных точках выполнения скрипта.</span><span class="sxs-lookup"><span data-stu-id="b3ba3-103">In [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)], a Multidimensional Expressions (MDX) script can apply to the entire cube, or to specific portions of the cube, at specific points within the execution of the script.</span></span> <span data-ttu-id="b3ba3-104">В скриптах многомерных выражений используется многоуровневый подход к вычислениям в кубе при помощи этапов вычисления.</span><span class="sxs-lookup"><span data-stu-id="b3ba3-104">The MDX script can take a layered approach to calculations within a cube through the use of calculation passes.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b3ba3-105">Дополнительные сведения о влиянии этапов вычисления на сами вычисления см. в разделе [Основные сведения о порядке этапов и порядке вычисления (многомерные выражения)](mdx-data-manipulation-understanding-pass-order-and-solve-order.md).</span><span class="sxs-lookup"><span data-stu-id="b3ba3-105">For more information on how calculation passes can affect calculations, see [Understanding Pass Order and Solve Order &#40;MDX&#41;](mdx-data-manipulation-understanding-pass-order-and-solve-order.md).</span></span>  
  
 <span data-ttu-id="b3ba3-106">Для управления этапами вычислений, областью и контекстом в скриптах многомерных выражений применяются инструкция CACULATE, функция `This` и инструкция SCOPE.</span><span class="sxs-lookup"><span data-stu-id="b3ba3-106">To control the calculation pass, scope, and context within an MDX script, you specifically use the CACULATE statement, the `This` function, and the SCOPE statement.</span></span>  
  
## <a name="using-the-calculate-statement"></a><span data-ttu-id="b3ba3-107">Инструкция CALCULATE</span><span class="sxs-lookup"><span data-stu-id="b3ba3-107">Using the CALCULATE Statement</span></span>  
 <span data-ttu-id="b3ba3-108">Инструкция CALCULATE заполняет каждую ячейку в кубе статистическими данными.</span><span class="sxs-lookup"><span data-stu-id="b3ba3-108">The CALCULATE statement populates each cell in the cube with aggregated data.</span></span> <span data-ttu-id="b3ba3-109">Например, скрипт многомерных выражений по умолчанию содержит одну инструкцию CALCULATE в начале.</span><span class="sxs-lookup"><span data-stu-id="b3ba3-109">For example, the default MDX script has a single CALCULATE statement at the beginning of the script.</span></span>  
  
 <span data-ttu-id="b3ba3-110">Дополнительные сведения о синтаксисе инструкции CALCULATE см. в разделе [Инструкция CALCULATE (многомерные выражения)](/sql/mdx/mdx-scripting-calculate).</span><span class="sxs-lookup"><span data-stu-id="b3ba3-110">For more information on the syntax of the CALCULATE statement, see [CALCULATE Statement &#40;MDX&#41;](/sql/mdx/mdx-scripting-calculate).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b3ba3-111">Если скрипт содержит инструкцию SCOPE, содержащую в себе инструкцию CALCULATE, в многомерных выражениях инструкция CALCULATE вычисляется в рамках контекста вложенного куба, определенного инструкцией SCOPE, а не для всего куба.</span><span class="sxs-lookup"><span data-stu-id="b3ba3-111">If the script contains a SCOPE statement that contains a CALCULATE statement, MDX evaluates the CALCULATE statement within the context of the subcube defined by the SCOPE statement, not against the whole cube.</span></span>  
  
## <a name="using-the-this-function"></a><span data-ttu-id="b3ba3-112">Функция This</span><span class="sxs-lookup"><span data-stu-id="b3ba3-112">Using the This Function</span></span>  
 <span data-ttu-id="b3ba3-113">Функция `This` позволяет обратиться к текущему вложенному кубу в рамках скрипта многомерных выражений.</span><span class="sxs-lookup"><span data-stu-id="b3ba3-113">The `This` function lets you retrieve the current subcube within an MDX script.</span></span> <span data-ttu-id="b3ba3-114">Функция `This` позволяет быстро заполнить ячейки в текущем вложенном кубе многомерным выражением.</span><span class="sxs-lookup"><span data-stu-id="b3ba3-114">You can use the `This` function to quickly set the value of cells within the current subcube to an MDX expression.</span></span> <span data-ttu-id="b3ba3-115">Функция `This` часто используется в сочетании с инструкцией SCOPE для изменения содержимого конкретного вложенного куба на определенном этапе вычислений.</span><span class="sxs-lookup"><span data-stu-id="b3ba3-115">You often use the `This` function in conjunction with the SCOPE statement to change the contents of a specific subcube during a specific calculation pass.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b3ba3-116">Если в скрипте присутствует инструкция SCOPE, содержащая функцию `This`, в многомерных выражениях функция `This` вычисляется в рамках контекста вложенного куба, определенного инструкцией SCOPE, а не для всего куба.</span><span class="sxs-lookup"><span data-stu-id="b3ba3-116">If the script contains a SCOPE statement that contains a `This` function, MDX evaluates the `This` function within the context of the subcube defined by the SCOPE statement, not against the whole cube.</span></span>  
  
### <a name="this-function-example"></a><span data-ttu-id="b3ba3-117">Пример функции This</span><span class="sxs-lookup"><span data-stu-id="b3ba3-117">This Function Example</span></span>  
 <span data-ttu-id="b3ba3-118">В следующем примере команд скрипта многомерных выражений функция `This` используется для увеличения значения меры Amount в группе мер Finance образца куба [!INCLUDE[ssAWDWsp](../../../includes/ssawdwsp-md.md)] на 10 % для потомков элемента Redmond в измерении Customer.</span><span class="sxs-lookup"><span data-stu-id="b3ba3-118">The following MDX script command example uses the `This` function to increase the value of the Amount measure, in the Finance measure group of the [!INCLUDE[ssAWDWsp](../../../includes/ssawdwsp-md.md)] sample cube, to 10% higher for the children of the Redmond member in the Customer dimension:</span></span>  
  
```  
/* This SCOPE statement defines the current subcube */  
SCOPE([Customer].&[Redmond].MEMBERS,   
    [Measures].[Amount], *);  
        /* This expression sets the value of the Amount measure */  
        THIS = [Measures].[Amount] * 1.1;  
END SCOPE;  
```  
  
 <span data-ttu-id="b3ba3-119">Дополнительные сведения о синтаксисе `This` функции см. в [этой &#40;&#41;многомерных выражений ](/sql/mdx/this-mdx).</span><span class="sxs-lookup"><span data-stu-id="b3ba3-119">For more information on the syntax of the `This` function, see [This &#40;MDX&#41;](/sql/mdx/this-mdx).</span></span>  
  
## <a name="using-the-scope-statement"></a><span data-ttu-id="b3ba3-120">Инструкция SCOPE</span><span class="sxs-lookup"><span data-stu-id="b3ba3-120">Using the SCOPE Statement</span></span>  
 <span data-ttu-id="b3ba3-121">Инструкция SCOPE определяет текущий вложенный куб, содержащий другие выражения и инструкции многомерных выражений и определяющий для них область в рамках скрипта многомерных выражений.</span><span class="sxs-lookup"><span data-stu-id="b3ba3-121">The SCOPE statement defines the current subcube that contains, and specifies the scope of, other MDX expressions and statements within an MDX script.</span></span> <span data-ttu-id="b3ba3-122">В многомерных выражениях эти другие выражения и многомерные инструкции, включая функцию `This` и инструкцию CALCULATE, вычисляются в контексте данного вложенного куба.</span><span class="sxs-lookup"><span data-stu-id="b3ba3-122">MDX evaluates this other MDX expressions and statements, including the `This` function and the CALCULATE statement, within the context of the subcube.</span></span>  
  
 <span data-ttu-id="b3ba3-123">Инструкция SCOPE является динамической, но по своей природе она не итеративна.</span><span class="sxs-lookup"><span data-stu-id="b3ba3-123">A SCOPE statement is dynamic, but not iterative in nature.</span></span> <span data-ttu-id="b3ba3-124">Инструкции, содержащиеся в инструкции SCOPE, выполняются один раз, но сам вложенный куб может определяться динамически.</span><span class="sxs-lookup"><span data-stu-id="b3ba3-124">The statements contained within a SCOPE statement run once, but the subcube itself can be dynamically determined.</span></span> <span data-ttu-id="b3ba3-125">Пусть, например, создан куб SampleCube.</span><span class="sxs-lookup"><span data-stu-id="b3ba3-125">For example, you have a cube named SampleCube.</span></span> <span data-ttu-id="b3ba3-126">К кубу SampleCube можно обратиться со следующей инструкцией SCOPE для определения вложенного куба, определяющего контекст, аналогичный ALLMEMBERS в измерении Measures.</span><span class="sxs-lookup"><span data-stu-id="b3ba3-126">Against the SampleCube cube, you apply the following SCOPE statement to define a subcube the defines the context as the ALLMEMBERS within the Measures dimension:</span></span>  
  
 `SCOPE([Measures].ALLMEMBERS);`  
  
 `THIS = [Measures].ALLMEMBERS.COUNT;`  
  
 `END SCOPE;`  
  
 <span data-ttu-id="b3ba3-127">Эти инструкции и выражения в инструкции SCOPE выполняются лишь один раз.</span><span class="sxs-lookup"><span data-stu-id="b3ba3-127">The statements and expressions within this SCOPE statement run once.</span></span>  
  
 <span data-ttu-id="b3ba3-128">Пусть теперь пользователь обращается со следующим запросом многомерных выражений, содержащим одну меру ExistingMeasure, к кубу SampleCube.</span><span class="sxs-lookup"><span data-stu-id="b3ba3-128">Now, a business user runs the following MDX query that contains one measure, named ExistingMeasure, against the SampleCube cube:</span></span>  
  
 `WITH MEMBER [Measures].[NewMeasure] AS '1'`  
  
 `SELECT`  
  
 `[Measures].ALLMEMBERS ON COLUMNS,`  
  
 `[Customer].DEFAULTMEMBER ON ROWS`  
  
 `FROM`  
  
 `[SampleCube]`  
  
 <span data-ttu-id="b3ba3-129">Возвращенный этим запросом набор ячеек примерно соответствует выводу, приведенному в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="b3ba3-129">The cellset returned from the query resembles the output shown in the following table.</span></span>  
  
||<span data-ttu-id="b3ba3-130">[ExistingMeasure]</span><span class="sxs-lookup"><span data-stu-id="b3ba3-130">[ExistingMeasure]</span></span>|<span data-ttu-id="b3ba3-131">[NewMeasure]</span><span class="sxs-lookup"><span data-stu-id="b3ba3-131">[NewMeasure]</span></span>|  
|-|-------------------------|--------------------|  
|<span data-ttu-id="b3ba3-132">[Customer].[All]</span><span class="sxs-lookup"><span data-stu-id="b3ba3-132">[Customer].[All]</span></span>|<span data-ttu-id="b3ba3-133">2</span><span class="sxs-lookup"><span data-stu-id="b3ba3-133">2</span></span>|<span data-ttu-id="b3ba3-134">2</span><span class="sxs-lookup"><span data-stu-id="b3ba3-134">2</span></span>|  
  
 <span data-ttu-id="b3ba3-135">Обратите внимание, что в возвращаемом наборе ячеек значение ExistingMeasure, включенное в инструкцию SCOPE в данном скрипте многомерных выражений, динамически обновляется после определения меры NewMeasure.</span><span class="sxs-lookup"><span data-stu-id="b3ba3-135">Looking at the returned cellset, notice how the ExistingMeasure value, included in the SCOPE statement within the MDX script, is dynamically updated after the measure NewMeasure was defined.</span></span>  
  
 <span data-ttu-id="b3ba3-136">Инструкция SCOPE может быть вложена в другую инструкцию SCOPE.</span><span class="sxs-lookup"><span data-stu-id="b3ba3-136">A SCOPE statement can be nested within another SCOPE statement.</span></span> <span data-ttu-id="b3ba3-137">Однако, поскольку инструкция SCOPE не является итеративной, главное назначение вложенных инструкций SCOPE — дальнейшее подразделение вложенного куба для последующей обработки.</span><span class="sxs-lookup"><span data-stu-id="b3ba3-137">However, as the SCOPE statement is not iterative, the primary purpose for nesting SCOPE statements is to further subdivide a subcube for special treatment.</span></span>  
  
### <a name="scope-statement-example"></a><span data-ttu-id="b3ba3-138">Пример инструкции SCOPE</span><span class="sxs-lookup"><span data-stu-id="b3ba3-138">SCOPE Statement Example</span></span>  
 <span data-ttu-id="b3ba3-139">В следующем примере скрипта многомерных выражений инструкция SCOPE используется для увеличения значения меры Amount в группе мер Finance образца куба [!INCLUDE[ssAWDWsp](../../../includes/ssawdwsp-md.md)] на 10 % для потомков элемента Redmond в измерении Customer.</span><span class="sxs-lookup"><span data-stu-id="b3ba3-139">The following MDX script example uses a SCOPE statement to sets the value of the Amount measure, in the Finance measure group of the [!INCLUDE[ssAWDWsp](../../../includes/ssawdwsp-md.md)] sample cube, to 10% higher for the children of the Redmond member in the Customer dimension.</span></span> <span data-ttu-id="b3ba3-140">Однако этот вложенный куб далее изменяется следующей инструкцией SCOPE так, чтобы он включал в себя меру Amount для потомков 2002 календарного года.</span><span class="sxs-lookup"><span data-stu-id="b3ba3-140">However, another SCOPE statement changes the subcube to include the Amount measure for the children of the 2002 calendar year.</span></span> <span data-ttu-id="b3ba3-141">Затем мера Amount обрабатывается только для этого вложенного куба, оставляя статистические значения для меры Amount в других календарных годах без изменений.</span><span class="sxs-lookup"><span data-stu-id="b3ba3-141">Finally, the Amount measure is then aggregated only for that subcube, leaving the aggregated values for the Amount measure in other calendar years unchanged.</span></span>  
  
```  
/* Calculate the entire cube first. */  
CALCULATE;  
/* This SCOPE statement defines the current subcube */  
SCOPE([Customer].&[Redmond].MEMBERS,   
    [Measures].[Amount], *);  
        /* This expression sets the value of the Amount measure */  
        THIS = [Measures].[Amount] * 1.1;  
END SCOPE;  
```  
  
 <span data-ttu-id="b3ba3-142">Дополнительные сведения о синтаксисе инструкции SCOPE см. в разделе [Инструкция SCOPE (многомерные выражения)](/sql/mdx/mdx-scripting-scope).</span><span class="sxs-lookup"><span data-stu-id="b3ba3-142">For more information on the syntax of the SCOPE statement, see [SCOPE Statement &#40;MDX&#41;](/sql/mdx/mdx-scripting-scope).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3ba3-143">См. также:</span><span class="sxs-lookup"><span data-stu-id="b3ba3-143">See Also</span></span>  
 <span data-ttu-id="b3ba3-144">[Справочник по языку многомерных выражений &#40;&#41;многомерных выражений](/sql/mdx/mdx-language-reference-mdx) </span><span class="sxs-lookup"><span data-stu-id="b3ba3-144">[MDX Language Reference &#40;MDX&#41;](/sql/mdx/mdx-language-reference-mdx) </span></span>  
 <span data-ttu-id="b3ba3-145">[Базовый скрипт многомерных выражений &#40;многомерные выражения&#41;](the-basic-mdx-script-mdx.md) </span><span class="sxs-lookup"><span data-stu-id="b3ba3-145">[The Basic MDX Script &#40;MDX&#41;](the-basic-mdx-script-mdx.md) </span></span>  
 [<span data-ttu-id="b3ba3-146">Основные принципы запросов многомерных выражений (службы Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="b3ba3-146">MDX Query Fundamentals &#40;Analysis Services&#41;</span></span>](mdx-query-fundamentals-analysis-services.md)  
  
  
