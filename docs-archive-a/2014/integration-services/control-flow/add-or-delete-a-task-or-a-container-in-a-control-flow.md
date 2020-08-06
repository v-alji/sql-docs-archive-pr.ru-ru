---
title: Добавление задачи или контейнера в поток управления или удаление их из него | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- containers [Integration Services], adding
- adding tasks
- adding containers
- tasks [Integration Services], adding
ms.assetid: 653084c6-87a3-45d5-b458-914ecf24d56a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8338a4143358d732a974287e587f482dc5c36a22
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665077"
---
# <a name="add-or-delete-a-task-or-a-container-in-a-control-flow"></a><span data-ttu-id="019cf-102">Добавление задачи или контейнера в поток управления или удалить их из него</span><span class="sxs-lookup"><span data-stu-id="019cf-102">Add or Delete a Task or a Container in a Control Flow</span></span>
  <span data-ttu-id="019cf-103">При работе в конструкторе потока управления окно «Область элементов» конструктора служб [!INCLUDE[ssIS](../../includes/ssis-md.md)] содержит задачи, которые службы [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] предоставляют для построения потока управления в пакете.</span><span class="sxs-lookup"><span data-stu-id="019cf-103">When you are working in the control flow designer, the Toolbox in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer lists the tasks that [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] provides for building control flow in a package.</span></span> <span data-ttu-id="019cf-104">Дополнительные сведения об области элементов см. в разделе [SSIS Toolbox](../ssis-toolbox.md).</span><span class="sxs-lookup"><span data-stu-id="019cf-104">For more information about the Toolbox, see [SSIS Toolbox](../ssis-toolbox.md).</span></span>  
  
 <span data-ttu-id="019cf-105">Пакет может содержать несколько экземпляров одной задачи.</span><span class="sxs-lookup"><span data-stu-id="019cf-105">A package can include multiple instances of the same task.</span></span> <span data-ttu-id="019cf-106">Каждый экземпляр задачи в пакете уникально идентифицируется, следовательно, можно настроить каждый экземпляр независимо от других.</span><span class="sxs-lookup"><span data-stu-id="019cf-106">Each instance of a task is uniquely identified in the package, and you can configure each instance differently.</span></span>  
  
 <span data-ttu-id="019cf-107">При удалении задачи, элементы управления очередностью, которые соединяли задачу с другими задачами и контейнерами потока управления, также удаляются.</span><span class="sxs-lookup"><span data-stu-id="019cf-107">If you delete a task, the precedence constraints that connect the task to other tasks and containers in the control flow are also deleted.</span></span>  
  
 <span data-ttu-id="019cf-108">Следующие процедуры описывают способы добавления или удаления задачи или контейнера в потоке управления пакета.</span><span class="sxs-lookup"><span data-stu-id="019cf-108">The following procedures describe how to add or delete a task or container in the control flow of a package.</span></span>  
  
### <a name="to-add-a-task-or-a-container-to-a-control-flow"></a><span data-ttu-id="019cf-109">Добавление задачи или контейнера к потоку управления</span><span class="sxs-lookup"><span data-stu-id="019cf-109">To add a task or a container to a control flow</span></span>  
  
1.  <span data-ttu-id="019cf-110">В среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]откройте проект служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , содержащий необходимый пакет.</span><span class="sxs-lookup"><span data-stu-id="019cf-110">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="019cf-111">Чтобы открыть пакет, дважды щелкните его в обозревателе решений.</span><span class="sxs-lookup"><span data-stu-id="019cf-111">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="019cf-112">Перейдите на вкладку **Поток управления** .</span><span class="sxs-lookup"><span data-stu-id="019cf-112">Click the **Control Flow** tab.</span></span>  
  
4.  <span data-ttu-id="019cf-113">Чтобы открыть **Область элементов**, выберите пункт **Область элементов** в меню **Вид** .</span><span class="sxs-lookup"><span data-stu-id="019cf-113">To open the **Toolbox**, click **Toolbox** on the **View** menu.</span></span>  
  
