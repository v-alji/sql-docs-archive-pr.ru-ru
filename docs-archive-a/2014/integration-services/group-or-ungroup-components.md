---
title: Группирование и разгруппирование компонентов | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- grouping containers
- tasks [Integration Services], grouping
- containers [Integration Services], grouping
- grouping tasks
ms.assetid: 34320838-c271-4f8c-90b3-1254690890bb
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f6811dffca41a12fe0afeeeb334e0107ac127c12
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655840"
---
# <a name="group-or-ungroup-components"></a><span data-ttu-id="a3341-102">Группирование и разгруппирование компонентов</span><span class="sxs-lookup"><span data-stu-id="a3341-102">Group or Ungroup Components</span></span>
  <span data-ttu-id="a3341-103">Вкладки **Поток управления**, **Поток данных**и **Обработчики событий** в конструкторе служб [!INCLUDE[ssIS](../includes/ssis-md.md)] поддерживают сворачиваемое группирование.</span><span class="sxs-lookup"><span data-stu-id="a3341-103">The **Control Flow**, **Data Flow**, and **Event Handlers** tabs in [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer supports collapsible grouping.</span></span> <span data-ttu-id="a3341-104">Если пакет содержит много компонентов, то вкладки могут оказаться перегруженными информацией и будет сложно сразу просматривать все компоненты и находить элемент, необходимый для работы.</span><span class="sxs-lookup"><span data-stu-id="a3341-104">If a package has many components, the tabs can become crowded, making it difficult to view all the components at one time and to locate the item with which you want to work.</span></span> <span data-ttu-id="a3341-105">Функция сворачиваемого группирования экономит рабочее пространство и упрощает работу с большими пакетами.</span><span class="sxs-lookup"><span data-stu-id="a3341-105">The collapsible grouping feature can conserve space on the work surface and make it easier to work with large packages.</span></span>  
  
 <span data-ttu-id="a3341-106">Нужно выбрать компоненты, сгруппировать их, а затем сворачивать или разворачивать группы по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="a3341-106">You select the components that you want to group, group them, and then expand or collapse the groups to suit your work.</span></span> <span data-ttu-id="a3341-107">Разворачивание группы предоставляет доступ к свойствам ее компонентов.</span><span class="sxs-lookup"><span data-stu-id="a3341-107">Expanding a group provides access to the properties of the components in the group.</span></span> <span data-ttu-id="a3341-108">Элементы управления очередностью, которые соединяют задачи и контейнеры, автоматически включаются в группу.</span><span class="sxs-lookup"><span data-stu-id="a3341-108">The precedence constraints that connect tasks and containers are automatically included in the group.</span></span>  
  
 <span data-ttu-id="a3341-109">Ниже приведены соображения по группированию компонентов.</span><span class="sxs-lookup"><span data-stu-id="a3341-109">The following are considerations for grouping components.</span></span>  
  
-   <span data-ttu-id="a3341-110">Группирование компонентов возможно, если поток управления, поток данных или обработчик событий содержат несколько компонентов.</span><span class="sxs-lookup"><span data-stu-id="a3341-110">To group components, the control flow, data flow, or event handler must contain more than one component.</span></span>  
  
-   <span data-ttu-id="a3341-111">Группы могут быть вложенными, что позволяет создавать группы внутри групп.</span><span class="sxs-lookup"><span data-stu-id="a3341-111">Groups can also be nested, making it possible to create groups within groups.</span></span> <span data-ttu-id="a3341-112">Область конструктора поддерживает несколько «невложенных» групп, но компонент может принадлежать только к одной группе, если группы не являются вложенными.</span><span class="sxs-lookup"><span data-stu-id="a3341-112">The design surface can implement multiple un-nested groups, but a component can belong to only one group, unless the groups are nested.</span></span>  
  
-   <span data-ttu-id="a3341-113">При сохранении пакета конструктор служб [!INCLUDE[ssIS](../includes/ssis-md.md)] сохраняет группирование, но оно не влияет на выполнение пакета.</span><span class="sxs-lookup"><span data-stu-id="a3341-113">When a package is saved, [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer saves the grouping, but the grouping has no effect on package execution.</span></span> <span data-ttu-id="a3341-114">Возможность группирования компонентов действует во время разработки и не влияет на работу пакета во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="a3341-114">The ability to group components is a design-time feature; it does not affect the run-time behavior of the package.</span></span>  
  
### <a name="to-group-components"></a><span data-ttu-id="a3341-115">Группирование компонентов</span><span class="sxs-lookup"><span data-stu-id="a3341-115">To group components</span></span>  
  
1.  <span data-ttu-id="a3341-116">В среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]откройте проект служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , содержащий необходимый пакет.</span><span class="sxs-lookup"><span data-stu-id="a3341-116">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="a3341-117">Чтобы открыть пакет, дважды щелкните его в обозревателе решений.</span><span class="sxs-lookup"><span data-stu-id="a3341-117">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="a3341-118">Перейдите на вкладку **Поток управления**, **Поток данных**или **Обработчики событий** .</span><span class="sxs-lookup"><span data-stu-id="a3341-118">Click the **Control Flow**, **Data Flow**, or **Event Handlers** tab.</span></span>  
  
4.  <span data-ttu-id="a3341-119">В области конструктора на вкладке выберите компоненты для группирования, щелкните их правой кнопкой мыши и выберите команду **Группировать**.</span><span class="sxs-lookup"><span data-stu-id="a3341-119">On the design surface of the tab, select the components you want to group, right-click a selected component, and then click **Group**.</span></span>  
  
5.  <span data-ttu-id="a3341-120">Чтобы сохранить обновленный пакет, выберите пункт **Сохранить выбранные элементы** в меню **Файл** .</span><span class="sxs-lookup"><span data-stu-id="a3341-120">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
### <a name="to-ungroup-components"></a><span data-ttu-id="a3341-121">Разгруппирование компонентов</span><span class="sxs-lookup"><span data-stu-id="a3341-121">To ungroup components</span></span>  
  
1.  <span data-ttu-id="a3341-122">В среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]откройте проект служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , содержащий необходимый пакет.</span><span class="sxs-lookup"><span data-stu-id="a3341-122">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="a3341-123">Чтобы открыть пакет, дважды щелкните его в обозревателе решений.</span><span class="sxs-lookup"><span data-stu-id="a3341-123">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="a3341-124">Перейдите на вкладку **Поток управления**, **Поток данных**или **Обработчики событий** .</span><span class="sxs-lookup"><span data-stu-id="a3341-124">Click the **Control Flow**, **Data Flow**, or **Event Handlers** tab.</span></span>  
  
