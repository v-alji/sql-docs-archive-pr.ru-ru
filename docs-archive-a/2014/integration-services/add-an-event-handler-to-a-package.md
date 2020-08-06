---
title: Добавление обработчика событий в пакет | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- event handlers [Integration Services], creating
ms.assetid: 5e56885d-8658-480a-bed9-3f2f8003fd78
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 007d81a395e06ac5a97210cd3e3ed6eea91aee57
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658973"
---
# <a name="add-an-event-handler-to-a-package"></a><span data-ttu-id="8e888-102">Добавление к пакету обработчик событий</span><span class="sxs-lookup"><span data-stu-id="8e888-102">Add an Event Handler to a Package</span></span>
  <span data-ttu-id="8e888-103">При выполнении контейнеров и задач происходят разные события.</span><span class="sxs-lookup"><span data-stu-id="8e888-103">At run time, containers and tasks raise events.</span></span> <span data-ttu-id="8e888-104">Возможно создание обработчиков пользовательских событий, которые отвечают на возникающие события запуском рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="8e888-104">You can create custom event handlers that respond to these events by running a workflow when the event is raised.</span></span> <span data-ttu-id="8e888-105">Например, можно создать обработчик событий, который по электронной почте посылает сообщение, если задача завершается неудачей.</span><span class="sxs-lookup"><span data-stu-id="8e888-105">For example, you can create an event handler that sends an e-mail message when a task fails.</span></span>  
  
 <span data-ttu-id="8e888-106">Обработчик событий аналогичен пакету.</span><span class="sxs-lookup"><span data-stu-id="8e888-106">An event handler is similar to a package.</span></span> <span data-ttu-id="8e888-107">Как и пакет, обработчик событий обеспечивает область действия для переменных и включает поток управления и потоки данных по выбору.</span><span class="sxs-lookup"><span data-stu-id="8e888-107">Like a package, an event handler can provide scope for variables, and includes a control flow and optional data flows.</span></span> <span data-ttu-id="8e888-108">Можно построить обработчик событий для пакетов, контейнера «цикл по каждому элементу», контейнера «цикл по элементам», контейнера последовательности и всех задач.</span><span class="sxs-lookup"><span data-stu-id="8e888-108">You can build event handlers for packages, the Foreach Loop container, the For Loop container, the Sequence container, and all tasks.</span></span>  
  
 <span data-ttu-id="8e888-109">Создайте обработчик событий, используя область конструктора вкладки **Обработчики событий** в конструкторе служб [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8e888-109">You create event handlers by using the design surface of the **Event Handlers** tab in [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="8e888-110">Если вкладка **Обработчики событий** активна, узлы **Элементы потока управления** и **Задачи плана обслуживания** в области элементов конструктора служб [!INCLUDE[ssIS](../includes/ssis-md.md)] содержат задачу и контейнеры для построения потока управления в обработчике событий.</span><span class="sxs-lookup"><span data-stu-id="8e888-110">When the **Event Handlers** tab is active, the **Control Flow Items** and **Maintenance Plan Tasks** nodes of the Toolbox in [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer contain the task and containers for building the control flow in the event handler.</span></span> <span data-ttu-id="8e888-111">Узлы **Источники потока данных**, **Преобразования**и **Назначения потока данных** содержат источники данных, преобразования и назначения для построения потоков данных в обработчике событий.</span><span class="sxs-lookup"><span data-stu-id="8e888-111">The **Data Flow Sources**, **Transformations**, **and Data Flow Destinations** nodes contain the data sources, transformations, and destinations for building the data flows in the event handler.</span></span> <span data-ttu-id="8e888-112">Дополнительные сведения см. в разделах [Поток управления](control-flow/control-flow.md) и [Поток данных](data-flow/data-flow.md).</span><span class="sxs-lookup"><span data-stu-id="8e888-112">For more information, see [Control Flow](control-flow/control-flow.md) and [Data Flow](data-flow/data-flow.md).</span></span>  
  
 <span data-ttu-id="8e888-113">Вкладка **Обработчики событий** также включает зону диспетчеров **Соединения** , в которой можно создавать и изменять диспетчеры соединений, используемых обработчиками событий для соединения с серверами и источниками данных.</span><span class="sxs-lookup"><span data-stu-id="8e888-113">The **Event Handlers** tab also includes the **Connections** Managers area where you can create and modify the connection managers that event handlers use to connect to servers and data sources.</span></span> <span data-ttu-id="8e888-114">Дополнительные сведения см. в разделе [Создание диспетчеров соединений](../../2014/integration-services/create-connection-managers.md).</span><span class="sxs-lookup"><span data-stu-id="8e888-114">For more information, see [Create Connection Managers](../../2014/integration-services/create-connection-managers.md).</span></span>  
  
### <a name="to-create-an-event-handler"></a><span data-ttu-id="8e888-115">Создание обработчика событий</span><span class="sxs-lookup"><span data-stu-id="8e888-115">To create an event handler</span></span>  
  
1.  <span data-ttu-id="8e888-116">В среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]откройте проект служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , содержащий необходимый пакет.</span><span class="sxs-lookup"><span data-stu-id="8e888-116">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="8e888-117">Чтобы открыть пакет, дважды щелкните его в обозревателе решений.</span><span class="sxs-lookup"><span data-stu-id="8e888-117">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="8e888-118">Перейдите на вкладку **Обработчики событий** .</span><span class="sxs-lookup"><span data-stu-id="8e888-118">Click the **Event Handlers** tab.</span></span>  
  
     <span data-ttu-id="8e888-119">![Снимок экрана: область конструктора с обработчиком событий](media/eventhandlers.gif "Снимок экрана: область конструктора с обработчиком событий")</span><span class="sxs-lookup"><span data-stu-id="8e888-119">![Screenshot of design surface with event handler](media/eventhandlers.gif "Screenshot of design surface with event handler")</span></span>  
  
     <span data-ttu-id="8e888-120">Создание потока управления и потоков данных в обработчике событий аналогично созданию потока управления и потока данных в пакете.</span><span class="sxs-lookup"><span data-stu-id="8e888-120">Creating the control flow and data flows in an event handler is similar to creating the control flow and data flows in a package.</span></span> <span data-ttu-id="8e888-121">Дополнительные сведения см. в разделах [Поток управления](control-flow/control-flow.md) и [Поток данных](data-flow/data-flow.md).</span><span class="sxs-lookup"><span data-stu-id="8e888-121">For more information, see [Control Flow](control-flow/control-flow.md) and [Data Flow](data-flow/data-flow.md).</span></span>  
  
