---
title: Расширение пакетов с помощью пользовательских объектов | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
ms.assetid: 26616eb8-9e80-434d-b22a-ece1b00f449d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0159983f518e51aa082ea23745663e7f09eee1fc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727289"
---
# <a name="extending-packages-with-custom-objects"></a><span data-ttu-id="012bd-102">Расширение пакетов с помощью пользовательских объектов</span><span class="sxs-lookup"><span data-stu-id="012bd-102">Extending Packages with Custom Objects</span></span>
  <span data-ttu-id="012bd-103">Если встроенные компоненты служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] не отвечают требованиям, их можно расширить, создав собственные программные расширения служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="012bd-103">If you find that the components provided in [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] do not meet your requirements, you can extend the power of [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] by coding your own extensions.</span></span> <span data-ttu-id="012bd-104">Существует два варианта расширения пакетов: можно написать код с использованием возможностей многофункциональных оболочек, предоставляемых задачей «Скрипт» и компонентом скрипта или самостоятельно создать пользовательские расширения служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], используя классы, производные от базовых классов, предоставляемых объектной моделью служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="012bd-104">You have two discrete options for extending your packages: you can write code within the powerful wrappers provided by the Script task and the Script component, or you can create custom [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] extensions from scratch by deriving from the base classes provided by the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] object model.</span></span>  
  
 <span data-ttu-id="012bd-105">В этом разделе подробно рассматривается расширение пакетов с помощью пользовательских объектов — вариант, предоставляющий более широкие возможности.</span><span class="sxs-lookup"><span data-stu-id="012bd-105">This section explores the more advanced of the two options - extending packages with custom objects.</span></span>  
  
 <span data-ttu-id="012bd-106">Если пользовательское решение служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] требует большей гибкости, чем обеспечивает задача или компонент «Скрипт», или если есть необходимость использования компонента, применение которого возможно в нескольких пакетах, модель объектов служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] позволяет создавать с нуля пользовательские задачи, компоненты потока данных и другие объекты пакета в управляемом коде.</span><span class="sxs-lookup"><span data-stu-id="012bd-106">When your custom [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] solution requires more flexibility than the Script task and the Script component provide, or when you need a component that you can reuse in multiple packages, the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] object model lets you build custom tasks, data flow components, and other package objects in managed code from the ground up.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="012bd-107">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="012bd-107">In This Section</span></span>  
 [<span data-ttu-id="012bd-108">Разработка пользовательских объектов для служб Integration Services</span><span class="sxs-lookup"><span data-stu-id="012bd-108">Developing Custom Objects for Integration Services</span></span>](developing-custom-objects-for-integration-services.md)  
 <span data-ttu-id="012bd-109">Описывает пользовательские объекты, которые можно создать для работы со службами [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], включая необходимые шаги и настройки.</span><span class="sxs-lookup"><span data-stu-id="012bd-109">Discusses the custom objects that can be created for [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], and summarizes the essential steps and settings.</span></span>  
  
 [<span data-ttu-id="012bd-110">Сохранение пользовательских объектов</span><span class="sxs-lookup"><span data-stu-id="012bd-110">Persisting Custom Objects</span></span>](persisting-custom-objects.md)  
 <span data-ttu-id="012bd-111">Описывает механизм сохраняемости по умолчанию пользовательских объектов и процесс реализации пользовательской сохраняемости.</span><span class="sxs-lookup"><span data-stu-id="012bd-111">Discusses the default persistence of custom objects, and the process of implementing custom persistence.</span></span>  
  
 [<span data-ttu-id="012bd-112">Сборка, развертывание и отладка пользовательских объектов</span><span class="sxs-lookup"><span data-stu-id="012bd-112">Building, Deploying, and Debugging Custom Objects</span></span>](building-deploying-and-debugging-custom-objects.md)  
 <span data-ttu-id="012bd-113">Описывает общие подходы к построению, развертыванию и тестированию различных типов пользовательских объектов.</span><span class="sxs-lookup"><span data-stu-id="012bd-113">Discusses the common approaches to building, deploying and testing the various types of custom objects.</span></span>  
  
 [<span data-ttu-id="012bd-114">Разработка пользовательской задачи</span><span class="sxs-lookup"><span data-stu-id="012bd-114">Developing a Custom Task</span></span>](task/developing-a-custom-task.md)  
 <span data-ttu-id="012bd-115">Описывает процесс программирования пользовательской задачи.</span><span class="sxs-lookup"><span data-stu-id="012bd-115">Describes the process of coding a custom task.</span></span>  
  
 [<span data-ttu-id="012bd-116">Разработка пользовательского диспетчера соединений</span><span class="sxs-lookup"><span data-stu-id="012bd-116">Developing a Custom Connection Manager</span></span>](connection-manager/developing-a-custom-connection-manager.md)  
 <span data-ttu-id="012bd-117">Описывает процесс программирования пользовательского диспетчера соединений.</span><span class="sxs-lookup"><span data-stu-id="012bd-117">Describes the process of coding a custom connection manager.</span></span>  
  
 [<span data-ttu-id="012bd-118">Разработка пользовательского регистратора</span><span class="sxs-lookup"><span data-stu-id="012bd-118">Developing a Custom Log Provider</span></span>](log-provider/developing-a-custom-log-provider.md)  
 <span data-ttu-id="012bd-119">Описывает процесс программирования пользовательского регистратора.</span><span class="sxs-lookup"><span data-stu-id="012bd-119">Describes the process of coding a custom log provider.</span></span>  
  
 [<span data-ttu-id="012bd-120">Разработка пользовательского перечислителя по каждому элементу</span><span class="sxs-lookup"><span data-stu-id="012bd-120">Developing a Custom ForEach Enumerator</span></span>](foreach-enumerator/developing-a-custom-foreach-enumerator.md)  
 <span data-ttu-id="012bd-121">Описывает процесс программирования пользовательского перечислителя.</span><span class="sxs-lookup"><span data-stu-id="012bd-121">Describes the process of coding a custom enumerator.</span></span>  
  
 [<span data-ttu-id="012bd-122">Разработка пользовательского компонента потока данных</span><span class="sxs-lookup"><span data-stu-id="012bd-122">Developing a Custom Data Flow Component</span></span>](data-flow/developing-a-custom-data-flow-component.md)  
 <span data-ttu-id="012bd-123">Описывает вопросы программирования пользовательских источников, преобразований и назначений потока данных.</span><span class="sxs-lookup"><span data-stu-id="012bd-123">Discusses how to program custom data flow sources, transformations, and destinations.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="012bd-124">Справочник</span><span class="sxs-lookup"><span data-stu-id="012bd-124">Reference</span></span>  
 [<span data-ttu-id="012bd-125">Справочник по сообщениям об ошибках служб Integration Services</span><span class="sxs-lookup"><span data-stu-id="012bd-125">Integration Services Error and Message Reference</span></span>](../integration-services-error-and-message-reference.md)  
 <span data-ttu-id="012bd-126">Содержится список стандартных кодов ошибок служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] с символическими именами и описаниями.</span><span class="sxs-lookup"><span data-stu-id="012bd-126">Lists the predefined [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] error codes with their symbolic names and descriptions.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="012bd-127">См. также</span><span class="sxs-lookup"><span data-stu-id="012bd-127">Related Sections</span></span>  
 [<span data-ttu-id="012bd-128">Расширение пакетов с помощью сценариев</span><span class="sxs-lookup"><span data-stu-id="012bd-128">Extending Packages with Scripting</span></span>](../extending-packages-scripting/extending-packages-with-scripting.md)  
 <span data-ttu-id="012bd-129">Описывает способ расширения потока управления с помощью задачи «Скрипт» или потока данных с помощью компонента скрипта.</span><span class="sxs-lookup"><span data-stu-id="012bd-129">Discusses how to extend the control flow by using the Script task, or extend the data flow by using the Script component.</span></span>  
  
 [<span data-ttu-id="012bd-130">Программное построение пакетов</span><span class="sxs-lookup"><span data-stu-id="012bd-130">Building Packages Programmatically</span></span>](../building-packages-programmatically/building-packages-programmatically.md)  
 <span data-ttu-id="012bd-131">Описывает создание, настройку, запуск, загрузку и сохранение пакетов служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] программным образом, а также программное выполнение других задач управления.</span><span class="sxs-lookup"><span data-stu-id="012bd-131">Describes how to create, configure, run, load, save, and manage [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages programmatically.</span></span>  
  
<span data-ttu-id="012bd-132">![Значок Integration Services (маленький)](../media/dts-16.gif "Значок служб Integration Services (маленький)")  **следит за обновлениями Integration Services**</span><span class="sxs-lookup"><span data-stu-id="012bd-132">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="012bd-133">Чтобы загрузить новейшую документацию, статьи, образцы и видеоматериалы корпорации Майкрософт, а также лучшие решения участников сообщества, посетите страницу служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] на сайте MSDN:</span><span class="sxs-lookup"><span data-stu-id="012bd-133">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="012bd-134">Посетить страницу «Службы Integration Services» на сайте MSDN</span><span class="sxs-lookup"><span data-stu-id="012bd-134">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="012bd-135">Чтобы получать автоматические уведомления об этих обновлениях, подпишитесь на RSS-каналы, предлагаемые на этой странице.</span><span class="sxs-lookup"><span data-stu-id="012bd-135">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="012bd-136">См. также:</span><span class="sxs-lookup"><span data-stu-id="012bd-136">See Also</span></span>  
 <span data-ttu-id="012bd-137">[Сравнение решений со скриптами и пользовательских объектов](../extending-packages-scripting/comparing-scripting-solutions-and-custom-objects.md) </span><span class="sxs-lookup"><span data-stu-id="012bd-137">[Comparing Scripting Solutions and Custom Objects](../extending-packages-scripting/comparing-scripting-solutions-and-custom-objects.md) </span></span>  
 [<span data-ttu-id="012bd-138">SQL Server Integration Services</span><span class="sxs-lookup"><span data-stu-id="012bd-138">SQL Server Integration Services</span></span>](../sql-server-integration-services.md)  
  
  
