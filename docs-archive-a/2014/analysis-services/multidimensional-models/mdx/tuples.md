---
title: Кортежи | Документация Майкрософт
ms.custom: ''
ms.date: 07/17/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 35b629ae-b1ef-44b1-b556-96956aeb56e7
author: minewiskan
ms.author: owend
ms.openlocfilehash: c39d03d60cb66f3b2e26b2e660bd85f4e5e9d4ec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87736995"
---
# <a name="tuples"></a><span data-ttu-id="4ca69-102">Кортежи</span><span class="sxs-lookup"><span data-stu-id="4ca69-102">Tuples</span></span>
  <span data-ttu-id="4ca69-103">Кортеж однозначно определяет срез данных в кубе.</span><span class="sxs-lookup"><span data-stu-id="4ca69-103">A tuple uniquely identifies a slice of data from a cube.</span></span> <span data-ttu-id="4ca69-104">Кортеж формируется сочетанием элементов измерения, если отсутствует несколько элементов, принадлежащих одной иерархии.</span><span class="sxs-lookup"><span data-stu-id="4ca69-104">The tuple is formed by a combination of dimension members, as long as there are no two or more members that belong to the same hierarchy.</span></span>  
  
## <a name="implicit-or-default-attribute-members-in-a-tuple"></a><span data-ttu-id="4ca69-105">Неявные элементы атрибута или элементы атрибута по умолчанию в кортеже</span><span class="sxs-lookup"><span data-stu-id="4ca69-105">Implicit or default attribute members in a tuple</span></span>  
 <span data-ttu-id="4ca69-106">При определении кортежа в запросе многомерных выражений или в многомерном выражении не обязательно явно включать элемент атрибута из каждой иерархии атрибута.</span><span class="sxs-lookup"><span data-stu-id="4ca69-106">When defining a tuple in an MDX query or expression, you do not need to explicitly include the attribute member from every attribute hierarchy.</span></span> <span data-ttu-id="4ca69-107">Если элемент из иерархии атрибута не включен явно в запрос или выражение, в кортеж неявным образом включается элемент по умолчанию данной иерархии атрибута.</span><span class="sxs-lookup"><span data-stu-id="4ca69-107">If a member from an attribute hierarchy is not explicitly included in a query or an expression, the default member for that attribute hierarchy is the attribute member implicitly included in the tuple.</span></span> <span data-ttu-id="4ca69-108">Если в кубе явно не указано обратное, элементом по умолчанию любой иерархии атрибута считается элемент «(Все)», если он существует.</span><span class="sxs-lookup"><span data-stu-id="4ca69-108">Unless otherwise explicitly defined in a cube, the default member for every attribute hierarchy is the (All) member, if an (All) member exists.</span></span> <span data-ttu-id="4ca69-109">Если такой элемент отсутствует в иерархии атрибута, элементом по умолчанию считается элемент верхнего уровня иерархии.</span><span class="sxs-lookup"><span data-stu-id="4ca69-109">If an (All) member does not exist within an attribute hierarchy, the default member is a member of the attribute hierarchy's top level.</span></span> <span data-ttu-id="4ca69-110">Мерой по умолчанию является первая мера указанного куба, если только мера по умолчанию не определена явно.</span><span class="sxs-lookup"><span data-stu-id="4ca69-110">The default measure is the first measure specified in the cube, unless a default measure is explicitly defined.</span></span> <span data-ttu-id="4ca69-111">Дополнительные сведения см. в разделах [Определение элемента по умолчанию](../attribute-properties-define-a-default-member.md) и [DefaultMember (многомерные выражения)](/sql/mdx/defaultmember-mdx).</span><span class="sxs-lookup"><span data-stu-id="4ca69-111">For more information, see [Define a Default Member](../attribute-properties-define-a-default-member.md) and [DefaultMember &#40;MDX&#41;](/sql/mdx/defaultmember-mdx).</span></span>  
  
 <span data-ttu-id="4ca69-112">Например, следующий кортеж определяет одну ячейку в базе данных Adventure Works, явно определяя только один элемент в измерении Measures.</span><span class="sxs-lookup"><span data-stu-id="4ca69-112">For example, the following tuple identifies a single cell in the Adventure Works database by explicitly defining only a single member of the Measures dimension.</span></span>  
  
