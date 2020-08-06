---
title: Задание свойств задачи или контейнера | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- tasks [Integration Services], properties
ms.assetid: 52d47ca4-fb8c-493d-8b2b-48bb269f859b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0a4c556b94af02c2f874f2740a70b1294c35e653
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751271"
---
# <a name="set-the-properties-of-a-task-or-container"></a><span data-ttu-id="e8d6c-102">Задание свойств задач или контейнеров</span><span class="sxs-lookup"><span data-stu-id="e8d6c-102">Set the Properties of a Task or Container</span></span>
  <span data-ttu-id="e8d6c-103">Большинство свойств задач и контейнеров можно задать с помощью окна **Свойства** .</span><span class="sxs-lookup"><span data-stu-id="e8d6c-103">You can set most properties of tasks and containers by using the **Properties** window.</span></span> <span data-ttu-id="e8d6c-104">Исключение составляют свойства коллекций задач и свойства, задание которых в окне **Свойства** было бы слишком сложным.</span><span class="sxs-lookup"><span data-stu-id="e8d6c-104">The exceptions are properties of task collections and properties that are too complex to set by using the **Properties** window.</span></span> <span data-ttu-id="e8d6c-105">Например, нельзя настроить перечислитель, который контейнер «цикл по каждому элементу» использует в окне **Свойства** .</span><span class="sxs-lookup"><span data-stu-id="e8d6c-105">For example, you cannot configure the enumerator that the Foreach Loop container uses in the **Properties** window.</span></span> <span data-ttu-id="e8d6c-106">Для задания таких сложных свойств следует использовать редактор задачи или контейнера.</span><span class="sxs-lookup"><span data-stu-id="e8d6c-106">You must use a task or container editor to set these complex properties.</span></span> <span data-ttu-id="e8d6c-107">У большинства редакторов задач и контейнеров имеется несколько узлов, содержащих связанные свойства.</span><span class="sxs-lookup"><span data-stu-id="e8d6c-107">Most task and container editors have multiple nodes and each node contains related properties.</span></span> <span data-ttu-id="e8d6c-108">Имя узла указывает на субъект свойств, содержащихся в узле.</span><span class="sxs-lookup"><span data-stu-id="e8d6c-108">The name of the node indicates the subject of the properties that the node contains.</span></span>  
  
 <span data-ttu-id="e8d6c-109">Следующие процедуры описывают задание свойств задачи или контейнера с помощью окон **Свойства** либо с помощью соответствующего редактора задачи или контейнера.</span><span class="sxs-lookup"><span data-stu-id="e8d6c-109">The following procedures describe how to set the properties of a task or container by using either the **Properties** windows, or the corresponding task or container editor.</span></span>  
  
### <a name="to-set-the-properties-of-a-task-or-container-by-using-the-properties-window"></a><span data-ttu-id="e8d6c-110">Задание свойств задачи или контейнера с помощью окна «Свойства»</span><span class="sxs-lookup"><span data-stu-id="e8d6c-110">To set the properties of a task or container by using the Properties window</span></span>  
  
1.  <span data-ttu-id="e8d6c-111">В среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]откройте проект служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , содержащий необходимый пакет.</span><span class="sxs-lookup"><span data-stu-id="e8d6c-111">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="e8d6c-112">Чтобы открыть пакет, дважды щелкните его в обозревателе решений.</span><span class="sxs-lookup"><span data-stu-id="e8d6c-112">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="e8d6c-113">Перейдите на вкладку **Поток управления** .</span><span class="sxs-lookup"><span data-stu-id="e8d6c-113">Click the **Control Flow** tab.</span></span>  
  
4.  <span data-ttu-id="e8d6c-114">В области конструктора на вкладке **Поток управления** щелкните правой кнопкой мыши задачу или контейнер, затем выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="e8d6c-114">On the design surface of the **Control Flow** tab, right-click the task or container, and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="e8d6c-115">В окне **Свойства** обновите значение свойства.</span><span class="sxs-lookup"><span data-stu-id="e8d6c-115">In the **Properties** window, update the property value.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e8d6c-116">Большинство свойств можно установить, введя значение в текстовое поле или выбрав его из списка.</span><span class="sxs-lookup"><span data-stu-id="e8d6c-116">Most properties can be set by typing a value directly in the text box, or by selecting a value from a list.</span></span> <span data-ttu-id="e8d6c-117">Однако некоторые свойства являются сложными и имеют собственный редактор свойств.</span><span class="sxs-lookup"><span data-stu-id="e8d6c-117">However, some properties are more complex and have a custom property editor.</span></span> <span data-ttu-id="e8d6c-118">Чтобы установить свойство, щелкните текстовое поле и нажмите кнопку **(…)** для открытия специализированного редактора.</span><span class="sxs-lookup"><span data-stu-id="e8d6c-118">To set the property, click in the text box, and then click the build **(...)** button to open the custom editor.</span></span>  
  
