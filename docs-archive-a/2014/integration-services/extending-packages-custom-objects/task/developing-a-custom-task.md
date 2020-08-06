---
title: Разработка пользовательской задачи | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- custom tasks [Integration Services], about custom tasks
- Task class
- custom tasks [Integration Services]
- SSIS custom tasks
- SSIS custom tasks, about custom tasks
- IDtsTaskUI interface
- DtsTaskAttribute attribute
- tasks [Integration Services], custom
- TaskHost object
ms.assetid: dcbd8615-fa6d-4ddb-b8a5-0b19dddd6239
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d9d3446acff7ced73ab47014bec51708dba225b6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666176"
---
# <a name="developing-a-custom-task"></a><span data-ttu-id="cafee-102">Разработка пользовательской задачи</span><span class="sxs-lookup"><span data-stu-id="cafee-102">Developing a Custom Task</span></span>
  <span data-ttu-id="cafee-103">Для выполнения элементов работы, направленных на обеспечение извлечения, преобразования и загрузки данных службы [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] используют задачи.</span><span class="sxs-lookup"><span data-stu-id="cafee-103">[!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] uses tasks to perform units of work in support of the extraction, transformation, and loading of data.</span></span> <span data-ttu-id="cafee-104">В службах [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] имеются различные задачи, выполняющие наиболее часто используемые действия, от извлечения инструкции SQL до загрузки файла с FTP-сайта.</span><span class="sxs-lookup"><span data-stu-id="cafee-104">[!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] includes a variety of tasks that perform the most frequently used actions, from executing an SQL statement to downloading a file from an FTP site.</span></span> <span data-ttu-id="cafee-105">Если имеющиеся задачи и поддерживаемые действия не удовлетворяют потребностям пользователя, можно создать пользовательскую задачу.</span><span class="sxs-lookup"><span data-stu-id="cafee-105">If the included tasks and supported actions do not completely meet your requirements, you can create a custom task.</span></span>  
  
 <span data-ttu-id="cafee-106">Для создания пользовательской задачи необходимо создать класс, наследующий от базового класса [Microsoft.SqlServer.Dts.Runtime.Task](/dotnet/api/microsoft.sqlserver.dts.runtime.task), применить атрибут <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute> к новому классу и переопределить важные методы и свойства базового класса, в том числе метод <xref:Microsoft.SqlServer.Dts.Runtime.Task.Execute%2A>.</span><span class="sxs-lookup"><span data-stu-id="cafee-106">To create a custom task, you have to create a class that inherits from the [Microsoft.SqlServer.Dts.Runtime.Task](/dotnet/api/microsoft.sqlserver.dts.runtime.task) base class, apply the <xref:Microsoft.SqlServer.Dts.Runtime.DtsTaskAttribute> attribute to your new class, and override the important methods and properties of the base class, including the <xref:Microsoft.SqlServer.Dts.Runtime.Task.Execute%2A> method.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cafee-107">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="cafee-107">In This Section</span></span>  
 <span data-ttu-id="cafee-108">В этом разделе описывается, как создавать, настраивать и кодировать пользовательскую задачу и, при необходимости, пользовательский интерфейс.</span><span class="sxs-lookup"><span data-stu-id="cafee-108">This section describes how to create, configure, and code a custom task and its optional custom user interface.</span></span>  
  
 [<span data-ttu-id="cafee-109">Создание пользовательской задачи</span><span class="sxs-lookup"><span data-stu-id="cafee-109">Creating a Custom Task</span></span>](creating-a-custom-task.md)  
 <span data-ttu-id="cafee-110">Описывает первый шаг, состоящий в создании пользовательской задачи.</span><span class="sxs-lookup"><span data-stu-id="cafee-110">Describes the first step, which is creating the custom task.</span></span>  
  
 [<span data-ttu-id="cafee-111">Создание кода пользовательской задачи</span><span class="sxs-lookup"><span data-stu-id="cafee-111">Coding a Custom Task</span></span>](coding-a-custom-task.md)  
 <span data-ttu-id="cafee-112">Описывает, как кодировать основные методы пользовательской задачи.</span><span class="sxs-lookup"><span data-stu-id="cafee-112">Describes how to code the principal methods of a custom task.</span></span>  
  
 [<span data-ttu-id="cafee-113">Соединение с источниками данных в пользовательской задаче</span><span class="sxs-lookup"><span data-stu-id="cafee-113">Connecting to Data Sources in a Custom Task</span></span>](connecting-to-data-sources-in-a-custom-task.md)  
 <span data-ttu-id="cafee-114">Описывает, как соединить пользовательскую задачу с источником данных.</span><span class="sxs-lookup"><span data-stu-id="cafee-114">Describes how to connect a custom task to a data source.</span></span>  
  
 [<span data-ttu-id="cafee-115">Вызов и определение событий в пользовательской задаче</span><span class="sxs-lookup"><span data-stu-id="cafee-115">Raising and Defining Events in a Custom Task</span></span>](raising-and-defining-events-in-a-custom-task.md)  
 <span data-ttu-id="cafee-116">Описывает, как обеспечить вызов событий и определить пользовательские события для пользовательской задачи.</span><span class="sxs-lookup"><span data-stu-id="cafee-116">Describes how to raise events and define custom events from the custom task.</span></span>  
  
 [<span data-ttu-id="cafee-117">Добавление поддержки отладки в пользовательскую задачу</span><span class="sxs-lookup"><span data-stu-id="cafee-117">Adding Support for Debugging in a Custom Task</span></span>](adding-support-for-debugging-in-a-custom-task.md)  
 <span data-ttu-id="cafee-118">Описывает, как создать целевые объекты точек останова в пользовательской задаче.</span><span class="sxs-lookup"><span data-stu-id="cafee-118">Describes how to create breakpoint targets in the custom task.</span></span>  
  
 [<span data-ttu-id="cafee-119">Разработка пользовательского интерфейса для пользовательской задачи</span><span class="sxs-lookup"><span data-stu-id="cafee-119">Developing a User Interface for a Custom Task</span></span>](developing-a-user-interface-for-a-custom-task.md)  
 <span data-ttu-id="cafee-120">Описывает, как создать пользовательский интерфейс, отображаемый в конструкторе служб [!INCLUDE[ssIS](../../../includes/ssis-md.md)] для настройки свойств пользовательской задачи.</span><span class="sxs-lookup"><span data-stu-id="cafee-120">Describes how to create a user interface that shows in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer to configure properties on the custom task.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="cafee-121">См. также</span><span class="sxs-lookup"><span data-stu-id="cafee-121">Related Sections</span></span>  
  
