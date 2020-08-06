---
title: Базовый скрипт МНОГОМЕРных выражений (многомерные выражения) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- default MDX scripts
- statements [MDX]
- expressions [MDX], scripts
- scripts [MDX], about scripts
ms.assetid: 83d9afda-7d34-42b5-8f28-20172a905f23
author: minewiskan
ms.author: owend
ms.openlocfilehash: de0d2fea002beda0eca480bd27140bdd202fcb83
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87737004"
---
# <a name="the-basic-mdx-script-mdx"></a><span data-ttu-id="762d6-102">Базовый скрипт многомерных выражений (многомерные выражения)</span><span class="sxs-lookup"><span data-stu-id="762d6-102">The Basic MDX Script (MDX)</span></span>
  <span data-ttu-id="762d6-103">Скрипт многомерных выражений (MDX) определяет процесс вычисления для куба в [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="762d6-103">A Multidimensional Expressions (MDX) script defines the calculation process for a cube in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="762d6-104">Существует два типа скриптов многомерных выражений.</span><span class="sxs-lookup"><span data-stu-id="762d6-104">There are two types of MDX scripts:</span></span>  
  
 <span data-ttu-id="762d6-105">**Скрипт многомерных выражений по умолчанию**</span><span class="sxs-lookup"><span data-stu-id="762d6-105">**The default MDX script**</span></span>  
 <span data-ttu-id="762d6-106">При создании куба службы [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] создают стандартный скрипт многомерных выражений для этого куба.</span><span class="sxs-lookup"><span data-stu-id="762d6-106">At the time that you create a cube, [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] creates a default MDX script for that cube.</span></span> <span data-ttu-id="762d6-107">В этом скрипте определяется этап вычисления для всего куба.</span><span class="sxs-lookup"><span data-stu-id="762d6-107">This script defines a calculation pass for the whole cube.</span></span>  
  
 <span data-ttu-id="762d6-108">**Пользовательский скрипт многомерных выражений**</span><span class="sxs-lookup"><span data-stu-id="762d6-108">**User-defined MDX script**</span></span>  
 <span data-ttu-id="762d6-109">После создания куба можно добавить пользовательские скрипты многомерных выражений, расширяющие характеристики вычисления куба.</span><span class="sxs-lookup"><span data-stu-id="762d6-109">After you have created a cube, you can add user-defined MDX scripts that extend the calculation capabilities of the cube.</span></span>  
  
## <a name="the-default-mdx-script"></a><span data-ttu-id="762d6-110">Скрипт многомерных выражений по умолчанию</span><span class="sxs-lookup"><span data-stu-id="762d6-110">The Default MDX Script</span></span>  
 <span data-ttu-id="762d6-111">Скрипт многомерных выражений по умолчанию, создаваемый службами [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] при определении куба, содержит одну инструкцию CALCULATE.</span><span class="sxs-lookup"><span data-stu-id="762d6-111">The default MDX script that [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] creates when you define a cube contains a single CALCULATE statement.</span></span> <span data-ttu-id="762d6-112">Эта инструкция CALCULATE находится в начале скрипта многомерных выражений по умолчанию и говорит о том, что весь куб должен быть рассчитан во время первого этапа вычислений.</span><span class="sxs-lookup"><span data-stu-id="762d6-112">This single CALCULATE statement is at the beginning of the default MDX script, and indicates that the entire cube should be calculated during the first calculation pass.</span></span>  
  
 <span data-ttu-id="762d6-113">Скрипт многомерных выражений по умолчанию также включает в себя команды, создающие именованные наборы, назначения и вычисляемые элементы, созданные в конструкторе кубов.</span><span class="sxs-lookup"><span data-stu-id="762d6-113">The default MDX script also contains the script commands that create named sets, assignments, and calculated members created in Cube Designer:</span></span>  
  
-   [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] <span data-ttu-id="762d6-114">добавляют команды непосредственно в скрипт многомерных выражений по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="762d6-114">directly adds script commands to the default MDX script.</span></span>  
  
-   <span data-ttu-id="762d6-115">Для каждого именованного набора в кубе в скрипт многомерных выражений по умолчанию добавляется соответствующая инструкция CREATE SET.</span><span class="sxs-lookup"><span data-stu-id="762d6-115">For each named set in the cube, a corresponding CREATE SET statement exists in the default MDX script.</span></span>  
  
-   <span data-ttu-id="762d6-116">Для каждого вычисляемого элемента в кубе в скрипт многомерных выражений по умолчанию добавляется соответствующая инструкция CREATE MEMBER.</span><span class="sxs-lookup"><span data-stu-id="762d6-116">For each calculated member defined in the cube, a corresponding CREATE MEMBER statement exists in the default MDX script.</span></span>  
  
 <span data-ttu-id="762d6-117">Порядком команд, именованных наборов и вычисляемых элементов в скрипте многомерных выражений по умолчанию можно управлять на вкладке **Вычисления** конструктора кубов.</span><span class="sxs-lookup"><span data-stu-id="762d6-117">You can control the order of script commands, named sets, and calculated members in the default MDX script by using the **Calculations** tab of Cube Designer.</span></span> <span data-ttu-id="762d6-118">Дополнительные сведения об определении вычислений, записываемых в скрипт многомерных выражений по умолчанию, см. в разделе [Вычисления в многомерных моделях](../calculations-in-multidimensional-models.md).</span><span class="sxs-lookup"><span data-stu-id="762d6-118">For more information on defining calculations stored in the default MDX script, see [Calculations in Multidimensional Models](../calculations-in-multidimensional-models.md).</span></span>  
  
 <span data-ttu-id="762d6-119">Если с кубом не связан ни один скрипт многомерных выражений, куб вычисляется по скрипту многомерных выражений по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="762d6-119">If there is no MDX script associated with a cube, the cube assumes the default MDX script.</span></span> <span data-ttu-id="762d6-120">Куб должен быть связан хотя бы с одним скриптом многомерных выражений, поскольку только в скрипте определяется порядок вычисления куба.</span><span class="sxs-lookup"><span data-stu-id="762d6-120">A cube needs to be associated with at least one MDX script because a cube relies on the MDX script to determine calculation behavior.</span></span> <span data-ttu-id="762d6-121">Другими словами, куб, не связанный со скриптом многомерных выражений или связанный с пустым скриптом многомерных выражений, не может и не будет вычислять значения ячеек.</span><span class="sxs-lookup"><span data-stu-id="762d6-121">In other words, a cube that was not associated with an MDX script or was associated with an empty MDX script could not and would not be able to calculate any cells.</span></span> <span data-ttu-id="762d6-122">Если кубы создаются программно при помощи команд языка скриптов служб Analysis Services (ASSL) или объектов AMO, рекомендуется создать для куба скрипт многомерных выражений по умолчанию с одной инструкцией CALCULATE.</span><span class="sxs-lookup"><span data-stu-id="762d6-122">If you programmatically create cubes, either by using Analysis Services Scripting Language (ASSL) commands or by using Analysis Management Objects (AMO), it is recommended that you create a default MDX script containing a single CALCULATE statement for the cube.</span></span>  
  
## <a name="mdx-script-content"></a><span data-ttu-id="762d6-123">Содержимое скрипта многомерных выражений</span><span class="sxs-lookup"><span data-stu-id="762d6-123">MDX Script Content</span></span>  
 <span data-ttu-id="762d6-124">Скрипт многомерных выражений может содержать следующие инструкции и выражения.</span><span class="sxs-lookup"><span data-stu-id="762d6-124">An MDX script can contain the following statements and expressions:</span></span>  
  
 <span data-ttu-id="762d6-125">Все инструкции сценариев многомерных выражений</span><span class="sxs-lookup"><span data-stu-id="762d6-125">All MDX scripting statements</span></span>  
 <span data-ttu-id="762d6-126">Инструкции скриптов многомерных выражений управляют контекстом и областью вычислений, а также поведением других инструкций в скрипте многомерных выражений.</span><span class="sxs-lookup"><span data-stu-id="762d6-126">In MDX scripts, MDX scripting statements control the context and scope of calculations, and manage the behavior of other statements in the MDX script.</span></span> <span data-ttu-id="762d6-127">В эту категорию входят следующие инструкции:</span><span class="sxs-lookup"><span data-stu-id="762d6-127">This category includes the following statements:</span></span>  
  
-   [<span data-ttu-id="762d6-128">СЧИТАЙТЕ</span><span class="sxs-lookup"><span data-stu-id="762d6-128">CALCULATE</span></span>](/sql/mdx/mdx-scripting-calculate)  
  
-   [<span data-ttu-id="762d6-129">ФИКСИРОВАТЬ</span><span class="sxs-lookup"><span data-stu-id="762d6-129">FREEZE</span></span>](/sql/mdx/mdx-scripting-freeze)  
  
-   [<span data-ttu-id="762d6-130">КОТОРЫХ</span><span class="sxs-lookup"><span data-stu-id="762d6-130">SCOPE</span></span>](/sql/mdx/mdx-scripting-scope)  
  
 <span data-ttu-id="762d6-131">Дополнительные сведения об инструкциях сценариев многомерных выражений см. в разделе [Инструкции сценариев многомерных выражений (многомерные выражения)](/sql/mdx/mdx-scripting-statements-mdx).</span><span class="sxs-lookup"><span data-stu-id="762d6-131">For more information on MDX scripting statements, see [MDX Scripting Statements &#40;MDX&#41;](/sql/mdx/mdx-scripting-statements-mdx).</span></span>  
  
 [<span data-ttu-id="762d6-132">CREATE MEMBER</span><span class="sxs-lookup"><span data-stu-id="762d6-132">CREATE MEMBER</span></span>](/sql/mdx/mdx-data-definition-create-member)  
 <span data-ttu-id="762d6-133">Инструкция CREATE MEMBER служит для создания вычисляемых элементов.</span><span class="sxs-lookup"><span data-stu-id="762d6-133">The CREATE MEMBER statement creates calculated members.</span></span> <span data-ttu-id="762d6-134">Дополнительные сведения о создании вычисляемых элементов см. в разделе [Создание вычисляемых элементов в многомерных выражениях (многомерные выражения)](mdx-calculated-members-building-calculated-members.md).</span><span class="sxs-lookup"><span data-stu-id="762d6-134">For more information about how to create calculated members, see [Building Calculated Members in MDX &#40;MDX&#41;](mdx-calculated-members-building-calculated-members.md).</span></span>  
  
 [<span data-ttu-id="762d6-135">CREATE SET</span><span class="sxs-lookup"><span data-stu-id="762d6-135">CREATE SET</span></span>](/sql/mdx/mdx-data-definition-create-set)  
 <span data-ttu-id="762d6-136">Инструкция CREATE SET служит для создания именованных наборов.</span><span class="sxs-lookup"><span data-stu-id="762d6-136">The CREATE SET statement creates named sets.</span></span> <span data-ttu-id="762d6-137">Дополнительные сведения о создании именованных наборов см. в разделе [Построение именованных наборов в многомерных выражениях (многомерные выражения)](mdx-named-sets-building-named-sets.md).</span><span class="sxs-lookup"><span data-stu-id="762d6-137">For more information about how to create names sets, see [Building Named Sets in MDX &#40;MDX&#41;](mdx-named-sets-building-named-sets.md).</span></span>  
  
 <span data-ttu-id="762d6-138">Условные операторы</span><span class="sxs-lookup"><span data-stu-id="762d6-138">Conditional statements</span></span>  
 <span data-ttu-id="762d6-139">Условные инструкции позволяют создавать ветвления в скриптах многомерных выражений.</span><span class="sxs-lookup"><span data-stu-id="762d6-139">Conditional statements add conditional logic to MDX scripts.</span></span> <span data-ttu-id="762d6-140">В эту категорию входят инструкции [CASE](/sql/mdx/case-statement-mdx) и [IF](/sql/mdx/mdx-scripting-if) .</span><span class="sxs-lookup"><span data-stu-id="762d6-140">This category includes the [CASE](/sql/mdx/case-statement-mdx) and [IF](/sql/mdx/mdx-scripting-if) statements.</span></span>  
  
 <span data-ttu-id="762d6-141">Выражения присваивания</span><span class="sxs-lookup"><span data-stu-id="762d6-141">Assignment expressions</span></span>  
 <span data-ttu-id="762d6-142">Выражения присваивания присваивают ограниченному вложенному кубу некое выражение, например просто значение.</span><span class="sxs-lookup"><span data-stu-id="762d6-142">An assignment expression assigns an expression, such as a value, to a constrained subcube.</span></span> <span data-ttu-id="762d6-143">Выражение ограниченного вложенного куба — это коллекция ограниченных выражений наборов, определяющих «грани» вложенного куба в скрипте многомерных выражений.</span><span class="sxs-lookup"><span data-stu-id="762d6-143">A constrained subcube expression is a collection of constrained set expressions that define the "edges" of a subcube within an MDX script.</span></span> <span data-ttu-id="762d6-144">Ниже продемонстрирован синтаксис выражения ограниченного вложенного куба:</span><span class="sxs-lookup"><span data-stu-id="762d6-144">The following codes shows the syntax for a constrained subcube expression:</span></span>  
  
```  
<Constrained subcube> ::= (   
    ( <Constrained set> [<Crossjoin operator> <Constrained set>...] |  
    <ROOT function> |  
    <TREE function> |  
    LEAVES() |  
    * ) [, <Constrained subcube>...]  
<Constrained set> ::=   
    <Natural hierarchy>.MEMBERS |   
    <Natural hierarchy>.LEVEL(<numeric expression>).MEMBERS |   
    { <Natural hierarchy member> } |   
    DESCENDANTS( <Natural hierarchy member>, <Level expression>, ( SELF | AFTER | SELF_AND_AFTER ) ) |   
    DESCENDANTS( <Natural hierarchy member>, , LEAVES )  
<Natural hierarchy> ::= <Hierarchy identifier>  
<Natural hierarchy member> ::= <Natural hierarchy>.<identifier>[.<identifier>...]  
```  
  
## <a name="see-also"></a><span data-ttu-id="762d6-145">См. также:</span><span class="sxs-lookup"><span data-stu-id="762d6-145">See Also</span></span>  
 <span data-ttu-id="762d6-146">[Справочник по языку многомерных выражений &#40;&#41;многомерных выражений](/sql/mdx/mdx-language-reference-mdx) </span><span class="sxs-lookup"><span data-stu-id="762d6-146">[MDX Language Reference &#40;MDX&#41;](/sql/mdx/mdx-language-reference-mdx) </span></span>  
 [<span data-ttu-id="762d6-147">Основные принципы создания скриптов многомерных выражений (службы Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="762d6-147">MDX Scripting Fundamentals &#40;Analysis Services&#41;</span></span>](mdx-scripting-fundamentals-analysis-services.md)  
  
  
