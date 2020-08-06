---
title: Разработка компонентов скрипта определенных типов | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- Script component [Integration Services], examples
ms.assetid: dfbbe959-6b4e-4b47-b9dd-bcc31929482d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 114c9ddca90ea02a8e1847444b28b9d5876650a9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664994"
---
# <a name="developing-specific-types-of-script-components"></a><span data-ttu-id="4872c-102">Разработка компонентов скрипта определенных типов</span><span class="sxs-lookup"><span data-stu-id="4872c-102">Developing Specific Types of Script Components</span></span>
  <span data-ttu-id="4872c-103">Компонент скрипта является настраиваемым средством, которое можно использовать в потоке данных пакета, чтобы выполнить практическое любое требование, которое не удается выполнить с помощью источников, преобразований и назначений, входящих в состав служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4872c-103">The Script component is a configurable tool that you can use in the data flow of a package to fill almost any requirement that is not met by the sources, transformations, and destinations that are included with [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span></span> <span data-ttu-id="4872c-104">В этом разделе содержатся образцы кода компонента скрипта, с помощью которых демонстрируются четыре варианта настройки компонента скрипта:</span><span class="sxs-lookup"><span data-stu-id="4872c-104">This section contains Script component code samples that demonstrate the four options for configuring the Script component:</span></span>  
  
-   <span data-ttu-id="4872c-105">В качестве источника.</span><span class="sxs-lookup"><span data-stu-id="4872c-105">As a source.</span></span>  
  
-   <span data-ttu-id="4872c-106">В качестве преобразования с синхронными выходами.</span><span class="sxs-lookup"><span data-stu-id="4872c-106">As a transformation with synchronous outputs.</span></span>  
  
-   <span data-ttu-id="4872c-107">В качестве преобразования с асинхронными выходами.</span><span class="sxs-lookup"><span data-stu-id="4872c-107">As a transformation with asynchronous outputs.</span></span>  
  
-   <span data-ttu-id="4872c-108">В качестве назначения.</span><span class="sxs-lookup"><span data-stu-id="4872c-108">As a destination.</span></span>  
  
 <span data-ttu-id="4872c-109">Дополнительные примеры компонента скрипта, см. в разделе [Дополнительные примеры компонента скрипта](../extending-packages-scripting-data-flow-script-component-examples/additional-script-component-examples.md).</span><span class="sxs-lookup"><span data-stu-id="4872c-109">For additional examples of the Script component, see [Additional Script Component Examples](../extending-packages-scripting-data-flow-script-component-examples/additional-script-component-examples.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4872c-110">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="4872c-110">In This Section</span></span>  
 [<span data-ttu-id="4872c-111">Создание источника с помощью компонента скрипта</span><span class="sxs-lookup"><span data-stu-id="4872c-111">Creating a Source with the Script Component</span></span>](creating-a-source-with-the-script-component.md)  
 <span data-ttu-id="4872c-112">Поясняет и демонстрирует, как создать источник потока данных с помощью компонента скрипта.</span><span class="sxs-lookup"><span data-stu-id="4872c-112">Explains and demonstrates how to create a data flow source by using the Script component.</span></span>  
  
 [<span data-ttu-id="4872c-113">Создание синхронного преобразования с помощью компонента скрипта</span><span class="sxs-lookup"><span data-stu-id="4872c-113">Creating a Synchronous Transformation with the Script Component</span></span>](creating-a-synchronous-transformation-with-the-script-component.md)  
 <span data-ttu-id="4872c-114">Поясняет и демонстрирует, как создать преобразование потока данных с синхронными выходами с помощью компонента скрипта.</span><span class="sxs-lookup"><span data-stu-id="4872c-114">Explains and demonstrates how to create a data flow transformation with synchronous outputs by using the Script component.</span></span> <span data-ttu-id="4872c-115">При подобном преобразовании строки данных изменяются на месте по мере их обработки компонентом.</span><span class="sxs-lookup"><span data-stu-id="4872c-115">This kind of transformation modifies rows of data in place as they pass through the component.</span></span>  
  
 [<span data-ttu-id="4872c-116">Создание асинхронного преобразования с помощью компонента скрипта</span><span class="sxs-lookup"><span data-stu-id="4872c-116">Creating an Asynchronous Transformation with the Script Component</span></span>](../extending-packages-scripting-data-flow-script-component-types/creating-an-asynchronous-transformation-with-the-script-component.md)  
 <span data-ttu-id="4872c-117">Поясняет и демонстрирует, как создать преобразование потока данных с асинхронными выходами с помощью компонента скрипта.</span><span class="sxs-lookup"><span data-stu-id="4872c-117">Explains and demonstrates how to create a data flow transformation with asynchronous outputs by using the Script component.</span></span> <span data-ttu-id="4872c-118">При таком преобразовании необходимо считать все строки данных, прежде чем добавить к данным, обрабатываемым компонентом, дополнительные сведения, например, вычисляемое статистическое выражение.</span><span class="sxs-lookup"><span data-stu-id="4872c-118">This kind of transformation has to read all rows of data before it can add more information, such as calculated aggregates, to the data that passes through the component.</span></span>  
  
 [<span data-ttu-id="4872c-119">Создание назначения с помощью компонента скрипта</span><span class="sxs-lookup"><span data-stu-id="4872c-119">Creating a Destination with the Script Component</span></span>](../extending-packages-scripting-data-flow-script-component-types/creating-a-destination-with-the-script-component.md)  
 <span data-ttu-id="4872c-120">Поясняет и демонстрирует, как создать назначение потока данных с помощью компонента скрипта.</span><span class="sxs-lookup"><span data-stu-id="4872c-120">Explains and demonstrates how to create a data flow destination by using the Script component.</span></span>  
  
<span data-ttu-id="4872c-121">![Значок Integration Services (маленький)](../media/dts-16.gif "Значок служб Integration Services (маленький)")  **следит за обновлениями Integration Services**</span><span class="sxs-lookup"><span data-stu-id="4872c-121">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="4872c-122">Чтобы загрузить новейшую документацию, статьи, образцы и видеоматериалы корпорации Майкрософт, а также лучшие решения участников сообщества, посетите страницу служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] на сайте MSDN:</span><span class="sxs-lookup"><span data-stu-id="4872c-122">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="4872c-123">Посетить страницу «Службы Integration Services» на сайте MSDN</span><span class="sxs-lookup"><span data-stu-id="4872c-123">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="4872c-124">Чтобы получать автоматические уведомления об этих обновлениях, подпишитесь на RSS-каналы, предлагаемые на этой странице.</span><span class="sxs-lookup"><span data-stu-id="4872c-124">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4872c-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="4872c-125">See Also</span></span>  
 <span data-ttu-id="4872c-126">[Сравнение решений со скриптами и пользовательских объектов](../extending-packages-scripting/comparing-scripting-solutions-and-custom-objects.md) </span><span class="sxs-lookup"><span data-stu-id="4872c-126">[Comparing Scripting Solutions and Custom Objects](../extending-packages-scripting/comparing-scripting-solutions-and-custom-objects.md) </span></span>  
 [<span data-ttu-id="4872c-127">Разработка компонентов потока данных определенных типов</span><span class="sxs-lookup"><span data-stu-id="4872c-127">Developing Specific Types of Data Flow Components</span></span>](../extending-packages-custom-objects-data-flow-types/developing-specific-types-of-data-flow-components.md)  
  
  
