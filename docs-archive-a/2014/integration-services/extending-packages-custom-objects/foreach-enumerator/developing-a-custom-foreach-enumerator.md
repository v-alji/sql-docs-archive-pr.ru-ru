---
title: Разработка пользовательского перечислителя по каждому элементу | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- custom foreach enumerators [Integration Services]
- custom foreach enumerators [Integration Services], about custom foreach enumerators
- foreach enumerators [Integration Services]
ms.assetid: bffe26e0-1b9a-47ad-bae6-6b708cb4cf4f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: bc3d61f98266320f63d7ee56262b7c85dfb64d39
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664428"
---
# <a name="developing-a-custom-foreach-enumerator"></a><span data-ttu-id="c4a27-102">Разработка пользовательского перечислителя по каждому элементу</span><span class="sxs-lookup"><span data-stu-id="c4a27-102">Developing a Custom ForEach Enumerator</span></span>
  <span data-ttu-id="c4a27-103">Для итерации по элементам коллекции и выполнения одинаковых задач для каждого элемента службы [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] используют перечислители по каждому элементу.</span><span class="sxs-lookup"><span data-stu-id="c4a27-103">[!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] uses foreach enumerators to iterate over the items in a collection and perform the same tasks for each element.</span></span> <span data-ttu-id="c4a27-104">Службы [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] содержат ряд различных перечислителей по каждому элементу, которыми поддерживается большинство наиболее часто используемых коллекций, например, все файлы в папке, все таблицы в базе данных или все элементы в списке, хранящемся в переменной пакета.</span><span class="sxs-lookup"><span data-stu-id="c4a27-104">[!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] includes a variety of foreach enumerators that support the most commonly used collections, such as all the files in a folder, all the tables in a database, or all the elements of a list stored in a package variable.</span></span> <span data-ttu-id="c4a27-105">Если предлагаемый выбор перечислителей по каждому элементу и коллекций не отвечает потребностям пользователя, можно создать пользовательский перечислитель по каждому элементу.</span><span class="sxs-lookup"><span data-stu-id="c4a27-105">If the foreach enumerators and collections that are provided do not entirely meet your requirements, you can create a custom foreach enumerator.</span></span>  
  
 <span data-ttu-id="c4a27-106">Для создания пользовательского перечислителя по каждому элементу необходимо создать класс, наследующий от базового класса <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator>, применить атрибут <xref:Microsoft.SqlServer.Dts.Runtime.DtsForEachEnumeratorAttribute> к новому классу и переопределить важные методы и свойства базового класса, в том числе метод <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator.GetEnumerator%2A>.</span><span class="sxs-lookup"><span data-stu-id="c4a27-106">To create a custom foreach enumerator, you have to create a class that inherits from the <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator> base class, apply the <xref:Microsoft.SqlServer.Dts.Runtime.DtsForEachEnumeratorAttribute> attribute to your new class, and override the important methods and properties of the base class, including the <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator.GetEnumerator%2A> method.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c4a27-107">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="c4a27-107">In This Section</span></span>  
 <span data-ttu-id="c4a27-108">В этом разделе описывается, как создавать, настраивать и кодировать пользовательский перечислитель по каждому элементу и, при необходимости, его пользовательский интерфейс.</span><span class="sxs-lookup"><span data-stu-id="c4a27-108">This section describes how to create, configure, and code a custom foreach enumerator and its custom user interface.</span></span>  
  
 [<span data-ttu-id="c4a27-109">Создание пользовательского перечислителя по каждому элементу</span><span class="sxs-lookup"><span data-stu-id="c4a27-109">Creating a Custom Foreach Enumerator</span></span>](creating-a-custom-foreach-enumerator.md)  
 <span data-ttu-id="c4a27-110">Описывает, как создать классы для проекта пользовательского перечислителя по каждому элементу.</span><span class="sxs-lookup"><span data-stu-id="c4a27-110">Describes how to create the classes for a custom foreach enumerator project.</span></span>  
  
 [<span data-ttu-id="c4a27-111">Написание кода пользовательского перечислителя по каждому элементу</span><span class="sxs-lookup"><span data-stu-id="c4a27-111">Coding a Custom Foreach Enumerator</span></span>](coding-a-custom-foreach-enumerator.md)  
 <span data-ttu-id="c4a27-112">Описывает, как реализовать пользовательский перечислитель по каждому элементу путем переопределения методов и свойств базового класса.</span><span class="sxs-lookup"><span data-stu-id="c4a27-112">Describes how to implement a custom foreach enumerator by overriding the methods and properties of the base class.</span></span>  
  
 [<span data-ttu-id="c4a27-113">Разработка пользовательского интерфейса для пользовательского перечислителя по каждому элементу</span><span class="sxs-lookup"><span data-stu-id="c4a27-113">Developing a User Interface for a Custom ForEach Enumerator</span></span>](developing-a-user-interface-for-a-custom-foreach-enumerator.md)  
 <span data-ttu-id="c4a27-114">Описывает, как реализовать класс пользовательского интерфейса и форму, используемую для настройки пользовательского перечислителя по каждому элементу.</span><span class="sxs-lookup"><span data-stu-id="c4a27-114">Describes how to implement the user interface class and the form that is used to configure the custom foreach enumerator.</span></span>  
  
## <a name="related-topics"></a><span data-ttu-id="c4a27-115">См. также</span><span class="sxs-lookup"><span data-stu-id="c4a27-115">Related Topics</span></span>  
  
