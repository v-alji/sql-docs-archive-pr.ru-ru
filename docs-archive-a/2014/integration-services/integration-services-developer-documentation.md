---
title: Руководством разработчика&#39;s (Integration Services) | Документация Майкрософт
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Integration Services, programming
- SSIS, programming
- SQL Server Integration Services, programming
- packages [Integration Services], programming
ms.assetid: 60fe148b-a7c4-4289-ae3e-2e949fc1886c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c16ec1a21cf7ebb711f6d3996eb6239ea052c83c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667275"
---
# <a name="developer39s-guide-integration-services"></a><span data-ttu-id="d60c5-102">Руководством для разработчиков&#39;(Integration Services)</span><span class="sxs-lookup"><span data-stu-id="d60c5-102">Developer&#39;s Guide (Integration Services)</span></span>
  <span data-ttu-id="d60c5-103">Службы [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] включают полностью переписанную модель объектов, которая была улучшена многими функциями, позволяющими упростить расширение и программирование пакетов и сделать их более гибкими и более мощными.</span><span class="sxs-lookup"><span data-stu-id="d60c5-103">[!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] includes a completely rewritten object model, which has been enhanced with many features that make extending and programming packages easier, more flexible, and more powerful.</span></span> <span data-ttu-id="d60c5-104">Разработчики могут расширять и программировать пакеты служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] почти в любом аспекте.</span><span class="sxs-lookup"><span data-stu-id="d60c5-104">Developers can extend and program almost every aspect of [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] packages.</span></span>  
  
 <span data-ttu-id="d60c5-105">Разработчик служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] может воспользоваться двумя фундаментальными подходами при программировании служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d60c5-105">As an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] developer, there are two fundamental approaches that you can take to [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] programming:</span></span>  
  
-   <span data-ttu-id="d60c5-106">Можно расширять пакеты путем создания компонентов, которые становятся доступными в конструкторе служб [!INCLUDE[ssIS](../includes/ssis-md.md)], чтобы предоставить пользовательскую функциональность в пакете.</span><span class="sxs-lookup"><span data-stu-id="d60c5-106">You can extend packages by writing components that become available within [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer to provide custom functionality in a package.</span></span>  
  
-   <span data-ttu-id="d60c5-107">Можно создавать, настраивать и выполнять пакеты программным путем из собственных приложений.</span><span class="sxs-lookup"><span data-stu-id="d60c5-107">You can create, configure, and run packages programmatically from your own applications.</span></span>  
  
 <span data-ttu-id="d60c5-108">Если обнаруживается, что встроенные компоненты в службах [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] не соответствуют конкретным требованиям, можно расширить возможности служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], разработав собственные модули.</span><span class="sxs-lookup"><span data-stu-id="d60c5-108">If you find that the built-in components in [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] do not meet your requirements, you can extend the power of [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] by coding your own extensions.</span></span> <span data-ttu-id="d60c5-109">Этот подход подразделяется на два отдельных способа.</span><span class="sxs-lookup"><span data-stu-id="d60c5-109">In this approach, you have two discrete options:</span></span>  
  
-   <span data-ttu-id="d60c5-110">Для нерегламентированного использования в одном пакете можно создать пользовательскую задачу, написав код в задаче «Скрипт», или разработать пользовательский компонент потока данных, написав код в компоненте скрипта, который можно настроить как источник, преобразование или назначение.</span><span class="sxs-lookup"><span data-stu-id="d60c5-110">For ad hoc use in a single package, you can create a custom task by writing code in the Script task, or a custom data flow component by writing code in the Script component, which you can configure as a source, transformation, or destination.</span></span> <span data-ttu-id="d60c5-111">Эти мощные оболочки сами создают инфраструктурный код для разработчика и позволяют ему сосредоточиться исключительно на создании пользовательской функциональности. Однако при этом сложно создать повторно используемый код.</span><span class="sxs-lookup"><span data-stu-id="d60c5-111">These powerful wrappers write the infrastructure code for you and let you focus exclusively on developing your custom functionality; however, they are not easily reusable elsewhere.</span></span>  
  
