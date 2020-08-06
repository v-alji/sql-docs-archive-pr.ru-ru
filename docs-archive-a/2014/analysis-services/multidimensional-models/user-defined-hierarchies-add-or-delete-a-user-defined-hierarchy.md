---
title: Добавление или удаление пользовательской иерархии | Документация Майкрософт
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- hierarchies [Analysis Services], adding
- removing hierarchies
- adding hierarchies
- deleting hierarchies
- hierarchies [Analysis Services], removing
ms.assetid: 953818b4-9543-4c01-bb20-1d45ec6dfb91
author: minewiskan
ms.author: owend
ms.openlocfilehash: d20404a1d93d57221eb830366392eb90600f26c7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665611"
---
# <a name="add-or-delete-a-user-defined-hierarchy"></a><span data-ttu-id="b3d0f-102">Добавление или удаление пользовательскую иерархию</span><span class="sxs-lookup"><span data-stu-id="b3d0f-102">Add or Delete a User-Defined Hierarchy</span></span>
  <span data-ttu-id="b3d0f-103">Добавление пользовательской иерархии в измерение и ее удаление производится на вкладке **Структура измерения** конструктора измерений в среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b3d0f-103">You add a user-defined hierarchy to or remove a user-defined hierarchy from a dimension on the **Dimension Structure** tab in Dimension Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="b3d0f-104">При добавлении пользовательской иерархии она будет недоступна для пользователей до тех пор, пока ее экземпляр не будет создан в экземпляре служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] и пока не выполнена обработка измерения.</span><span class="sxs-lookup"><span data-stu-id="b3d0f-104">When you add a user-defined hierarchy, it is not available to users until it is instantiated in an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance and the dimension is processed.</span></span> <span data-ttu-id="b3d0f-105">Дополнительные сведения см. в разделе [базы данных многомерной модели &#40;службы SSAS&#41;](multidimensional-model-databases-ssas.md) и [Обработка объектов многомерной модели](processing-a-multidimensional-model-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="b3d0f-105">For more information, see [Multidimensional Model Databases &#40;SSAS&#41;](multidimensional-model-databases-ssas.md) and [Multidimensional Model Object Processing](processing-a-multidimensional-model-analysis-services.md).</span></span>  
  
### <a name="to-add-a-user-defined-hierarchy-to-a-dimension"></a><span data-ttu-id="b3d0f-106">Добавление пользовательской иерархии к измерению</span><span class="sxs-lookup"><span data-stu-id="b3d0f-106">To add a user-defined hierarchy to a dimension</span></span>  
  