```  
(Measures.[Reseller Sales Amount])  
```  
  
 <span data-ttu-id="4ca69-113">В предыдущем примере уникально определена ячейка, состоящая из элемента Reseller Sales Amount из измерения Measures и элемента по умолчанию из каждой иерархии атрибута в кубе.</span><span class="sxs-lookup"><span data-stu-id="4ca69-113">The previous example uniquely identifies the cell consisting of the Reseller Sales Amount member from the Measures dimension and the default member from every attribute hierarchy in the cube.</span></span> <span data-ttu-id="4ca69-114">Элементом по умолчанию для каждой иерархии атрибута, кроме Destination Currency, является элемент «(Все)».</span><span class="sxs-lookup"><span data-stu-id="4ca69-114">The default member is the (All) member for every attribute hierarchy other than the Destination Currency attribute hierarchy.</span></span> <span data-ttu-id="4ca69-115">Элементом по умолчанию для иерархии Destination Currency является элемент US Dollar (он определен в скрипте многомерных выражений в кубе Adventure Works).</span><span class="sxs-lookup"><span data-stu-id="4ca69-115">The default member for the Destination Currency hierarchy is the US Dollar member (this default member is defined in the MDX script for the Adventure Works cube).</span></span>  
  
 <span data-ttu-id="4ca69-116">Следующий запрос возвращает значение ячейки, на которую ссылается кортеж, указанный в предыдущем примере ($80 450 596,98).</span><span class="sxs-lookup"><span data-stu-id="4ca69-116">The following query returns the value for the cell referenced by the tuple specified in the previous example, ($80,450.596.98).</span></span>  
  
```  
SELECT   
Measures.[Reseller Sales Amount] ON COLUMNS   
FROM [Adventure Works]  
```  
  
