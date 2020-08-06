---
title: Разработка пользовательского регистратора | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- SSIS packages, log providers
- custom log providers [Integration Services]
- SQL Server Integration Services packages, log providers
- log providers [Integration Services]
- packages [Integration Services], logs
- Integration Services packages, log providers
ms.assetid: 3f715b95-7074-4f5c-8ae2-246998052e78
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 88d4f70fa9d50628b831b56f9fa22100648fce51
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655881"
---
# <a name="developing-a-custom-log-provider"></a><span data-ttu-id="c6547-102">Разработка пользовательского регистратора</span><span class="sxs-lookup"><span data-stu-id="c6547-102">Developing a Custom Log Provider</span></span>
  <span data-ttu-id="c6547-103">В службах [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] имеются различные возможности по ведению журналов, которые позволяют отслеживать события, возникающие во время выполнения пакетов.</span><span class="sxs-lookup"><span data-stu-id="c6547-103">[!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] has extensive logging capabilities that make it possible to capture events that occur during package execution.</span></span> <span data-ttu-id="c6547-104">Службы [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] включают целый ряд регистраторов, используя которые можно создавать и сохранять журналы в различных форматах, например XML, текстовом, базы данных или в виде журнала событий Windows.</span><span class="sxs-lookup"><span data-stu-id="c6547-104">[!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] includes a variety of log providers that enable logs to be created and stored in formats such as XML, text, database, or in the Windows event log.</span></span> <span data-ttu-id="c6547-105">Если предоставляемые регистраторы и форматы выходных данных не вполне отвечают вашим требованиям, вы можете создать пользовательский регистратор.</span><span class="sxs-lookup"><span data-stu-id="c6547-105">If the log providers and the output formats that are provided do not entirely meet your requirements, you can create a custom log provider.</span></span>

 <span data-ttu-id="c6547-106">Чтобы создать пользовательский регистратор, необходимо создать класс, унаследованный от базового класса <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase>, применить к этому новому классу атрибут <xref:Microsoft.SqlServer.Dts.Runtime.DtsLogProviderAttribute> и переопределить важные методы и свойства базового класса, включая свойство <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.ConfigString%2A> и метод <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Log%2A>.</span><span class="sxs-lookup"><span data-stu-id="c6547-106">To create a custom log provider, you have to create a class that inherits from the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase> base class, apply the <xref:Microsoft.SqlServer.Dts.Runtime.DtsLogProviderAttribute> attribute to your new class, and override the important methods and properties of the base class, including the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.ConfigString%2A> property and the <xref:Microsoft.SqlServer.Dts.Runtime.LogProviderBase.Log%2A> method.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="c6547-107">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="c6547-107">In This Section</span></span>
 <span data-ttu-id="c6547-108">Этот раздел описывает создание, настройку и программирование пользовательского регистратора.</span><span class="sxs-lookup"><span data-stu-id="c6547-108">This section describes how to create, configure, and code a custom log provider.</span></span>

 <span data-ttu-id="c6547-109">[Создание пользовательского регистратора](creating-a-custom-log-provider.md) Описывает создание классов для пользовательского проекта регистратора.</span><span class="sxs-lookup"><span data-stu-id="c6547-109">[Creating a Custom Log Provider](creating-a-custom-log-provider.md) Describes how to create the classes for a custom log provider project.</span></span>

 <span data-ttu-id="c6547-110">[Программирование пользовательского регистратора](coding-a-custom-log-provider.md) Описывает реализацию пользовательского регистратора путем переопределения методов и свойств базового класса.</span><span class="sxs-lookup"><span data-stu-id="c6547-110">[Coding a Custom Log Provider](coding-a-custom-log-provider.md) Describes how to implement a custom log provider by overriding the methods and properties of the base class.</span></span>

 <span data-ttu-id="c6547-111">[Разработка пользовательского интерфейса для пользовательского регистратора](developing-a-user-interface-for-a-custom-log-provider.md) Настраиваемые пользовательские интерфейсы для пользовательских регистраторов не поддерживаются в [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c6547-111">[Developing a User Interface for a Custom Log Provider](developing-a-user-interface-for-a-custom-log-provider.md) Custom user interfaces for custom log providers are not supported in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)].</span></span>

## <a name="related-topics"></a><span data-ttu-id="c6547-112">См. также</span><span class="sxs-lookup"><span data-stu-id="c6547-112">Related Topics</span></span>

### <a name="information-common-to-all-custom-objects"></a><span data-ttu-id="c6547-113">Общие сведения для всех пользовательских объектов</span><span class="sxs-lookup"><span data-stu-id="c6547-113">Information Common to all Custom Objects</span></span>
 <span data-ttu-id="c6547-114">Сведения, общие для всех типов пользовательских объектов, которые можно создавать в службах [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], см. в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="c6547-114">For information that is common to all the type of custom objects that you can create in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], see the following topics:</span></span>

 <span data-ttu-id="c6547-115">[Разработка пользовательских объектов для Integration Services](../developing-custom-objects-for-integration-services.md) Описывает основные шаги реализации всех типов пользовательских объектов для [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c6547-115">[Developing Custom Objects for Integration Services](../developing-custom-objects-for-integration-services.md) Describes the basic steps in implementing all types of custom objects for [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)].</span></span>

 <span data-ttu-id="c6547-116">[Сохранение пользовательских объектов](../persisting-custom-objects.md) Описывает пользовательскую сохраняемость и объясняет, когда это необходимо.</span><span class="sxs-lookup"><span data-stu-id="c6547-116">[Persisting Custom Objects](../persisting-custom-objects.md) Describes custom persistence and explains when it is necessary.</span></span>

 <span data-ttu-id="c6547-117">[Сборка, развертывание и отладка пользовательских объектов](../building-deploying-and-debugging-custom-objects.md) Описывает методы создания, подписывания, развертывания и отладки пользовательских объектов.</span><span class="sxs-lookup"><span data-stu-id="c6547-117">[Building, Deploying, and Debugging Custom Objects](../building-deploying-and-debugging-custom-objects.md) Describes the techniques for building, signing, deploying, and debugging custom objects.</span></span>

### <a name="information-about-other-custom-objects"></a><span data-ttu-id="c6547-118">Сведения о других пользовательских объектах</span><span class="sxs-lookup"><span data-stu-id="c6547-118">Information about Other Custom Objects</span></span>
 <span data-ttu-id="c6547-119">Сведения о других типах пользовательских объектов, которые можно создавать в службах [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], см. в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="c6547-119">For information on the other types of custom objects that you can create in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], see the following topics:</span></span>

 <span data-ttu-id="c6547-120">[Разработка пользовательской задачи](../task/developing-a-custom-task.md) Описывает, как программировать пользовательские задачи.</span><span class="sxs-lookup"><span data-stu-id="c6547-120">[Developing a Custom Task](../task/developing-a-custom-task.md) Discusses how to program custom tasks.</span></span>

 <span data-ttu-id="c6547-121">[Разработка пользовательского диспетчера соединений](../connection-manager/developing-a-custom-connection-manager.md) Описывает, как программировать пользовательские диспетчеры соединений.</span><span class="sxs-lookup"><span data-stu-id="c6547-121">[Developing a Custom Connection Manager](../connection-manager/developing-a-custom-connection-manager.md) Discusses how to program custom connection managers.</span></span>

 <span data-ttu-id="c6547-122">[Разработка пользовательского перечислителя Foreach](../foreach-enumerator/developing-a-custom-foreach-enumerator.md) Описывает, как программировать пользовательские перечислители.</span><span class="sxs-lookup"><span data-stu-id="c6547-122">[Developing a Custom ForEach Enumerator](../foreach-enumerator/developing-a-custom-foreach-enumerator.md) Discusses how to program custom enumerators.</span></span>

 <span data-ttu-id="c6547-123">[Разработка пользовательского компонента потока данных](../data-flow/developing-a-custom-data-flow-component.md) Описывает, как программировать пользовательские источники потока данных, преобразования и назначения.</span><span class="sxs-lookup"><span data-stu-id="c6547-123">[Developing a Custom Data Flow Component](../data-flow/developing-a-custom-data-flow-component.md) Discusses how to program custom data flow sources, transformations, and destinations.</span></span>

<span data-ttu-id="c6547-124">![Значок Integration Services (маленький)](../../media/dts-16.gif "Значок служб Integration Services (маленький)")  **следит за обновлениями Integration Services**</span><span class="sxs-lookup"><span data-stu-id="c6547-124">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="c6547-125">Чтобы загрузить новейшую документацию, статьи, образцы и видеоматериалы корпорации Майкрософт, а также лучшие решения участников сообщества, посетите страницу служб [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] на сайте MSDN:</span><span class="sxs-lookup"><span data-stu-id="c6547-125">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="c6547-126">Посетить страницу «Службы Integration Services» на сайте MSDN</span><span class="sxs-lookup"><span data-stu-id="c6547-126">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="c6547-127">Чтобы получать автоматические уведомления об этих обновлениях, подпишитесь на RSS-каналы, предлагаемые на этой странице.</span><span class="sxs-lookup"><span data-stu-id="c6547-127">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>


