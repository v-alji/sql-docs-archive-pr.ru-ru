---
title: Контейнер последовательности | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.sequencecontainer.f1
helpviewer_keywords:
- Sequence container
- grouping control flows
- containers [Integration Services], Sequence
- subset control flow [Integration Services]
ms.assetid: 7731f91e-b8b3-4d96-a0d9-73f568547cb3
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b972f923e2134363ba1b378beebebbeb1e5d6bb6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665470"
---
# <a name="sequence-container"></a><span data-ttu-id="28d97-102">контейнер последовательности</span><span class="sxs-lookup"><span data-stu-id="28d97-102">Sequence Container</span></span>
  <span data-ttu-id="28d97-103">Контейнер последовательности определяет поток управления, являющийся подмножеством потока управления пакета.</span><span class="sxs-lookup"><span data-stu-id="28d97-103">The Sequence container defines a control flow that is a subset of the package control flow.</span></span> <span data-ttu-id="28d97-104">Контейнер последовательности группирует пакет в несколько отдельных потоков управления, каждый из которых содержит одну или более задач и контейнеров, выполняющихся в общем потоке управления.</span><span class="sxs-lookup"><span data-stu-id="28d97-104">Sequence containers group the package into multiple separate control flows, each containing one or more tasks and containers that run within the overall package control flow.</span></span>  
  
 <span data-ttu-id="28d97-105">Помимо других контейнеров, контейнер последовательности может включать несколько задач.</span><span class="sxs-lookup"><span data-stu-id="28d97-105">The Sequence container can include multiple tasks in addition to other containers.</span></span> <span data-ttu-id="28d97-106">Добавление задач и контейнеров к контейнеру последовательности аналогично их добавлению к пакету, за исключением случаев, когда вместо контейнера пакетов задачи и контейнеры перетаскиваются в контейнер последовательности.</span><span class="sxs-lookup"><span data-stu-id="28d97-106">Adding tasks and containers to a Sequence container is similar to adding them to a package, except you drag the tasks and containers to the Sequence container instead of to the package container.</span></span> <span data-ttu-id="28d97-107">Если контейнер последовательности включает более одной задачи или контейнера, то их можно соединить с помощью управлений очередностью так же, как и в пакете.</span><span class="sxs-lookup"><span data-stu-id="28d97-107">If the Sequence container includes more than one task or container, you can connect them using precedence constraints just as you do in a package.</span></span> <span data-ttu-id="28d97-108">Дополнительные сведения см. в статье [Precedence Constraints](precedence-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="28d97-108">For more information, see [Precedence Constraints](precedence-constraints.md).</span></span>  
  
 <span data-ttu-id="28d97-109">Применение контейнера последовательности дает множество преимуществ:</span><span class="sxs-lookup"><span data-stu-id="28d97-109">There are many benefits of using a Sequence container:</span></span>  
  
-   <span data-ttu-id="28d97-110">Отключение групп задач, если нужно сосредоточить отладку пакета на одном подмножестве потока управления пакета;</span><span class="sxs-lookup"><span data-stu-id="28d97-110">Disabling groups of tasks to focus package debugging on one subset of the package control flow.</span></span>  
  
-   <span data-ttu-id="28d97-111">Управление свойствами нескольких задач одновременно путем определения этих свойств в контейнере последовательности, а не в каждой отдельной задаче.</span><span class="sxs-lookup"><span data-stu-id="28d97-111">Managing properties on multiple tasks in one location by setting properties on a Sequence container instead of on the individual tasks.</span></span>  
  
     <span data-ttu-id="28d97-112">Например, свойству `Disable` контейнера последовательности можно присвоить значение `True`, что позволит отключить все задачи и контейнеры в контейнере последовательности.</span><span class="sxs-lookup"><span data-stu-id="28d97-112">For example, you can set the `Disable` property of the Sequence container to `True` to disable all the tasks and containers in the Sequence container.</span></span>  
  
-   <span data-ttu-id="28d97-113">Создание области видимости для переменных, которыми может пользоваться группа связанных задач и контейнеров.</span><span class="sxs-lookup"><span data-stu-id="28d97-113">Providing scope for variables that a group of related tasks and containers use.</span></span>  
  
-   <span data-ttu-id="28d97-114">Следует группировать такое количество задач, чтобы ими можно было легче управлять, сворачивая и разворачивая контейнер последовательности.</span><span class="sxs-lookup"><span data-stu-id="28d97-114">Grouping many tasks so you can more easily managed them by collapsing and expanding the Sequence container.</span></span>  
  
     <span data-ttu-id="28d97-115">Помимо этого, с помощью окна **Группа** можно создать группы задач, способные разворачиваться и сворачиваться.</span><span class="sxs-lookup"><span data-stu-id="28d97-115">You can also create task groups, which expand and collapse using the **Group** box.</span></span> <span data-ttu-id="28d97-116">Окно **Группа** появляется только во время проектирования, во время выполнения у него нет свойств или поведения.</span><span class="sxs-lookup"><span data-stu-id="28d97-116">However, the **Group** box is a design-time feature that has no properties or run-time behavior.</span></span> <span data-ttu-id="28d97-117">Дополнительные сведения см. в разделе [Группирование или разгруппирование компонентов](../group-or-ungroup-components.md).</span><span class="sxs-lookup"><span data-stu-id="28d97-117">For more information, see [Group or Ungroup Components](../group-or-ungroup-components.md)</span></span>  
  
-   <span data-ttu-id="28d97-118">Задайте атрибут транзакции для контейнера последовательности, чтобы определить транзакцию для подмножества потока управления пакета.</span><span class="sxs-lookup"><span data-stu-id="28d97-118">Set a transaction attribute on the Sequence container to define a transaction for a subset of the package control flow.</span></span> <span data-ttu-id="28d97-119">Таким образом, возможно выполнение транзакции на более детальном уровне.</span><span class="sxs-lookup"><span data-stu-id="28d97-119">In this way, you can manage transactions at a more granular level.</span></span>  
  
     <span data-ttu-id="28d97-120">Например, если в контейнере последовательности находятся две связанные задачи: одна удаляет данные из таблицы, а вторая вставляет данные в таблицу, можно настроить транзакцию так, чтобы гарантировать, что удаление будет отменено, если произойдет ошибка во время операции вставки.</span><span class="sxs-lookup"><span data-stu-id="28d97-120">For example, if a Sequence container includes two related tasks, one task that deletes data in a table and another task that inserts data into a table, you can configure a transaction to ensure that the delete action is rolled back if the insert action fails.</span></span> <span data-ttu-id="28d97-121">Дополнительные сведения см. в разделе [Транзакции служб Integration Services](../integration-services-transactions.md).</span><span class="sxs-lookup"><span data-stu-id="28d97-121">For more information, see [Integration Services Transactions](../integration-services-transactions.md).</span></span>  
  
## <a name="configuration-of-the-sequence-container"></a><span data-ttu-id="28d97-122">Настройка контейнера последовательности</span><span class="sxs-lookup"><span data-stu-id="28d97-122">Configuration of the Sequence Container</span></span>  
 <span data-ttu-id="28d97-123">У контейнера последовательности нет отдельного интерфейса пользователя, его можно настроить только в окне **Свойства** среды [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] или программно.</span><span class="sxs-lookup"><span data-stu-id="28d97-123">The Sequence container has no custom user interface and you can configure it only in the **Properties** window of [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] or programmatically.</span></span>  
  
 <span data-ttu-id="28d97-124">Дополнительные сведения о задании этих свойств программными средствами см. в документации по классу **T:Microsoft.SqlServer.Dts.Runtime.Sequence** в руководстве для разработчиков.</span><span class="sxs-lookup"><span data-stu-id="28d97-124">For information about programmatically setting these properties, see documentation for the **T:Microsoft.SqlServer.Dts.Runtime.Sequence** class in the Developer Guide.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="28d97-125">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="28d97-125">Related Tasks</span></span>  
 <span data-ttu-id="28d97-126">Дополнительные сведения о настройке свойств этого компонента [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]см. в разделе [Задание свойств задач или контейнеров](../set-the-properties-of-a-task-or-container.md).</span><span class="sxs-lookup"><span data-stu-id="28d97-126">For information about how to set properties of the component in the [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], see [Set the Properties of a Task or Container](../set-the-properties-of-a-task-or-container.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28d97-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="28d97-127">See Also</span></span>  
 <span data-ttu-id="28d97-128">[Добавление задачи или контейнера в поток управления или удалить их из него](add-or-delete-a-task-or-a-container-in-a-control-flow.md) </span><span class="sxs-lookup"><span data-stu-id="28d97-128">[Add or Delete a Task or a Container in a Control Flow](add-or-delete-a-task-or-a-container-in-a-control-flow.md) </span></span>  
 <span data-ttu-id="28d97-129">[Соединение задач и контейнеров с помощью элементов управления очередностью по умолчанию](../connect-tasks-and-containers-by-using-a-default-precedence-constraint.md) </span><span class="sxs-lookup"><span data-stu-id="28d97-129">[Connect Tasks and Containers by Using a Default Precedence Constraint](../connect-tasks-and-containers-by-using-a-default-precedence-constraint.md) </span></span>  
 [<span data-ttu-id="28d97-130">Контейнеры служб Integration Services</span><span class="sxs-lookup"><span data-stu-id="28d97-130">Integration Services Containers</span></span>](integration-services-containers.md)  
  
  
