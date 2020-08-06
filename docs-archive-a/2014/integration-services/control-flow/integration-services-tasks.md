---
title: Задачи служб Integration Services | Документы Майкрософт
ms.custom: ''
ms.date: 08/22/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- scripts [Integration Services], tasks
- files [Integration Services], task options
- workflow tasks [Integration Services]
- Integration Services, tasks
- adding package tasks
- tasks [Integration Services], listed
- SSIS tasks
- SSIS, tasks
- control flow [Integration Services], tasks
- tasks [Integration Services]
- grouping tasks
- tasks [Integration Services], about tasks
- SQL Server Integration Services tasks
- data preparation tasks [Integration Services]
- directory operations [Integration Services]
ms.assetid: 75c8901d-6966-4af3-abe5-10af6dd9313b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5fa58dec1e05a0333c295efc7f00a1d6df935792
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658338"
---
# <a name="integration-services-tasks"></a><span data-ttu-id="4e45d-102">Задачи служб Integration Services</span><span class="sxs-lookup"><span data-stu-id="4e45d-102">Integration Services Tasks</span></span>
  <span data-ttu-id="4e45d-103">Задачами называются элементы потока управления, которые определяют рабочие модули, выполняющиеся в потоке управления пакета.</span><span class="sxs-lookup"><span data-stu-id="4e45d-103">Tasks are control flow elements that define units of work that are performed in a package control flow.</span></span> <span data-ttu-id="4e45d-104">Пакет служб [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] состоит из одной задачи или нескольких.</span><span class="sxs-lookup"><span data-stu-id="4e45d-104">An [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package is made up of one or more tasks.</span></span> <span data-ttu-id="4e45d-105">Если в пакете несколько задач, они связаны и упорядочены в потоке управления с помощью управления очередностью.</span><span class="sxs-lookup"><span data-stu-id="4e45d-105">If the package contains more than one task, they are connected and sequenced in the control flow by precedence constraints.</span></span>  
  
 <span data-ttu-id="4e45d-106">Можно также создавать пользовательские задачи на языке программирования, поддерживающем COM, например на Visual Basic, или на языке программирования для платформы .NET, например на C#.</span><span class="sxs-lookup"><span data-stu-id="4e45d-106">You can also write custom tasks using a programming language that supports COM, such as Visual Basic, or a .NET programming language, such as C#.</span></span>  
  
 <span data-ttu-id="4e45d-107">Конструктор служб [!INCLUDE[ssIS](../../includes/ssis-md.md)] — графическое средство служб [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] для работы с пакетами — предоставляет область конструктора для создания потока управления пакета и специальные редакторы для настройки задач.</span><span class="sxs-lookup"><span data-stu-id="4e45d-107">The [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, the graphical tool in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] for working with packages, provides the design surface for creating package control flow, and provides custom editors for configuring tasks.</span></span> <span data-ttu-id="4e45d-108">Можно также использовать объектную модель служб [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] для создания пакетов программными средствами.</span><span class="sxs-lookup"><span data-stu-id="4e45d-108">You can also program the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] object model to create packages programmatically.</span></span>  
  