6.  <span data-ttu-id="e8d6c-119">При желании можно создать выражения свойств для динамического обновления свойств задачи или контейнера.</span><span class="sxs-lookup"><span data-stu-id="e8d6c-119">Optionally, create property expressions to dynamically update the properties of the task or container.</span></span> <span data-ttu-id="e8d6c-120">Дополнительные сведения см. в разделе [Добавление или изменение выражение свойства](expressions/add-or-change-a-property-expression.md).</span><span class="sxs-lookup"><span data-stu-id="e8d6c-120">For more information, see [Add or Change a Property Expression](expressions/add-or-change-a-property-expression.md).</span></span>  
  
7.  <span data-ttu-id="e8d6c-121">Чтобы сохранить обновленный пакет, выберите пункт **Сохранить выбранные элементы** в меню **Файл** .</span><span class="sxs-lookup"><span data-stu-id="e8d6c-121">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
### <a name="to-set-the-properties-of-a-task-or-container-by-using-a-task-or-container-editor"></a><span data-ttu-id="e8d6c-122">Задание свойств задачи или контейнера с помощью редактора задачи или контейнера</span><span class="sxs-lookup"><span data-stu-id="e8d6c-122">To set the properties of a task or container by using a task or container editor</span></span>  
  
1.  <span data-ttu-id="e8d6c-123">В среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]откройте проект служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , содержащий необходимый пакет.</span><span class="sxs-lookup"><span data-stu-id="e8d6c-123">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="e8d6c-124">Чтобы открыть пакет, дважды щелкните его в обозревателе решений.</span><span class="sxs-lookup"><span data-stu-id="e8d6c-124">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="e8d6c-125">Перейдите на вкладку **Поток управления** .</span><span class="sxs-lookup"><span data-stu-id="e8d6c-125">Click the **Control Flow** tab.</span></span>  
  
4.  <span data-ttu-id="e8d6c-126">В области конструктора на вкладке **Поток управления** щелкните правой кнопкой мыши задачу или контейнер, затем выберите пункт **Изменить** , чтобы открыть соответствующий редактор задачи или контейнера.</span><span class="sxs-lookup"><span data-stu-id="e8d6c-126">On the design surface of the **Control Flow** tab, right-click the task or container, and then click **Edit** to open the corresponding task or container editor.</span></span>  
  
     <span data-ttu-id="e8d6c-127">Сведения о настройке контейнера "цикл по элементам" см. в разделе [Настройка контейнера "цикл по элементам"](control-flow/for-loop-container.md).</span><span class="sxs-lookup"><span data-stu-id="e8d6c-127">For information about how to configure the For Loop container, see [Configure a For Loop Container](control-flow/for-loop-container.md).</span></span>  
  
     <span data-ttu-id="e8d6c-128">Сведения о настройке контейнера "цикл по каждому элементу" см. в разделе [Настройка контейнера "цикл по каждому элементу"](control-flow/foreach-loop-container.md).</span><span class="sxs-lookup"><span data-stu-id="e8d6c-128">For information about how to configure the Foreach Loop container, see [Configure a Foreach Loop Container](control-flow/foreach-loop-container.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e8d6c-129">У контейнера последовательности нет настраиваемого редактора.</span><span class="sxs-lookup"><span data-stu-id="e8d6c-129">The Sequence container has no custom editor.</span></span>  
  
5.  <span data-ttu-id="e8d6c-130">Если в редакторе задачи или контейнера имеется несколько узлов, щелкните тот, который содержит нужное свойство.</span><span class="sxs-lookup"><span data-stu-id="e8d6c-130">If the task or container editor has multiple nodes, click the node that contains the property that you want to set.</span></span>  
  
6.  <span data-ttu-id="e8d6c-131">Либо щелкните пункт **Выражения** и создайте на странице **Выражения** выражения свойств, которые будут автоматически обновлять свойства задачи или контейнера.</span><span class="sxs-lookup"><span data-stu-id="e8d6c-131">Optionally, click **Expressions** and, on the **Expressions** page, create property expressions to dynamically update the properties of the task or container.</span></span> <span data-ttu-id="e8d6c-132">Дополнительные сведения см. в разделе [Добавление или изменение выражение свойства](expressions/add-or-change-a-property-expression.md).</span><span class="sxs-lookup"><span data-stu-id="e8d6c-132">For more information, see [Add or Change a Property Expression](expressions/add-or-change-a-property-expression.md).</span></span>  
  
7.  <span data-ttu-id="e8d6c-133">Обновите значение свойства.</span><span class="sxs-lookup"><span data-stu-id="e8d6c-133">Update the property value.</span></span>  
  
8.  <span data-ttu-id="e8d6c-134">Чтобы сохранить обновленный пакет, выберите пункт **Сохранить выбранные элементы** в меню **Файл** .</span><span class="sxs-lookup"><span data-stu-id="e8d6c-134">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8d6c-135">См. также:</span><span class="sxs-lookup"><span data-stu-id="e8d6c-135">See Also</span></span>  
 <span data-ttu-id="e8d6c-136">[Задачи служб Integration Services](control-flow/integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="e8d6c-136">[Integration Services Tasks](control-flow/integration-services-tasks.md) </span></span>  
 [<span data-ttu-id="e8d6c-137">Контейнеры служб Integration Services</span><span class="sxs-lookup"><span data-stu-id="e8d6c-137">Integration Services Containers</span></span>](control-flow/integration-services-containers.md)  
  
  