> [!NOTE]  
>  <span data-ttu-id="4ca69-117">При определении оси для набора (в данном случае состоящего из одного кортежа) в запросе набор для оси столбцов необходимо указать перед набором для оси строк.</span><span class="sxs-lookup"><span data-stu-id="4ca69-117">When you specify an axis for a set (in this case composed of a single tuple) in a query, you must begin by specifying a set for the column axis before specifying a set for the row axis.</span></span> <span data-ttu-id="4ca69-118">Ось столбцов называют *ось(0)* или просто *0*.</span><span class="sxs-lookup"><span data-stu-id="4ca69-118">The column axis can also be referred to as *axis(0)* or simply *0*.</span></span> <span data-ttu-id="4ca69-119">Дополнительные сведения о запросах многомерных выражений см. в разделе [Базовый запрос многомерных выражений (многомерные выражения)](mdx-query-the-basic-query.md).</span><span class="sxs-lookup"><span data-stu-id="4ca69-119">For more information about MDX queries, see [The Basic MDX Query &#40;MDX&#41;](mdx-query-the-basic-query.md).</span></span>  
  
### <a name="tuples-as-values-or-member-references"></a><span data-ttu-id="4ca69-120">Кортежи в качестве значений или ссылок на элементы</span><span class="sxs-lookup"><span data-stu-id="4ca69-120">Tuples as values or member references</span></span>  
 <span data-ttu-id="4ca69-121">Кортеж можно использовать в запросе, чтобы вернуть значение ячейки, на которую он ссылается, как показано в предыдущем примере.</span><span class="sxs-lookup"><span data-stu-id="4ca69-121">You can use a tuple in a query to return the value in the cell that is referenced by the tuple, as in the previous example.</span></span> <span data-ttu-id="4ca69-122">Кроме того, кортеж можно использовать в выражении для явной ссылки на элементы, указанные в нем.</span><span class="sxs-lookup"><span data-stu-id="4ca69-122">Or you can use a tuple in an expression to explicitly refer to the members specified in the tuple.</span></span> <span data-ttu-id="4ca69-123">В запросе или выражении можно использовать функции, которые возвращают кортежи или работают с ними.</span><span class="sxs-lookup"><span data-stu-id="4ca69-123">The query or the expression can utilize functions that either return or consume tuples.</span></span> <span data-ttu-id="4ca69-124">Кортеж можно использовать для ссылки на значение ячейки, на которую он указывает, или для определения сочетания элементов для передачи в другие функции.</span><span class="sxs-lookup"><span data-stu-id="4ca69-124">A tuple can be used to either refer to the value of the cell that the tuple specifies, or to specify a combination of members when utilized in a function.</span></span>  
  
### <a name="tuple-dimensionality"></a><span data-ttu-id="4ca69-125">Размерность кортежа</span><span class="sxs-lookup"><span data-stu-id="4ca69-125">Tuple dimensionality</span></span>  
 <span data-ttu-id="4ca69-126">*Размерностью* кортежа называют последовательность или порядок его элементов.</span><span class="sxs-lookup"><span data-stu-id="4ca69-126">The *dimensionality* of a tuple refers to the sequence or order of the members in the tuple.</span></span> <span data-ttu-id="4ca69-127">Поскольку неявные элементы всегда расположены в одном и том же порядке, размерность практически всегда зависит от элементов кортежа, определенных явно.</span><span class="sxs-lookup"><span data-stu-id="4ca69-127">Since the implicit members always occur in the same order, dimensionality is most often thought of in terms of the explicitly defined members of the tuple.</span></span> <span data-ttu-id="4ca69-128">Порядок элементов кортежа важен при определении набора кортежей.</span><span class="sxs-lookup"><span data-stu-id="4ca69-128">The ordering of the members of the tuple is important when you define a set of tuples.</span></span> <span data-ttu-id="4ca69-129">В следующем примере кортеж содержит два элемента по оси столбцов.</span><span class="sxs-lookup"><span data-stu-id="4ca69-129">The following example includes two members in a tuple on the column axis.</span></span>  
  
```  
SELECT   
([Measures].[Reseller Sales Amount],[Date].[Calendar Year].[CY 2004]) ON COLUMNS   
FROM [Adventure Works]  
```  
  
> [!NOTE]  
>  <span data-ttu-id="4ca69-130">Если явно указывается элемент кортежа из нескольких измерений, весь кортеж необходимо заключить в скобки.</span><span class="sxs-lookup"><span data-stu-id="4ca69-130">When you explicitly specify a member in a tuple from more than one dimension, you must include the entire tuple in parentheses.</span></span> <span data-ttu-id="4ca69-131">Если указывается только один элемент кортежа, скобки использовать не обязательно.</span><span class="sxs-lookup"><span data-stu-id="4ca69-131">When only specifying a single member in a tuple, parentheses are optional.</span></span>  
  
 <span data-ttu-id="4ca69-132">Кортеж в запросе в предыдущем примере возвращает ячейку куба на пересечении меры Reseller Sales Amount измерения Measures и элемента CY 2004 иерархии атрибута Calendar Year в измерении Date.</span><span class="sxs-lookup"><span data-stu-id="4ca69-132">The tuple in the query in the previous example specifies the return of the cube cell at the intersection of the Reseller Sales Amount Measure of the Measures dimension and the CY 2004 member of the Calendar Year attribute hierarchy in the Date dimension.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4ca69-133">На элемент атрибута можно ссылаться по имени или ключу.</span><span class="sxs-lookup"><span data-stu-id="4ca69-133">An attribute member can be referred by either its member name or its member key.</span></span> <span data-ttu-id="4ca69-134">В предыдущем примере ссылку [CY 2004] можно изменить на &[2004].</span><span class="sxs-lookup"><span data-stu-id="4ca69-134">In the previous example, you could replace the reference to [CY 2004] with &[2004].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ca69-135">См. также:</span><span class="sxs-lookup"><span data-stu-id="4ca69-135">See Also</span></span>  
 <span data-ttu-id="4ca69-136">[Основные понятия в Analysis Services &#40;многомерных выражений&#41;](../key-concepts-in-mdx-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="4ca69-136">[Key Concepts in MDX &#40;Analysis Services&#41;](../key-concepts-in-mdx-analysis-services.md) </span></span>  
 <span data-ttu-id="4ca69-137">[Пространство куба](cube-space.md) </span><span class="sxs-lookup"><span data-stu-id="4ca69-137">[Cube Space](cube-space.md) </span></span>  
 <span data-ttu-id="4ca69-138">[Автоматической проверки существования](autoexists.md) </span><span class="sxs-lookup"><span data-stu-id="4ca69-138">[Autoexists](autoexists.md) </span></span>  
 [<span data-ttu-id="4ca69-139">Работа с элементами, кортежами и наборами (многомерные выражения)</span><span class="sxs-lookup"><span data-stu-id="4ca69-139">Working with Members, Tuples, and Sets &#40;MDX&#41;</span></span>](working-with-members-tuples-and-sets-mdx.md)  
  
  