### <a name="information-common-to-all-custom-objects"></a><span data-ttu-id="cafee-122">Общие сведения для всех пользовательских объектов</span><span class="sxs-lookup"><span data-stu-id="cafee-122">Information Common to all Custom Objects</span></span>  
 <span data-ttu-id="cafee-123">Сведения, общие для всех типов пользовательских объектов, которые можно создавать в службах [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], см. в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="cafee-123">For information that is common to all the type of custom objects that you can create in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], see the following topics:</span></span>  
  
 [<span data-ttu-id="cafee-124">Разработка пользовательских объектов для служб Integration Services</span><span class="sxs-lookup"><span data-stu-id="cafee-124">Developing Custom Objects for Integration Services</span></span>](../developing-custom-objects-for-integration-services.md)  
 <span data-ttu-id="cafee-125">Описывает основные шаги реализации всех типов пользовательских объектов для служб [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cafee-125">Describes the basic steps in implementing all kinds of custom objects for [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="cafee-126">Сохранение пользовательских объектов</span><span class="sxs-lookup"><span data-stu-id="cafee-126">Persisting Custom Objects</span></span>](../persisting-custom-objects.md)  
 <span data-ttu-id="cafee-127">Описывает пользовательский механизм сохраняемости, при необходимости приводя пояснения.</span><span class="sxs-lookup"><span data-stu-id="cafee-127">Describes custom persistence and explains when it is necessary.</span></span>  
  
 [<span data-ttu-id="cafee-128">Сборка, развертывание и отладка пользовательских объектов</span><span class="sxs-lookup"><span data-stu-id="cafee-128">Building, Deploying, and Debugging Custom Objects</span></span>](../building-deploying-and-debugging-custom-objects.md)  
 <span data-ttu-id="cafee-129">Описывает методы построения, подписывания, развертывания и отладки пользовательских объектов.</span><span class="sxs-lookup"><span data-stu-id="cafee-129">Describes the techniques for building, signing, deploying, and debugging custom objects.</span></span>  
  
### <a name="information-about-other-custom-objects"></a><span data-ttu-id="cafee-130">Сведения о других пользовательских объектах</span><span class="sxs-lookup"><span data-stu-id="cafee-130">Information about Other Custom Objects</span></span>  
 <span data-ttu-id="cafee-131">Сведения о других типах пользовательских объектов, которые можно создавать в службах [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], см. в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="cafee-131">For information about the other types of custom objects that you can create in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], see the following topics:</span></span>  
  
 [<span data-ttu-id="cafee-132">Разработка пользовательского диспетчера соединений</span><span class="sxs-lookup"><span data-stu-id="cafee-132">Developing a Custom Connection Manager</span></span>](../connection-manager/developing-a-custom-connection-manager.md)  
 <span data-ttu-id="cafee-133">Описывает вопросы программирования пользовательских диспетчеров соединений.</span><span class="sxs-lookup"><span data-stu-id="cafee-133">Discusses how to program custom connection managers.</span></span>  
  
 [<span data-ttu-id="cafee-134">Разработка пользовательского регистратора</span><span class="sxs-lookup"><span data-stu-id="cafee-134">Developing a Custom Log Provider</span></span>](../log-provider/developing-a-custom-log-provider.md)  
 <span data-ttu-id="cafee-135">Описывает вопросы программирования пользовательских регистраторов.</span><span class="sxs-lookup"><span data-stu-id="cafee-135">Discusses how to program custom log providers.</span></span>  
  
 [<span data-ttu-id="cafee-136">Разработка пользовательского перечислителя по каждому элементу</span><span class="sxs-lookup"><span data-stu-id="cafee-136">Developing a Custom ForEach Enumerator</span></span>](../foreach-enumerator/developing-a-custom-foreach-enumerator.md)  
 <span data-ttu-id="cafee-137">Описывает вопросы программирования пользовательских перечислителей.</span><span class="sxs-lookup"><span data-stu-id="cafee-137">Discusses how to program custom enumerators.</span></span>  
  
 [<span data-ttu-id="cafee-138">Разработка пользовательского компонента потока данных</span><span class="sxs-lookup"><span data-stu-id="cafee-138">Developing a Custom Data Flow Component</span></span>](../data-flow/developing-a-custom-data-flow-component.md)  
 <span data-ttu-id="cafee-139">Описывает вопросы программирования пользовательских источников, преобразований и назначений потока данных.</span><span class="sxs-lookup"><span data-stu-id="cafee-139">Discusses how to program custom data flow sources, transformations, and destinations.</span></span>  
  