### <a name="information-common-to-all-custom-objects"></a><span data-ttu-id="c4a27-116">Общие сведения для всех пользовательских объектов</span><span class="sxs-lookup"><span data-stu-id="c4a27-116">Information Common to all Custom Objects</span></span>  
 <span data-ttu-id="c4a27-117">Сведения, общие для всех типов пользовательских объектов, которые можно создавать в службах [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], см. в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="c4a27-117">For information that is common to all the type of custom objects that you can create in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], see the following topics:</span></span>  
  
 [<span data-ttu-id="c4a27-118">Разработка пользовательских объектов для служб Integration Services</span><span class="sxs-lookup"><span data-stu-id="c4a27-118">Developing Custom Objects for Integration Services</span></span>](../developing-custom-objects-for-integration-services.md)  
 <span data-ttu-id="c4a27-119">Описывает основные шаги по реализации всех типов пользовательских объектов для служб [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c4a27-119">Describes the basic steps in implementing all types of custom objects for [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="c4a27-120">Сохранение пользовательских объектов</span><span class="sxs-lookup"><span data-stu-id="c4a27-120">Persisting Custom Objects</span></span>](../persisting-custom-objects.md)  
 <span data-ttu-id="c4a27-121">Описывает пользовательский механизм сохраняемости, при необходимости приводя пояснения.</span><span class="sxs-lookup"><span data-stu-id="c4a27-121">Describes custom persistence and explains when it is necessary.</span></span>  
  
 [<span data-ttu-id="c4a27-122">Сборка, развертывание и отладка пользовательских объектов</span><span class="sxs-lookup"><span data-stu-id="c4a27-122">Building, Deploying, and Debugging Custom Objects</span></span>](../building-deploying-and-debugging-custom-objects.md)  
 <span data-ttu-id="c4a27-123">Описывает методы построения, подписывания, развертывания и отладки пользовательских объектов.</span><span class="sxs-lookup"><span data-stu-id="c4a27-123">Describes the techniques for building, signing, deploying, and debugging custom objects.</span></span>  
  
### <a name="information-about-other-custom-objects"></a><span data-ttu-id="c4a27-124">Сведения о других пользовательских объектах</span><span class="sxs-lookup"><span data-stu-id="c4a27-124">Information about Other Custom Objects</span></span>  
 <span data-ttu-id="c4a27-125">Сведения о других типах пользовательских объектов, которые можно создавать в службах [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], см. в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="c4a27-125">For information on the other types of custom objects that you can create in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], see the following topics:</span></span>  
  
 [<span data-ttu-id="c4a27-126">Разработка пользовательской задачи</span><span class="sxs-lookup"><span data-stu-id="c4a27-126">Developing a Custom Task</span></span>](../task/developing-a-custom-task.md)  
 <span data-ttu-id="c4a27-127">Описывает программирование пользовательских задач.</span><span class="sxs-lookup"><span data-stu-id="c4a27-127">Discusses how to program custom tasks.</span></span>  
  
 [<span data-ttu-id="c4a27-128">Разработка пользовательского диспетчера соединений</span><span class="sxs-lookup"><span data-stu-id="c4a27-128">Developing a Custom Connection Manager</span></span>](../connection-manager/developing-a-custom-connection-manager.md)  
 <span data-ttu-id="c4a27-129">Описывает вопросы программирования пользовательских диспетчеров соединений.</span><span class="sxs-lookup"><span data-stu-id="c4a27-129">Discusses how to program custom connection managers.</span></span>  
  
 [<span data-ttu-id="c4a27-130">Разработка пользовательского регистратора</span><span class="sxs-lookup"><span data-stu-id="c4a27-130">Developing a Custom Log Provider</span></span>](../log-provider/developing-a-custom-log-provider.md)  
 <span data-ttu-id="c4a27-131">Описывает вопросы программирования пользовательских регистраторов.</span><span class="sxs-lookup"><span data-stu-id="c4a27-131">Discusses how to program custom log providers.</span></span>  
  
 [<span data-ttu-id="c4a27-132">Разработка пользовательского компонента потока данных</span><span class="sxs-lookup"><span data-stu-id="c4a27-132">Developing a Custom Data Flow Component</span></span>](../data-flow/developing-a-custom-data-flow-component.md)  
 <span data-ttu-id="c4a27-133">Описывает вопросы программирования пользовательских источников, преобразований и назначений потока данных.</span><span class="sxs-lookup"><span data-stu-id="c4a27-133">Discusses how to program custom data flow sources, transformations, and destinations.</span></span>  
  
<span data-ttu-id="c4a27-134">![Значок Integration Services (маленький)](../../media/dts-16.gif "Значок служб Integration Services (маленький)")  **следит за обновлениями Integration Services**</span><span class="sxs-lookup"><span data-stu-id="c4a27-134">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="c4a27-135">Чтобы загрузить новейшую документацию, статьи, образцы и видеоматериалы корпорации Майкрософт, а также лучшие решения участников сообщества, посетите страницу служб [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] на сайте MSDN:</span><span class="sxs-lookup"><span data-stu-id="c4a27-135">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="c4a27-136">Посетить страницу «Службы Integration Services» на сайте MSDN</span><span class="sxs-lookup"><span data-stu-id="c4a27-136">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="c4a27-137">Чтобы получать автоматические уведомления об этих обновлениях, подпишитесь на RSS-каналы, предлагаемые на этой странице.</span><span class="sxs-lookup"><span data-stu-id="c4a27-137">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
  