-   <span data-ttu-id="d60c5-112">Для использования в нескольких пакетах можно создать пользовательские модули служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], такие как диспетчеры соединений, задачи, перечислители, регистраторы и компоненты потока данных.</span><span class="sxs-lookup"><span data-stu-id="d60c5-112">For use in multiple packages, you can create custom [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] extensions such as connection managers, tasks, enumerators, log providers, and data flow components.</span></span> <span data-ttu-id="d60c5-113">Управляемая модель объектов служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] содержит базовые классы, которые предоставляют исходную точку и позволяют разрабатывать пользовательские модули проще, чем когда-либо.</span><span class="sxs-lookup"><span data-stu-id="d60c5-113">The managed [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] object model contains base classes that provide a starting point and make developing custom extensions easier than ever.</span></span>  
  
 <span data-ttu-id="d60c5-114">Если требуется создавать пакеты динамически или управлять и запускать пакеты служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] за пределами среды разработки, можно воспользоваться возможностью управлять пакетами программным путем.</span><span class="sxs-lookup"><span data-stu-id="d60c5-114">If you want to create packages dynamically, or to manage and run [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] packages outside the development environment, you can manipulate packages programmatically.</span></span> <span data-ttu-id="d60c5-115">Можно загружать, изменять и запускать существующие пакеты или создавать и запускать полностью новые пакеты программным путем.</span><span class="sxs-lookup"><span data-stu-id="d60c5-115">You can load, modify, and run existing packages, or you can create and run entirely new packages programmatically.</span></span> <span data-ttu-id="d60c5-116">Этот подход предлагает следующий набор вариантов.</span><span class="sxs-lookup"><span data-stu-id="d60c5-116">In this approach, you have a continuous range of options:</span></span>  
  
-   <span data-ttu-id="d60c5-117">Загрузка и выполнение существующего пакета без изменения.</span><span class="sxs-lookup"><span data-stu-id="d60c5-117">Load and run an existing package without modification.</span></span>  
  
-   <span data-ttu-id="d60c5-118">Загрузка существующего пакета, изменение его конфигурации (например, указание другого источника данных) и выполнение пакета.</span><span class="sxs-lookup"><span data-stu-id="d60c5-118">Load an existing package, reconfigure it (for example, specify a different data source), and run it.</span></span>  
  
