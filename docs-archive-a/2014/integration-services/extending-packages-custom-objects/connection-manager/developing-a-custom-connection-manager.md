---
title: Разработка пользовательского диспетчера соединений | Документы Майкрософт
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- packages [Integration Services], connections
- custom connection managers [Integration Services], about custom connection managers
- connection managers [Integration Services], custom
- Integration Services packages, connection managers
- SSIS packages, connection managers
- SQL Server Integration Services packages, connection managers
- custom connection managers [Integration Services]
ms.assetid: bda0b29e-57f5-4879-b04d-1396dc56daa8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 19c5a9066db6542742537a41a7f567d1b4b1d23d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751303"
---
# <a name="developing-a-custom-connection-manager"></a><span data-ttu-id="bbbae-102">Разработка пользовательского диспетчера соединений</span><span class="sxs-lookup"><span data-stu-id="bbbae-102">Developing a Custom Connection Manager</span></span>
  <span data-ttu-id="bbbae-103">Службы [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] инкапсулируют сведения, необходимые для подключения к внешнему источнику данных, с помощью диспетчеров соединений.</span><span class="sxs-lookup"><span data-stu-id="bbbae-103">[!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] uses connection managers to encapsulate the information needed to connect to an external data source.</span></span> <span data-ttu-id="bbbae-104">В службах [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] имеются различные диспетчеры соединений, поддерживающие соединения с наиболее распространенными источниками данных, от корпоративных баз данных до текстовых файлов и книг Excel.</span><span class="sxs-lookup"><span data-stu-id="bbbae-104">[!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] includes a variety of connection managers that support connections to the most commonly used data sources, from enterprise databases to text files and Excel worksheets.</span></span> <span data-ttu-id="bbbae-105">Если набор диспетчеров соединений и внешних источников данных, поддерживаемых службами [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], не отвечает потребностям пользователя, можно создать пользовательский диспетчер соединений.</span><span class="sxs-lookup"><span data-stu-id="bbbae-105">If the connection managers and external data sources supported by [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] do not entirely meet your requirements, you can create a custom connection manager.</span></span>  
  
 <span data-ttu-id="bbbae-106">Для создания пользовательского диспетчера соединений необходимо создать класс, наследующий от базового класса <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase>, применить атрибут <xref:Microsoft.SqlServer.Dts.Runtime.DtsConnectionAttribute> к новому классу и переопределить важные методы и свойства базового класса, в том числе свойство <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.ConnectionString%2A> и метод <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.AcquireConnection%2A>.</span><span class="sxs-lookup"><span data-stu-id="bbbae-106">To create a custom connection manager, you have to create a class that inherits from the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase> base class, apply the <xref:Microsoft.SqlServer.Dts.Runtime.DtsConnectionAttribute> attribute to your new class, and override the important methods and properties of the base class, including the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.ConnectionString%2A> property and the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.AcquireConnection%2A> method.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="bbbae-107">Большая часть задач, источников и назначений в службах [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] работает только с определенными типами встроенных диспетчеров соединений.</span><span class="sxs-lookup"><span data-stu-id="bbbae-107">Most of the tasks, sources, and destinations that have been built into [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] work only with specific types of built-in connection managers.</span></span> <span data-ttu-id="bbbae-108">Прежде чем приступить к разработке пользовательского диспетчера соединений для использования со встроенными задачами и компонентами, необходимо выяснить, ограничивается ли список диспетчеров соединений, применимых для этих компонентов, каким-либо определенным типом.</span><span class="sxs-lookup"><span data-stu-id="bbbae-108">Before developing a custom connection manager for use with built-in tasks and components, check whether those components restrict the list of available connection managers to those of a specific type.</span></span> <span data-ttu-id="bbbae-109">Если для решения необходим пользовательский диспетчер соединений, также может понадобиться разработать пользовательскую задачу, источник или назначение для работы с пользовательским диспетчером.</span><span class="sxs-lookup"><span data-stu-id="bbbae-109">If your solution requires a custom connection manager, you might also have to develop a custom task, or a custom source or destination, for use with the connection manager.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bbbae-110">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="bbbae-110">In This Section</span></span>  
 <span data-ttu-id="bbbae-111">В этом разделе описывается, как создавать, настраивать и кодировать пользовательский диспетчер соединений и, при необходимости, его пользовательский интерфейс.</span><span class="sxs-lookup"><span data-stu-id="bbbae-111">This section describes how to create, configure, and code a custom connection manager and its optional custom user interface.</span></span> <span data-ttu-id="bbbae-112">Фрагменты кода, приведенные в этом разделе, являются производными от образца пользовательского диспетчера соединений SQL Server.</span><span class="sxs-lookup"><span data-stu-id="bbbae-112">The code snippets shown in this section are drawn from the Sql Server Custom Connection Manager Sample.</span></span>  
  
 [<span data-ttu-id="bbbae-113">Создание пользовательского диспетчера соединений</span><span class="sxs-lookup"><span data-stu-id="bbbae-113">Creating a Custom Connection Manager</span></span>](creating-a-custom-connection-manager.md)  
 <span data-ttu-id="bbbae-114">Описывает, как создать классы для проекта пользовательского диспетчера соединений.</span><span class="sxs-lookup"><span data-stu-id="bbbae-114">Describes how to create the classes for a custom connection manager project.</span></span>  
  
 [<span data-ttu-id="bbbae-115">Написание кода пользовательского диспетчера соединений</span><span class="sxs-lookup"><span data-stu-id="bbbae-115">Coding a Custom Connection Manager</span></span>](coding-a-custom-connection-manager.md)  
 <span data-ttu-id="bbbae-116">Описывает, как реализовать пользовательский диспетчер соединений путем переопределения методов и свойств базового класса.</span><span class="sxs-lookup"><span data-stu-id="bbbae-116">Describes how to implement a custom connection manager by overriding the methods and properties of the base class.</span></span>  
  
 [<span data-ttu-id="bbbae-117">Разработка пользовательского интерфейса для пользовательского диспетчера соединений</span><span class="sxs-lookup"><span data-stu-id="bbbae-117">Developing a User Interface for a Custom Connection Manager</span></span>](developing-a-user-interface-for-a-custom-connection-manager.md)  
 <span data-ttu-id="bbbae-118">Описывает, как реализовать класс пользовательского интерфейса и форму, используемую для настройки пользовательского диспетчера соединений.</span><span class="sxs-lookup"><span data-stu-id="bbbae-118">Describes how to implement the user interface class and the form that is used to configure the custom connection manager.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="bbbae-119">См. также</span><span class="sxs-lookup"><span data-stu-id="bbbae-119">Related Sections</span></span>  
  