5.  <span data-ttu-id="019cf-114">Раскройте **Элементы потока управления** и **Задачи обслуживания**.</span><span class="sxs-lookup"><span data-stu-id="019cf-114">Expand **Control Flow Items** and **Maintenance Tasks**.</span></span>  
  
6.  <span data-ttu-id="019cf-115">Перетащите задачи и контейнеры из **области элементов** в область конструктора на вкладке **Поток управления** .</span><span class="sxs-lookup"><span data-stu-id="019cf-115">Drag tasks and containers from the **Toolbox** to the design surface of the **Control Flow** tab.</span></span>  
  
7.  <span data-ttu-id="019cf-116">Подключите задачу или контейнер в рамках потока управления пакетами перетаскиванием его соединителя на другой компонент в потоке управления.</span><span class="sxs-lookup"><span data-stu-id="019cf-116">Connect a task or container within the package control flow by dragging its connector to another component in the control flow.</span></span>  
  
8.  <span data-ttu-id="019cf-117">Чтобы сохранить обновленный пакет, выберите пункт **Сохранить выбранные элементы** в меню **Файл** .</span><span class="sxs-lookup"><span data-stu-id="019cf-117">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
### <a name="to-delete-a-task-or-a-container-from-a-control-flow"></a><span data-ttu-id="019cf-118">Удаление задачи или контейнера из потока управления</span><span class="sxs-lookup"><span data-stu-id="019cf-118">To delete a task or a container from a control flow</span></span>  
  
1.  <span data-ttu-id="019cf-119">В среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]откройте проект служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , содержащий необходимый пакет.</span><span class="sxs-lookup"><span data-stu-id="019cf-119">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="019cf-120">Чтобы открыть пакет, дважды щелкните его в обозревателе решений.</span><span class="sxs-lookup"><span data-stu-id="019cf-120">In Solution Explorer, double-click the package to open it.</span></span> <span data-ttu-id="019cf-121">Выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="019cf-121">Do one of the following:</span></span>  
  
    -   <span data-ttu-id="019cf-122">Перейдите на вкладку **Поток управления** , щелкните правой кнопкой мыши задачу или пакет, которые необходимо удалить, и затем выберите пункт **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="019cf-122">Click the **Control Flow** tab, right-click the task or container that you want to remove, and then click **Delete**.</span></span>  
  
    -   <span data-ttu-id="019cf-123">Откройте **обозреватель пакетов**.</span><span class="sxs-lookup"><span data-stu-id="019cf-123">Open **Package Explorer**.</span></span> <span data-ttu-id="019cf-124">В папке **Исполняемые объекты** щелкните правой кнопкой мыши задачу или контейнер, которые необходимо удалить, затем выберите пункт **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="019cf-124">From the **Executables** folder, right-click the task or container that you want to remove, and then click **Delete**.</span></span>  
  
3.  <span data-ttu-id="019cf-125">Чтобы сохранить обновленный пакет, выберите пункт **Сохранить выбранные элементы** в меню **Файл** .</span><span class="sxs-lookup"><span data-stu-id="019cf-125">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="019cf-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="019cf-126">See Also</span></span>  
 <span data-ttu-id="019cf-127">[Задачи служб Integration Services](integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="019cf-127">[Integration Services Tasks](integration-services-tasks.md) </span></span>  
 <span data-ttu-id="019cf-128">[Контейнеры Integration Services](integration-services-containers.md) </span><span class="sxs-lookup"><span data-stu-id="019cf-128">[Integration Services Containers](integration-services-containers.md) </span></span>  
 [<span data-ttu-id="019cf-129">Поток управления</span><span class="sxs-lookup"><span data-stu-id="019cf-129">Control Flow</span></span>](control-flow.md)  
  
  
