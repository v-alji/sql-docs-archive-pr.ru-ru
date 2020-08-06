---
title: Перспективы в многомерных моделях | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- default members
- hiding objects from perspective
- renaming perspectives
- attributes [Analysis Services], default members
- removing perspectives
- perspectives [Analysis Services]
- names [Analysis Services], perspectives
- cubes [Analysis Services], perspectives
- deleting perspectives
ms.assetid: 5a3d6577-6833-4c24-820c-b65bb856157b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2d4be87ddbd691710b361d8b07d225bce37659fb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657364"
---
# <a name="perspectives-in-multidimensional-models"></a><span data-ttu-id="be2e7-102">Перспективы в многомерных моделях</span><span class="sxs-lookup"><span data-stu-id="be2e7-102">Perspectives in Multidimensional Models</span></span>
  <span data-ttu-id="be2e7-103">Перспектива представляет собой подмножество куба, созданное для отдельного приложения или группы пользователей.</span><span class="sxs-lookup"><span data-stu-id="be2e7-103">A perspective is a subset of a cube created for a particular application or group of users.</span></span> <span data-ttu-id="be2e7-104">Перспективой по умолчанию является собственно куб.</span><span class="sxs-lookup"><span data-stu-id="be2e7-104">The cube itself is the default perspective.</span></span> <span data-ttu-id="be2e7-105">Перспектива открыта для клиента в виде куба.</span><span class="sxs-lookup"><span data-stu-id="be2e7-105">A perspective is exposed to a client as a cube.</span></span> <span data-ttu-id="be2e7-106">Когда пользователь просматривает перспективу, она отображается в виде другого куба.</span><span class="sxs-lookup"><span data-stu-id="be2e7-106">When a user views a perspective, it appears like another cube.</span></span> <span data-ttu-id="be2e7-107">Изменения, выполненные с данными куба при обратной записи в перспективу, выполняются в исходном кубе.</span><span class="sxs-lookup"><span data-stu-id="be2e7-107">Any changes made to cube data through writeback in the perspective are to the original cube.</span></span> <span data-ttu-id="be2e7-108">Дополнительные сведения о представлениях см. в разделах [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]и [Перспективы](../multidimensional-models-olap-logical-cube-objects/perspectives.md).</span><span class="sxs-lookup"><span data-stu-id="be2e7-108">For more information about the views in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], see [Perspectives](../multidimensional-models-olap-logical-cube-objects/perspectives.md).</span></span>  
  
 <span data-ttu-id="be2e7-109">Используйте вкладку **Перспективы** в конструкторе кубов для создания или измерения перспектив в кубе.</span><span class="sxs-lookup"><span data-stu-id="be2e7-109">Use the **Perspectives** tab in Cube Designer to create or modify perspectives in a cube.</span></span> <span data-ttu-id="be2e7-110">Первый столбец на вкладке **Перспективы** — столбец **Объекты куба** , в котором перечислены объекты куба.</span><span class="sxs-lookup"><span data-stu-id="be2e7-110">The first column of the **Perspectives** tab is the **Cube Objects** column, which lists all the objects in the cube.</span></span> <span data-ttu-id="be2e7-111">Это соответствует перспективе куба по умолчанию, то есть собственно кубу.</span><span class="sxs-lookup"><span data-stu-id="be2e7-111">This corresponds to the default perspective for the cube, which is the cube itself.</span></span>  
  
## <a name="creating-or-deleting-perspectives"></a><span data-ttu-id="be2e7-112">Создание или удаление перспектив</span><span class="sxs-lookup"><span data-stu-id="be2e7-112">Creating or Deleting Perspectives</span></span>  
 <span data-ttu-id="be2e7-113">На вкладке **Перспективы** можно добавить перспективу с помощью команды **Создать перспективу** в меню **Куб** .</span><span class="sxs-lookup"><span data-stu-id="be2e7-113">You can add a perspective to the **Perspectives** tab by clicking **New Perspective** on the **Cube** menu.</span></span> <span data-ttu-id="be2e7-114">Можно нажать кнопку **Создать перспективу** на панели инструментов или щелкнуть правой кнопкой мыши в любом месте панели и выбрать в контекстном меню пункт **Создать перспективу** .</span><span class="sxs-lookup"><span data-stu-id="be2e7-114">You can also click the **New Perspective** button on the toolbar, or right-click anywhere in the pane and click **New Perspective** on the shortcut menu.</span></span> <span data-ttu-id="be2e7-115">К кубу можно добавлять любое количество перспектив.</span><span class="sxs-lookup"><span data-stu-id="be2e7-115">You can add any number of perspectives to a cube.</span></span>  
  
 <span data-ttu-id="be2e7-116">Для удаления перспективы сначала щелкните в любой ячейке столбца с перспективой, которую требуется удалить.</span><span class="sxs-lookup"><span data-stu-id="be2e7-116">To remove a perspective, first click any cell in the column for the perspective that you want to delete.</span></span> <span data-ttu-id="be2e7-117">Затем в меню **Куб** выберите пункт **Удалить перспективу**.</span><span class="sxs-lookup"><span data-stu-id="be2e7-117">Then, on the **Cube** menu, click **Delete Perspective**.</span></span> <span data-ttu-id="be2e7-118">Также можно нажать кнопку **Удалить перспективу** на панели инструментов или щелкнуть правой кнопкой мыши в любой ячейке перспективы, которую требуется удалить, и выбрать в контекстном меню пункт **Удалить перспективу** .</span><span class="sxs-lookup"><span data-stu-id="be2e7-118">You can also click the **Delete Perspective** button on the toolbar, or right-click any cell in the perspective you want to delete, and then click **Delete Perspective** on the shortcut menu.</span></span>  
  