### <a name="information-common-to-all-custom-objects"></a><span data-ttu-id="bbbae-120">Общие сведения для всех пользовательских объектов</span><span class="sxs-lookup"><span data-stu-id="bbbae-120">Information Common to all Custom Objects</span></span>  
 <span data-ttu-id="bbbae-121">Сведения, общие для всех типов пользовательских объектов, которые можно создавать в службах [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], см. в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="bbbae-121">For information that is common to all the type of custom objects that you can create in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], see the following topics:</span></span>  
  
 [<span data-ttu-id="bbbae-122">Разработка пользовательских объектов для служб Integration Services</span><span class="sxs-lookup"><span data-stu-id="bbbae-122">Developing Custom Objects for Integration Services</span></span>](../developing-custom-objects-for-integration-services.md)  
 <span data-ttu-id="bbbae-123">Описывает основные шаги по реализации всех типов пользовательских объектов для служб [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bbbae-123">Describes the basic steps in implementing all types of custom objects for [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="bbbae-124">Сохранение пользовательских объектов</span><span class="sxs-lookup"><span data-stu-id="bbbae-124">Persisting Custom Objects</span></span>](../persisting-custom-objects.md)  
 <span data-ttu-id="bbbae-125">Описывает пользовательский механизм сохраняемости, при необходимости приводя пояснения.</span><span class="sxs-lookup"><span data-stu-id="bbbae-125">Describes custom persistence and explains when it is necessary.</span></span>  
  
 [<span data-ttu-id="bbbae-126">Сборка, развертывание и отладка пользовательских объектов</span><span class="sxs-lookup"><span data-stu-id="bbbae-126">Building, Deploying, and Debugging Custom Objects</span></span>](../building-deploying-and-debugging-custom-objects.md)  
 <span data-ttu-id="bbbae-127">Описывает методы построения, подписывания, развертывания и отладки пользовательских объектов.</span><span class="sxs-lookup"><span data-stu-id="bbbae-127">Describes the techniques for building, signing, deploying, and debugging custom objects.</span></span>  
  
### <a name="information-about-other-custom-objects"></a><span data-ttu-id="bbbae-128">Сведения о других пользовательских объектах</span><span class="sxs-lookup"><span data-stu-id="bbbae-128">Information about Other Custom Objects</span></span>  
 <span data-ttu-id="bbbae-129">Сведения о других типах пользовательских объектов, которые можно создавать в службах [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], см. в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="bbbae-129">For information on the other types of custom objects that you can create in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], see the following topics:</span></span>  
  
 [<span data-ttu-id="bbbae-130">Разработка пользовательской задачи</span><span class="sxs-lookup"><span data-stu-id="bbbae-130">Developing a Custom Task</span></span>](../task/developing-a-custom-task.md)  
 <span data-ttu-id="bbbae-131">Описывает программирование пользовательских задач.</span><span class="sxs-lookup"><span data-stu-id="bbbae-131">Discusses how to program custom tasks.</span></span>  
  
 [<span data-ttu-id="bbbae-132">Разработка пользовательского регистратора</span><span class="sxs-lookup"><span data-stu-id="bbbae-132">Developing a Custom Log Provider</span></span>](../log-provider/developing-a-custom-log-provider.md)  
 <span data-ttu-id="bbbae-133">Описывает вопросы программирования пользовательских регистраторов.</span><span class="sxs-lookup"><span data-stu-id="bbbae-133">Discusses how to program custom log providers.</span></span>  
  
 [<span data-ttu-id="bbbae-134">Разработка пользовательского перечислителя по каждому элементу</span><span class="sxs-lookup"><span data-stu-id="bbbae-134">Developing a Custom ForEach Enumerator</span></span>](../foreach-enumerator/developing-a-custom-foreach-enumerator.md)  
 <span data-ttu-id="bbbae-135">Описывает вопросы программирования пользовательских перечислителей.</span><span class="sxs-lookup"><span data-stu-id="bbbae-135">Discusses how to program custom enumerators.</span></span>  
  
 [<span data-ttu-id="bbbae-136">Разработка пользовательского компонента потока данных</span><span class="sxs-lookup"><span data-stu-id="bbbae-136">Developing a Custom Data Flow Component</span></span>](../data-flow/developing-a-custom-data-flow-component.md)  
 <span data-ttu-id="bbbae-137">Описывает вопросы программирования пользовательских источников, преобразований и назначений потока данных.</span><span class="sxs-lookup"><span data-stu-id="bbbae-137">Discusses how to program custom data flow sources, transformations, and destinations.</span></span>  
  
<span data-ttu-id="bbbae-138">![Значок Integration Services (маленький)](../../media/dts-16.gif "Значок служб Integration Services (маленький)")  **следит за обновлениями Integration Services**</span><span class="sxs-lookup"><span data-stu-id="bbbae-138">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="bbbae-139">Чтобы загрузить новейшую документацию, статьи, образцы и видеоматериалы корпорации Майкрософт, а также лучшие решения участников сообщества, посетите страницу служб [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] на сайте MSDN:</span><span class="sxs-lookup"><span data-stu-id="bbbae-139">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="bbbae-140">Посетить страницу «Службы Integration Services» на сайте MSDN</span><span class="sxs-lookup"><span data-stu-id="bbbae-140">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="bbbae-141">Чтобы получать автоматические уведомления об этих обновлениях, подпишитесь на RSS-каналы, предлагаемые на этой странице.</span><span class="sxs-lookup"><span data-stu-id="bbbae-141">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
  
