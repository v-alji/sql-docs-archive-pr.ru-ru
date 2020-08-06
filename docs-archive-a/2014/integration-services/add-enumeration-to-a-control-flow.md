---
title: Добавить перечисление в поток управления | Документация Майкрософт
ms.custom: ''
ms.date: 08/22/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- adding enumerations
- Foreach Loop containers
- control flow [Integration Services], enumerations
- repeating workflows
- enumerations [Integration Services]
ms.assetid: f212b5fb-3cc4-422e-9b7c-89eb769a812a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 59b8569880fdf1a49f5f2ca1f6841841f9790af6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658961"
---
# <a name="add-enumeration-to-a-control-flow"></a><span data-ttu-id="60ec4-102">Добавление перечисления к потоку управления</span><span class="sxs-lookup"><span data-stu-id="60ec4-102">Add Enumeration to a Control Flow</span></span>
  [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]<span data-ttu-id="60ec4-103">включают в себя контейнер "Цикл по каждому элементу" — элемент потока управления, который позволяет легко использовать циклы, перечисляющие файлы и объекты в потоке управления пакета.</span><span class="sxs-lookup"><span data-stu-id="60ec4-103">includes the Foreach Loop container, a control flow element that makes it simple to include a looping construct that enumerates files and objects in the control flow of a package.</span></span> <span data-ttu-id="60ec4-104">Дополнительные сведения см. в разделе [Контейнер «цикл по каждому элементу»](control-flow/foreach-loop-container.md).</span><span class="sxs-lookup"><span data-stu-id="60ec4-104">For more information, see [Foreach Loop Container](control-flow/foreach-loop-container.md).</span></span>  
  
 <span data-ttu-id="60ec4-105">Контейнер «цикл по каждому элементу» не добавляет новых функций, он только предоставляет структуру, в которой можно построить повторяемый поток управления, указать тип перечислителя и задать его параметры.</span><span class="sxs-lookup"><span data-stu-id="60ec4-105">The Foreach Loop container provides no functionality; it provides only the structure in which you build the repeatable control flow, specify an enumerator type, and configure the enumerator.</span></span> <span data-ttu-id="60ec4-106">Чтобы контейнер заработал, необходимо включить в контейнер «цикл по каждому элементу» как минимум одну задачу.</span><span class="sxs-lookup"><span data-stu-id="60ec4-106">To provide container functionality, you must include at least one task in the Foreach Loop container.</span></span> <span data-ttu-id="60ec4-107">Дополнительные сведения см. в разделе [Integration Services Tasks](control-flow/integration-services-tasks.md).</span><span class="sxs-lookup"><span data-stu-id="60ec4-107">For more information, see [Integration Services Tasks](control-flow/integration-services-tasks.md).</span></span>  
  
 <span data-ttu-id="60ec4-108">Контейнер «цикл по каждому элементу» может включать поток управления из нескольких задач и может содержать другие контейнеры.</span><span class="sxs-lookup"><span data-stu-id="60ec4-108">The Foreach Loop container can include a control flow with multiple tasks and other containers.</span></span> <span data-ttu-id="60ec4-109">Добавление задач и контейнеров в контейнер «цикл по каждому элементу» сходно с добавлением их к пакету, только перетаскивание происходит в контейнер «цикл по каждому элементу», а не в пакет.</span><span class="sxs-lookup"><span data-stu-id="60ec4-109">Adding tasks and containers to a Foreach Loop container is similar to adding them to a package, except you drag the tasks and containers to the Foreach Loop container instead of to the package.</span></span> <span data-ttu-id="60ec4-110">Если контейнер «цикл по каждому элементу» содержит более одной задачи или контейнера, их можно соединить с использованием объектов управления очередностью, как и в пакете.</span><span class="sxs-lookup"><span data-stu-id="60ec4-110">If the Foreach Loop container includes more than one task or container, you can connect them using precedence constraints just as you do in a package.</span></span> <span data-ttu-id="60ec4-111">Дополнительные сведения см. в статье [Precedence Constraints](control-flow/precedence-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="60ec4-111">For more information, see [Precedence Constraints](control-flow/precedence-constraints.md).</span></span>  
  
### <a name="to-implement-a-foreach-loop-container-in-a-control-flow"></a><span data-ttu-id="60ec4-112">Включение контейнера «цикл по каждому элементу» в поток управления</span><span class="sxs-lookup"><span data-stu-id="60ec4-112">To implement a Foreach Loop container in a control flow</span></span>  
  
1.  <span data-ttu-id="60ec4-113">Добавьте к пакету контейнер «цикл по каждому элементу».</span><span class="sxs-lookup"><span data-stu-id="60ec4-113">Add the Foreach Loop container to the package.</span></span> <span data-ttu-id="60ec4-114">Дополнительные сведения см. [в разделе Добавление или удаление задачи или контейнера в потоке управления](control-flow/add-or-delete-a-task-or-a-container-in-a-control-flow.md) .</span><span class="sxs-lookup"><span data-stu-id="60ec4-114">For more information, see [Add or Delete a Task or a Container in a Control Flow](control-flow/add-or-delete-a-task-or-a-container-in-a-control-flow.md)</span></span>  
  <span data-ttu-id="60ec4-115">.</span><span class="sxs-lookup"><span data-stu-id="60ec4-115">.</span></span>  
  
2.  <span data-ttu-id="60ec4-116">Добавьте в контейнер «цикл по каждому элементу» задачи и контейнеры.</span><span class="sxs-lookup"><span data-stu-id="60ec4-116">Add tasks and containers to the Foreach Loop container.</span></span> <span data-ttu-id="60ec4-117">Дополнительные сведения см. [в разделе Добавление или удаление задачи или контейнера в потоке управления](control-flow/add-or-delete-a-task-or-a-container-in-a-control-flow.md) .</span><span class="sxs-lookup"><span data-stu-id="60ec4-117">For more information, see [Add or Delete a Task or a Container in a Control Flow](control-flow/add-or-delete-a-task-or-a-container-in-a-control-flow.md)</span></span>  
  <span data-ttu-id="60ec4-118">.</span><span class="sxs-lookup"><span data-stu-id="60ec4-118">.</span></span>  
  
3.  <span data-ttu-id="60ec4-119">Соедините задачи и контейнеры в контейнере «цикл по каждому элементу» с помощью объектов управления очередностью.</span><span class="sxs-lookup"><span data-stu-id="60ec4-119">Connect tasks and containers in the Foreach Loop container using precedence constraints.</span></span> <span data-ttu-id="60ec4-120">Дополнительные сведения см. в разделе [Соединение задач и контейнеров с помощью элементов управления очередностью по умолчанию](../../2014/integration-services/connect-tasks-and-containers-by-using-a-default-precedence-constraint.md).</span><span class="sxs-lookup"><span data-stu-id="60ec4-120">For more information, see [Connect Tasks and Containers by Using a Default Precedence Constraint](../../2014/integration-services/connect-tasks-and-containers-by-using-a-default-precedence-constraint.md).</span></span>  
  
4.  <span data-ttu-id="60ec4-121">Задайте параметры контейнера «цикл по каждому элементу».</span><span class="sxs-lookup"><span data-stu-id="60ec4-121">Configure the Foreach Loop container.</span></span> <span data-ttu-id="60ec4-122">Дополнительные сведения см. в разделе [Настройка контейнера «цикл по каждому элементу»](../../2014/integration-services/configure-a-foreach-loop-container.md).</span><span class="sxs-lookup"><span data-stu-id="60ec4-122">For more information, see [Configure a Foreach Loop Container](../../2014/integration-services/configure-a-foreach-loop-container.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60ec4-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="60ec4-123">See Also</span></span>  
 <span data-ttu-id="60ec4-124">[Добавление или удаление задачи или контейнера в потоке управления](control-flow/add-or-delete-a-task-or-a-container-in-a-control-flow.md) </span><span class="sxs-lookup"><span data-stu-id="60ec4-124">[Add or Delete a Task or a Container in a Control Flow](control-flow/add-or-delete-a-task-or-a-container-in-a-control-flow.md) </span></span>  
 <span data-ttu-id="60ec4-125">[Группирование или разгруппирование компонентов](group-or-ungroup-components.md) </span><span class="sxs-lookup"><span data-stu-id="60ec4-125">[Group or Ungroup Components](group-or-ungroup-components.md) </span></span>  
 <span data-ttu-id="60ec4-126">[Управление очередностью](control-flow/precedence-constraints.md) </span><span class="sxs-lookup"><span data-stu-id="60ec4-126">[Precedence Constraints](control-flow/precedence-constraints.md) </span></span>  
 <span data-ttu-id="60ec4-127">[Добавление итерации в поток управления](add-iteration-to-a-control-flow.md) </span><span class="sxs-lookup"><span data-stu-id="60ec4-127">[Add Iteration to a Control Flow](add-iteration-to-a-control-flow.md) </span></span>  
 [<span data-ttu-id="60ec4-128">Поток управления</span><span class="sxs-lookup"><span data-stu-id="60ec4-128">Control Flow</span></span>](control-flow/control-flow.md)  
  
  