1.  <span data-ttu-id="b3d0f-107">В среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]откройте соответствующий проект служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , а затем откройте нужное измерение.</span><span class="sxs-lookup"><span data-stu-id="b3d0f-107">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the appropriate [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project, and then open the dimension with which you want to work.</span></span>  
  
     <span data-ttu-id="b3d0f-108">Измерение открывается в конструкторе измерений на вкладке **Структура измерения** .</span><span class="sxs-lookup"><span data-stu-id="b3d0f-108">The dimension opens in Dimension Designer on the **Dimension Structure** tab.</span></span>  
  
2.  <span data-ttu-id="b3d0f-109">Перетащите атрибут, который хотите использовать в пользовательской иерархии, из панели **Атрибуты** на панель **Иерархии** .</span><span class="sxs-lookup"><span data-stu-id="b3d0f-109">From the **Attributes** pane, drag an attribute that you want to use in the user-defined hierarchy to the **Hierarchies** pane.</span></span>  
  
3.  <span data-ttu-id="b3d0f-110">Перетащите дополнительные атрибуты, чтобы сформировать уровни в пользовательской иерархии.</span><span class="sxs-lookup"><span data-stu-id="b3d0f-110">Drag additional attributes to form levels in the user-defined hierarchy.</span></span>  
  
     <span data-ttu-id="b3d0f-111">Порядок, в котором атрибуты перечислены в иерархии, имеет значение.</span><span class="sxs-lookup"><span data-stu-id="b3d0f-111">The order in which attributes are listed in the hierarchy is important.</span></span> <span data-ttu-id="b3d0f-112">Например, в иерархии времени годы должны находиться выше дней.</span><span class="sxs-lookup"><span data-stu-id="b3d0f-112">For example, in a time hierarchy, years should appear higher in the hierarchy list than days.</span></span>  
  
4.  <span data-ttu-id="b3d0f-113">При необходимости можно переупорядочить уровни в пользовательской иерархии, перетащив их на соответствующие позиции.</span><span class="sxs-lookup"><span data-stu-id="b3d0f-113">Optionally, rearrange the levels in the user-defined hierarchy by dragging them to the correct positions.</span></span>  
  
5.  <span data-ttu-id="b3d0f-114">При необходимости измените свойства пользовательской иерархии или ее уровней.</span><span class="sxs-lookup"><span data-stu-id="b3d0f-114">Optionally, modify properties of the user-defined hierarchy or its levels.</span></span>  
  
     <span data-ttu-id="b3d0f-115">Например, можно указать имя для пользовательской иерархии, переименовать один или несколько ее уровней и определить пользовательское имя для уровня «Все».</span><span class="sxs-lookup"><span data-stu-id="b3d0f-115">For example, you might want to specify a name for the user-defined hierarchy, rename one or more of its levels, and define a custom name for the All level.</span></span> <span data-ttu-id="b3d0f-116">Дополнительные сведения см. в разделе [Свойства пользовательской иерархии](../multidimensional-models-olap-logical-dimension-objects/user-hierarchies-properties.md)и [Свойства уровня &#91;павед за&#93;](../multidimensional-models-olap-logical-dimension-objects/user-hierarchies-level-properties.md).</span><span class="sxs-lookup"><span data-stu-id="b3d0f-116">For more information, see [User Hierarchy Properties](../multidimensional-models-olap-logical-dimension-objects/user-hierarchies-properties.md), and [Level Properties &#91;Paved Over&#93;](../multidimensional-models-olap-logical-dimension-objects/user-hierarchies-level-properties.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b3d0f-117">По умолчанию пользовательская иерархия — это просто путь детализации данных для пользователей.</span><span class="sxs-lookup"><span data-stu-id="b3d0f-117">By default, a user-defined hierarchy is just a path that enables users to drill down for information.</span></span> <span data-ttu-id="b3d0f-118">Но если между уровнями имеются связи, производительность запросов может быть увеличена путем настройки связей атрибутов между уровнями.</span><span class="sxs-lookup"><span data-stu-id="b3d0f-118">However, if relationships exist between levels, you can increase query performance by configuring attribute relationships between levels.</span></span> <span data-ttu-id="b3d0f-119">Дополнительные сведения см. в разделах [Связи атрибутов](../multidimensional-models-olap-logical-dimension-objects/attribute-relationships.md) и [Определение связей атрибутов](attribute-relationships-define.md).</span><span class="sxs-lookup"><span data-stu-id="b3d0f-119">For more information, see [Attribute Relationships](../multidimensional-models-olap-logical-dimension-objects/attribute-relationships.md) and [Define Attribute Relationships](attribute-relationships-define.md).</span></span>  
  
### <a name="to-remove-a-user-defined-hierarchy-from-a-dimension"></a><span data-ttu-id="b3d0f-120">Удаление пользовательской иерархии из измерения</span><span class="sxs-lookup"><span data-stu-id="b3d0f-120">To remove a user-defined hierarchy from a dimension</span></span>  
  
-   <span data-ttu-id="b3d0f-121">На панели **Иерархии** вкладки **Структура измерения** выберите пользовательскую иерархию, которую хотите удалить.</span><span class="sxs-lookup"><span data-stu-id="b3d0f-121">On the **Dimension Structure** tab, click the user-defined hierarchy that you want to remove in the **Hierarchies** pane.</span></span> <span data-ttu-id="b3d0f-122">На панели инструментов щелкните **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="b3d0f-122">On the toolbar, click **Delete**.</span></span>  
  
     - <span data-ttu-id="b3d0f-123">или</span><span class="sxs-lookup"><span data-stu-id="b3d0f-123">or -</span></span>  
  
-   <span data-ttu-id="b3d0f-124">На панели **Иерархия** щелкните правой кнопкой мыши пользовательскую иерархию, которую необходимо удалить, и выберите **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="b3d0f-124">Right-click the user-defined hierarchy that you want to remove in the **Hierarchies** pane and then click **Delete**.</span></span>  
  
     - <span data-ttu-id="b3d0f-125">или</span><span class="sxs-lookup"><span data-stu-id="b3d0f-125">or -</span></span>  
  
-   <span data-ttu-id="b3d0f-126">Удалите иерархию из области конструктора с помощью мыши.</span><span class="sxs-lookup"><span data-stu-id="b3d0f-126">Drag the user-defined hierarchy off of the design surface.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3d0f-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="b3d0f-127">See Also</span></span>  
 <span data-ttu-id="b3d0f-128">[Пользовательские иерархии](../multidimensional-models-olap-logical-dimension-objects/user-hierarchies.md) </span><span class="sxs-lookup"><span data-stu-id="b3d0f-128">[User Hierarchies](../multidimensional-models-olap-logical-dimension-objects/user-hierarchies.md) </span></span>  
 [<span data-ttu-id="b3d0f-129">Создание пользовательских иерархий</span><span class="sxs-lookup"><span data-stu-id="b3d0f-129">Create User-Defined Hierarchies</span></span>](user-defined-hierarchies-create.md)  
  
  