4.  <span data-ttu-id="8e888-122">В списке **Исполняемый объект** выберите исполняемый объект, для которого создается обработчик события.</span><span class="sxs-lookup"><span data-stu-id="8e888-122">In the **Executable** list, select the executable for which you want to create an event handler.</span></span>  
  
5.  <span data-ttu-id="8e888-123">В списке **Обработчик событий** выберите обработчик событий, который необходимо построить.</span><span class="sxs-lookup"><span data-stu-id="8e888-123">In the **Event handler** list, select the event handler you want to build.</span></span>  
  
6.  <span data-ttu-id="8e888-124">Щелкните ссылку в области конструктора на вкладке **Обработчик событий** .</span><span class="sxs-lookup"><span data-stu-id="8e888-124">Click the link on the design surface of the **Event Handler** tab.</span></span>  
  
7.  <span data-ttu-id="8e888-125">Добавьте элементы потока управления к обработчику событий и подключите элементы, используя управление очередностью (перетаскивая ограничение из одного элемента потока управления в другой).</span><span class="sxs-lookup"><span data-stu-id="8e888-125">Add control flow items to the event handler, and connect items using a precedence constraint by dragging the constraint from one control flow item to another.</span></span> <span data-ttu-id="8e888-126">Дополнительные сведения см. в разделе [Поток управления](control-flow/control-flow.md).</span><span class="sxs-lookup"><span data-stu-id="8e888-126">For more information, see [Control Flow](control-flow/control-flow.md).</span></span>  
  
8.  <span data-ttu-id="8e888-127">Дополнительно можно добавить задачу потока данных и в области конструктора на вкладке **Поток данных** создать поток данных для обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="8e888-127">Optionally, add a Data Flow task, and on the design surface of the **Data Flow** tab, create a data flow for the event handler.</span></span> <span data-ttu-id="8e888-128">Дополнительные сведения см. в статье [Поток данных](data-flow/data-flow.md).</span><span class="sxs-lookup"><span data-stu-id="8e888-128">For more information, see [Data Flow](data-flow/data-flow.md).</span></span>  
  
9. <span data-ttu-id="8e888-129">Чтобы сохранить пакет, в меню **Файл** выберите пункт **Сохранить выбранные элементы** .</span><span class="sxs-lookup"><span data-stu-id="8e888-129">On the **File** menu, click **Save Selected Items** to save the package.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e888-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="8e888-130">See Also</span></span>  
 <span data-ttu-id="8e888-131">[SQL Server Integration Services](../../2014/integration-services/sql-server-integration-services.md) </span><span class="sxs-lookup"><span data-stu-id="8e888-131">[SQL Server Integration Services](../../2014/integration-services/sql-server-integration-services.md) </span></span>  
 [<span data-ttu-id="8e888-132">Ведение журналов в службах Integration Services (SSIS)</span><span class="sxs-lookup"><span data-stu-id="8e888-132">Integration Services &#40;SSIS&#41; Logging</span></span>](performance/integration-services-ssis-logging.md)  
  
  