<span data-ttu-id="cafee-140">![Значок Integration Services (маленький)](../../media/dts-16.gif "Значок служб Integration Services (маленький)")  **следит за обновлениями Integration Services**</span><span class="sxs-lookup"><span data-stu-id="cafee-140">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="cafee-141">Чтобы загрузить новейшую документацию, статьи, образцы и видеоматериалы корпорации Майкрософт, а также лучшие решения участников сообщества, посетите страницу служб [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] на сайте MSDN:</span><span class="sxs-lookup"><span data-stu-id="cafee-141">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="cafee-142">Посетить страницу «Службы Integration Services» на сайте MSDN</span><span class="sxs-lookup"><span data-stu-id="cafee-142">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="cafee-143">Чтобы получать автоматические уведомления об этих обновлениях, подпишитесь на RSS-каналы, предлагаемые на этой странице.</span><span class="sxs-lookup"><span data-stu-id="cafee-143">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cafee-144">См. также:</span><span class="sxs-lookup"><span data-stu-id="cafee-144">See Also</span></span>  
 <span data-ttu-id="cafee-145">[Расширение пакета с помощью задачи "Скрипт"](../../extending-packages-scripting/task/extending-the-package-with-the-script-task.md) </span><span class="sxs-lookup"><span data-stu-id="cafee-145">[Extending the Package with the Script Task](../../extending-packages-scripting/task/extending-the-package-with-the-script-task.md) </span></span>  
 [<span data-ttu-id="cafee-146">Сравнение решений со сценариями и пользовательских объектов</span><span class="sxs-lookup"><span data-stu-id="cafee-146">Comparing Scripting Solutions and Custom Objects</span></span>](../../extending-packages-scripting/comparing-scripting-solutions-and-custom-objects.md)  
  
  