## <a name="types-of-tasks"></a><span data-ttu-id="4e45d-109">Типы задач</span><span class="sxs-lookup"><span data-stu-id="4e45d-109">Types of Tasks</span></span>  
 [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] <span data-ttu-id="4e45d-110">содержатся следующие типы задач.</span><span class="sxs-lookup"><span data-stu-id="4e45d-110">includes the following types of tasks.</span></span>  
  
 <span data-ttu-id="4e45d-111">Задача потока данных</span><span class="sxs-lookup"><span data-stu-id="4e45d-111">Data Flow Task</span></span>  
 <span data-ttu-id="4e45d-112">Задача, создающая поток данных для извлечения данных, применения преобразований на уровне столбцов и загрузки данных.</span><span class="sxs-lookup"><span data-stu-id="4e45d-112">The task that runs data flows to extract data, apply column level transformations, and load data.</span></span>  
  
 <span data-ttu-id="4e45d-113">Задачи подготовки данных</span><span class="sxs-lookup"><span data-stu-id="4e45d-113">Data Preparation Tasks</span></span>  
 <span data-ttu-id="4e45d-114">Эти задачи включают в себя следующие процессы: копирование файлов и каталогов, загрузку файлов и данных, запуск веб-методов, добавление операций в XML-документы и профилирование данных для очистки.</span><span class="sxs-lookup"><span data-stu-id="4e45d-114">These tasks do the following processes: copy files and directories; download files and data; run Web methods; apply operations to XML documents; and profile data for cleansing.</span></span>  
  
 <span data-ttu-id="4e45d-115">Задачи рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="4e45d-115">Workflow Tasks</span></span>  
 <span data-ttu-id="4e45d-116">Задачи, связывающиеся с другими процессами для выполнения пакетов, программ или пакетных файлов, отправки и получения сообщений между пакетами, отправки сообщений электронной почты, считывания данных из инструментария управления Windows (WMI) и слежения за событиями WMI.</span><span class="sxs-lookup"><span data-stu-id="4e45d-116">The tasks that communicate with other processes to run packages, run programs or batch files, send and receive messages between packages, send e-mail messages, read Windows Management Instrumentation (WMI) data, and watch for WMI events.</span></span>  
  
 <span data-ttu-id="4e45d-117">Задачи SQL Server</span><span class="sxs-lookup"><span data-stu-id="4e45d-117">SQL Server Tasks</span></span>  
 <span data-ttu-id="4e45d-118">Задачи доступа к объектам и данным [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , их копирования, вставки, удаления и изменения.</span><span class="sxs-lookup"><span data-stu-id="4e45d-118">The tasks that access, copy, insert, delete, and modify [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] objects and data.</span></span>  
  
 <span data-ttu-id="4e45d-119">Задачи сценариев</span><span class="sxs-lookup"><span data-stu-id="4e45d-119">Scripting Tasks</span></span>  
 <span data-ttu-id="4e45d-120">Задачи, расширяющие функциональность пакетов с помощью скриптов.</span><span class="sxs-lookup"><span data-stu-id="4e45d-120">The tasks that extend package functionality by using scripts.</span></span>  
  
 <span data-ttu-id="4e45d-121">Задачи служб Analysis Services</span><span class="sxs-lookup"><span data-stu-id="4e45d-121">Analysis Services Tasks</span></span>  
 <span data-ttu-id="4e45d-122">Задачи, создающие, изменяющие, удаляющие и обрабатывающие объекты служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4e45d-122">The tasks that create, modify, delete, and process [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] objects.</span></span>  
  
 <span data-ttu-id="4e45d-123">Задачи обслуживания</span><span class="sxs-lookup"><span data-stu-id="4e45d-123">Maintenance Tasks</span></span>  
 <span data-ttu-id="4e45d-124">Задачи, выполняющие функции администрирования, например создание резервных копий и сжатие баз данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , перестроение и изменение структуры индексов, а также выполнение заданий агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4e45d-124">The tasks that perform administrative functions such as backing up and shrinking [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases, rebuilding and reorganizing indexes, and running [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs.</span></span>  
  
 <span data-ttu-id="4e45d-125">Пользовательские задачи</span><span class="sxs-lookup"><span data-stu-id="4e45d-125">Custom Tasks</span></span>  
 <span data-ttu-id="4e45d-126">Дополнительно можно создавать пользовательские задачи на языке программирования, поддерживающем COM, например Visual Basic, или на языке программирования для платформы .NET, например C#.</span><span class="sxs-lookup"><span data-stu-id="4e45d-126">Additionally, you can write custom tasks using a programming language that supports COM, such as Visual Basic, or a .NET programming language, such as C#.</span></span> <span data-ttu-id="4e45d-127">Чтобы получить доступ к пользовательской задаче в конструкторе служб [!INCLUDE[ssIS](../../includes/ssis-md.md)] , можно создать и зарегистрировать пользовательский интерфейс для задачи.</span><span class="sxs-lookup"><span data-stu-id="4e45d-127">If you want to access your custom task in the [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, you can create and register a user interface for the task.</span></span> <span data-ttu-id="4e45d-128">Дополнительные сведения см. в разделе [Разработка пользовательской задачи](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span><span class="sxs-lookup"><span data-stu-id="4e45d-128">For more information, see [Developing a Custom Task](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span></span>  
  
## <a name="configuration-of-tasks"></a><span data-ttu-id="4e45d-129">Настройка задач</span><span class="sxs-lookup"><span data-stu-id="4e45d-129">Configuration of Tasks</span></span>  
 <span data-ttu-id="4e45d-130">Пакет служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] может содержать одну задачу, например задачу «Выполнение SQL», удаляющую записи из таблицы базы данных при выполнении пакета.</span><span class="sxs-lookup"><span data-stu-id="4e45d-130">An [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package can contain a single task, such as an Execute SQL task that deletes records in a database table when the package runs.</span></span> <span data-ttu-id="4e45d-131">Однако обычно в пакетах находится несколько задач, и каждая из них настроена так, чтобы выполняться в контексте потока управления пакета.</span><span class="sxs-lookup"><span data-stu-id="4e45d-131">However, packages typically contain several tasks, and each task is set to run within the context of the package control flow.</span></span> <span data-ttu-id="4e45d-132">У обработчиков событий, которые являются рабочими процессами, запускающимися в ответ на события времени выполнения, также могут быть задачи.</span><span class="sxs-lookup"><span data-stu-id="4e45d-132">Event handlers, which are workflows that run in response to run-time events, can also have tasks.</span></span>  
  
 <span data-ttu-id="4e45d-133">Дополнительные сведения о добавлении задачи в пакет с помощью конструктора [!INCLUDE[ssIS](../../includes/ssis-md.md)] см. в разделе [Добавление задачи или контейнера в поток управления или удаление их из него](add-or-delete-a-task-or-a-container-in-a-control-flow.md).</span><span class="sxs-lookup"><span data-stu-id="4e45d-133">For more information about adding a task to a package using [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, see [Add or Delete a Task or a Container in a Control Flow](add-or-delete-a-task-or-a-container-in-a-control-flow.md).</span></span>  
  
 <span data-ttu-id="4e45d-134">Дополнительные сведения о программном добавлении задач в пакет см. в разделе [Программное добавление задач](../building-packages-programmatically/adding-tasks-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="4e45d-134">For more information about adding a task to a package programmatically, see [Adding Tasks Programmatically](../building-packages-programmatically/adding-tasks-programmatically.md).</span></span>  
  
 <span data-ttu-id="4e45d-135">Каждая задача может быть настроена отдельно с помощью собственных диалоговых окон, предоставляемых конструктором служб [!INCLUDE[ssIS](../../includes/ssis-md.md)] , или в окне «Свойства» среды [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4e45d-135">Each task can be configured individually using the custom dialog boxes for each task that [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer provides, or the Properties window included in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="4e45d-136">В пакете может храниться несколько задач одного типа (например, шесть задач "Выполнение SQL"), и каждая из них может быть настроена по-разному.</span><span class="sxs-lookup"><span data-stu-id="4e45d-136">A package can include multiple tasks of the same type-for example, six Execute SQL tasks-and each task can be configured differently.</span></span> <span data-ttu-id="4e45d-137">Дополнительные сведения см. в разделе [Задание свойств задач или контейнеров](../set-the-properties-of-a-task-or-container.md).</span><span class="sxs-lookup"><span data-stu-id="4e45d-137">For more information, see [Set the Properties of a Task or Container](../set-the-properties-of-a-task-or-container.md).</span></span>  
  
## <a name="tasks-connections-and-groups"></a><span data-ttu-id="4e45d-138">Подключения и группы задач</span><span class="sxs-lookup"><span data-stu-id="4e45d-138">Tasks Connections and Groups</span></span>  
 <span data-ttu-id="4e45d-139">Если задача содержит несколько задач, они связаны и упорядочены в потоке управления с помощью ограничений очередностью.</span><span class="sxs-lookup"><span data-stu-id="4e45d-139">If the task contains more than one task, they are connected and sequenced in the control flow by precedence constraints.</span></span> <span data-ttu-id="4e45d-140">Дополнительные сведения см. в статье [Precedence Constraints](precedence-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="4e45d-140">For more information, see [Precedence Constraints](precedence-constraints.md).</span></span>  
  
 <span data-ttu-id="4e45d-141">Задачи можно группировать и выполнять как одно целое либо повторять их выполнение в цикле.</span><span class="sxs-lookup"><span data-stu-id="4e45d-141">Tasks can be grouped together and performed as a single unit of work, or repeated in a loop.</span></span> <span data-ttu-id="4e45d-142">Дополнительные сведения см. в разделах [Foreach Loop Container](foreach-loop-container.md), [For Loop Container](for-loop-container.md)и [Sequence Container](sequence-container.md).</span><span class="sxs-lookup"><span data-stu-id="4e45d-142">For more information, see [Foreach Loop Container](foreach-loop-container.md), [For Loop Container](for-loop-container.md), and [Sequence Container](sequence-container.md).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="4e45d-143">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="4e45d-143">Related Tasks</span></span>  
 [<span data-ttu-id="4e45d-144">Добавление задачи или контейнера в поток управления или удаление их из него</span><span class="sxs-lookup"><span data-stu-id="4e45d-144">Add or Delete a Task or a Container in a Control Flow</span></span>](add-or-delete-a-task-or-a-container-in-a-control-flow.md)  
  
  