-   <span data-ttu-id="d60c5-119">Создание нового пакета, добавление и настройка компонентов, изменение одного объекта за другим и одного свойства за другим, сохранение пакета, а затем выполнение.</span><span class="sxs-lookup"><span data-stu-id="d60c5-119">Create a new package, add and configure components, making changes object by object and property by property, save it, and then run it.</span></span>  
  
 <span data-ttu-id="d60c5-120">Эти подходы к программированию служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] описаны в этом разделе и демонстрируются на примерах.</span><span class="sxs-lookup"><span data-stu-id="d60c5-120">These approaches to [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] programming are described in this section and demonstrated with examples.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d60c5-121">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="d60c5-121">In This Section</span></span>  
 [<span data-ttu-id="d60c5-122">Общие сведения о программировании служб Integration Services</span><span class="sxs-lookup"><span data-stu-id="d60c5-122">Integration Services Programming Overview</span></span>](integration-services-programming-overview.md)  
 <span data-ttu-id="d60c5-123">Описывает роли потока управления и потока данных в разработке служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d60c5-123">Describes the roles of control flow and data flow in [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] development.</span></span>  
  
 [<span data-ttu-id="d60c5-124">Основные сведения о синхронных и асинхронных преобразованиях</span><span class="sxs-lookup"><span data-stu-id="d60c5-124">Understanding Synchronous and Asynchronous Transformations</span></span>](understanding-synchronous-and-asynchronous-transformations.md)  
 <span data-ttu-id="d60c5-125">Описывает важное различие между синхронными и асинхронными выходами, а также описывает компоненты, в которых используются эти выходы в потоке данных.</span><span class="sxs-lookup"><span data-stu-id="d60c5-125">Describes the important distinction between synchronous and asynchronous outputs and the components that use them in the data flow.</span></span>  
  
 [<span data-ttu-id="d60c5-126">Работа с диспетчерами соединений программным образом</span><span class="sxs-lookup"><span data-stu-id="d60c5-126">Working with Connection Managers Programmatically</span></span>](working-with-connection-managers-programmatically.md)  
 <span data-ttu-id="d60c5-127">Описывает диспетчеры соединений, которые можно использовать из управляемого кода, а также значения, возвращаемые диспетчерами при вызове метода `AcquireConnection` из кода.</span><span class="sxs-lookup"><span data-stu-id="d60c5-127">Lists the connection managers that you can use from managed code, and the values that the connection managers return when the code calls the `AcquireConnection` method.</span></span>  
  
 [<span data-ttu-id="d60c5-128">Расширение пакетов с помощью сценариев</span><span class="sxs-lookup"><span data-stu-id="d60c5-128">Extending Packages with Scripting</span></span>](extending-packages-scripting/extending-packages-with-scripting.md)  
 <span data-ttu-id="d60c5-129">Показывает, как расширить поток управления с помощью задачи «Скрипт» или поток данных с помощью компонента скрипта.</span><span class="sxs-lookup"><span data-stu-id="d60c5-129">Describes how to extend the control flow by using the Script task, or the data flow by using the Script component.</span></span>  
  
 [<span data-ttu-id="d60c5-130">Расширение пакетов с помощью пользовательских объектов</span><span class="sxs-lookup"><span data-stu-id="d60c5-130">Extending Packages with Custom Objects</span></span>](extending-packages-custom-objects/extending-packages-with-custom-objects.md)  
 <span data-ttu-id="d60c5-131">Показывает, как создавать и программировать пользовательские задачи, компоненты потока данных и другие объекты пакета для применения в нескольких пакетах.</span><span class="sxs-lookup"><span data-stu-id="d60c5-131">Describes how to create and program custom tasks, data flow components, and other package objects for use in multiple packages.</span></span>  
  
 [<span data-ttu-id="d60c5-132">Программное построение пакетов</span><span class="sxs-lookup"><span data-stu-id="d60c5-132">Building Packages Programmatically</span></span>](building-packages-programmatically/building-packages-programmatically.md)  
 <span data-ttu-id="d60c5-133">Показывает, как создавать, настраивать и сохранять пакеты служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] программным путем.</span><span class="sxs-lookup"><span data-stu-id="d60c5-133">Describes how to create, configure, and save [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] packages programmatically.</span></span>  
  
 [<span data-ttu-id="d60c5-134">Выполнение пакетов и управление пакетами программным образом</span><span class="sxs-lookup"><span data-stu-id="d60c5-134">Running and Managing Packages Programmatically</span></span>](run-manage-packages-programmatically/running-and-managing-packages-programmatically.md)  
 <span data-ttu-id="d60c5-135">Показывает, как перечислять, запускать пакеты служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] и управлять ими программным путем.</span><span class="sxs-lookup"><span data-stu-id="d60c5-135">Describes how to enumerate, run, and manage [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] packages programmatically.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="d60c5-136">Справочник</span><span class="sxs-lookup"><span data-stu-id="d60c5-136">Reference</span></span>  
 [<span data-ttu-id="d60c5-137">Справочник по сообщениям об ошибках служб Integration Services</span><span class="sxs-lookup"><span data-stu-id="d60c5-137">Integration Services Error and Message Reference</span></span>](integration-services-error-and-message-reference.md)  
 <span data-ttu-id="d60c5-138">Содержит список стандартных кодов ошибок служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] с символическими именами и описаниями.</span><span class="sxs-lookup"><span data-stu-id="d60c5-138">Lists the predefined [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] error codes, together with their symbolic names and descriptions.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="d60c5-139">См. также</span><span class="sxs-lookup"><span data-stu-id="d60c5-139">Related Sections</span></span>  
 [<span data-ttu-id="d60c5-140">Инструменты устранения неполадок при разработке пакета</span><span class="sxs-lookup"><span data-stu-id="d60c5-140">Troubleshooting Tools for Package Development</span></span>](troubleshooting/troubleshooting-tools-for-package-development.md)  
 <span data-ttu-id="d60c5-141">Описывает возможности и инструментальные средства служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], предназначенные для устранения неполадок в пакетах в процессе разработки.</span><span class="sxs-lookup"><span data-stu-id="d60c5-141">Describes the features and tools that [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] provides for troubleshooting packages during development.</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="d60c5-142">Внешние ресурсы</span><span class="sxs-lookup"><span data-stu-id="d60c5-142">External Resources</span></span>  
  
-   <span data-ttu-id="d60c5-143">Образцы CodePlex, [Образцы продуктов служб Integration Services](https://go.microsoft.com/fwlink/?LinkID=131204)на сайте www.codeplex.com/MSFTISProdSamples</span><span class="sxs-lookup"><span data-stu-id="d60c5-143">CodePlex samples, [Integration Services Product Samples](https://go.microsoft.com/fwlink/?LinkID=131204), on www.codeplex.com/MSFTISProdSamples</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d60c5-144">См. также:</span><span class="sxs-lookup"><span data-stu-id="d60c5-144">See Also</span></span>  
 [<span data-ttu-id="d60c5-145">SQL Server Integration Services</span><span class="sxs-lookup"><span data-stu-id="d60c5-145">SQL Server Integration Services</span></span>](sql-server-integration-services.md)  
  
  