## <a name="renaming-perspectives"></a><span data-ttu-id="be2e7-119">переименование перспектив</span><span class="sxs-lookup"><span data-stu-id="be2e7-119">Renaming Perspectives</span></span>  
 <span data-ttu-id="be2e7-120">В первой строке перспектив представлено имя перспективы.</span><span class="sxs-lookup"><span data-stu-id="be2e7-120">The first row of each perspective shows its name.</span></span> <span data-ttu-id="be2e7-121">При создании перспективы ее исходное имя — Perspective (далее следует порядковый номер, начинающийся с 1, если уже имеется проекция с именем Perspective).</span><span class="sxs-lookup"><span data-stu-id="be2e7-121">When you create a perspective, the name is initially Perspective (followed by an ordinal number, starting with 1, if there is already a perspective called Perspective).</span></span> <span data-ttu-id="be2e7-122">Щелкните имя для его редактирования.</span><span class="sxs-lookup"><span data-stu-id="be2e7-122">You can click the name to edit it.</span></span>  
  
## <a name="hiding-objects-from-a-perspective"></a><span data-ttu-id="be2e7-123">Скрытие объектов в перспективе</span><span class="sxs-lookup"><span data-stu-id="be2e7-123">Hiding Objects from a Perspective</span></span>  
 <span data-ttu-id="be2e7-124">Чтобы скрыть объект в перспективе, снимите флажок в строке, соответствующей объекту, в столбце перспективы.</span><span class="sxs-lookup"><span data-stu-id="be2e7-124">To hide an object from a perspective, clear the check box in the row that corresponds to the object in the column for the perspective.</span></span> <span data-ttu-id="be2e7-125">В перспективе можно скрыть следующие объекты куба:</span><span class="sxs-lookup"><span data-stu-id="be2e7-125">The cube objects that can be hidden from a perspective are:</span></span>  
  
-   <span data-ttu-id="be2e7-126">Группы мер</span><span class="sxs-lookup"><span data-stu-id="be2e7-126">Measure groups</span></span>  
  
-   <span data-ttu-id="be2e7-127">Меры</span><span class="sxs-lookup"><span data-stu-id="be2e7-127">Measures</span></span>  
  
-   <span data-ttu-id="be2e7-128">Измерения</span><span class="sxs-lookup"><span data-stu-id="be2e7-128">Dimensions</span></span>  
  
-   <span data-ttu-id="be2e7-129">Иерархии</span><span class="sxs-lookup"><span data-stu-id="be2e7-129">Hierarchies</span></span>  
  
-   <span data-ttu-id="be2e7-130">Именованные наборы</span><span class="sxs-lookup"><span data-stu-id="be2e7-130">Named sets</span></span>  
  
-   <span data-ttu-id="be2e7-131">Ключевые показатели эффективности</span><span class="sxs-lookup"><span data-stu-id="be2e7-131">KPIs</span></span>  
  
-   <span data-ttu-id="be2e7-132">Действия</span><span class="sxs-lookup"><span data-stu-id="be2e7-132">Actions</span></span>  
  
-   <span data-ttu-id="be2e7-133">Вычисляемые элементы</span><span class="sxs-lookup"><span data-stu-id="be2e7-133">Calculated members</span></span>  
  
 <span data-ttu-id="be2e7-134">Чтобы просмотреть объект, разверните категорию (**Группы мер**, **Измерения**, **Ключевые показатели эффективности**, **Вычисления**или **Действия**) для любого типа объекта в узле **Объекты куба**.</span><span class="sxs-lookup"><span data-stu-id="be2e7-134">To view any object, expand the category (**Measure Groups**, **Dimensions**, **KPIs**, **Calculations**, or **Actions**) for any object type under **Cube Objects**.</span></span> <span data-ttu-id="be2e7-135">Чтобы просмотреть иерархии или атрибуты в измерении, сначала разверните измерение, а затем строку **Иерархии** или **Атрибуты** .</span><span class="sxs-lookup"><span data-stu-id="be2e7-135">To view hierarchies or attributes in a dimension, first expand a dimension, and then expand the **Hierarchies** or **Attributes** row.</span></span> <span data-ttu-id="be2e7-136">Чтобы просмотреть меры в группе мер, разверните группу.</span><span class="sxs-lookup"><span data-stu-id="be2e7-136">To view measures in a measure group, expand the measure group.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be2e7-137">См. также:</span><span class="sxs-lookup"><span data-stu-id="be2e7-137">See Also</span></span>  
 [<span data-ttu-id="be2e7-138">Кубы в многомерных моделях</span><span class="sxs-lookup"><span data-stu-id="be2e7-138">Cubes in Multidimensional Models</span></span>](cubes-in-multidimensional-models.md)  
  
  