4.  <span data-ttu-id="a3341-125">В области конструктора на вкладке выберите группу, содержащую компонент для разгруппирования, щелкните ее правой кнопкой мыши и выберите команду **Разгруппировать**.</span><span class="sxs-lookup"><span data-stu-id="a3341-125">On the design surface of the tab, select the group that contains the component you want to ungroup, right-click, and then click **Ungroup**.</span></span>  
  
5.  <span data-ttu-id="a3341-126">Чтобы сохранить обновленный пакет, выберите пункт **Сохранить выбранные элементы** в меню **Файл** .</span><span class="sxs-lookup"><span data-stu-id="a3341-126">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3341-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="a3341-127">See Also</span></span>  
 [<span data-ttu-id="a3341-128">Добавление задачи или контейнера в поток управления или удалить их из него</span><span class="sxs-lookup"><span data-stu-id="a3341-128">Add or Delete a Task or a Container in a Control Flow</span></span>](control-flow/add-or-delete-a-task-or-a-container-in-a-control-flow.md)  
     
 [<span data-ttu-id="a3341-129">Соединение задач и контейнеров с помощью элементов управления очередностью по умолчанию</span><span class="sxs-lookup"><span data-stu-id="a3341-129">Connect Tasks and Containers by Using a Default Precedence Constraint</span></span>](../../2014/integration-services/connect-tasks-and-containers-by-using-a-default-precedence-constraint.md)  
  
  
