---
title: Разработка компонентов потока данных определенных типов | Документы Майкрософт
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
- data flow task [Integration Services], components
- components [Integration Services], data flow
- data flow [Integration Services], components
ms.assetid: 348e219a-b8ff-425e-b9c6-811880101c54
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 3e168c866e03bfa5fd1f32127e4bfd6e58a2e8d5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87736602"
---
# <a name="developing-specific-types-of-data-flow-components"></a><span data-ttu-id="cd189-102">Разработка компонентов потока данных определенных типов</span><span class="sxs-lookup"><span data-stu-id="cd189-102">Developing Specific Types of Data Flow Components</span></span>
  <span data-ttu-id="cd189-103">Этот раздел описывает специфические особенности разработки компонентов источника, компонентов преобразования с синхронными выходами компонентов преобразования с асинхронными выходами и компоненты назначения.</span><span class="sxs-lookup"><span data-stu-id="cd189-103">This section covers the specifics of developing source components, transformation components with synchronous outputs, transformation components with asynchronous outputs, and destination components.</span></span>  
  
 <span data-ttu-id="cd189-104">Общие сведения о разработке компонентов см. в разделе [Разработка пользовательского компонента потока данных](../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="cd189-104">For information about component development in general, see [Developing a Custom Data Flow Component](../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cd189-105">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="cd189-105">In This Section</span></span>  
 [<span data-ttu-id="cd189-106">Разработка пользовательского компонента источника</span><span class="sxs-lookup"><span data-stu-id="cd189-106">Developing a Custom Source Component</span></span>](../extending-packages-custom-objects-data-flow-types/developing-a-custom-source-component.md)  
 <span data-ttu-id="cd189-107">Содержит сведения о разработке компонента, осуществляющего доступ к данным внешнего источника данных и поставляющего их компонентам, расположенным ниже в потоке данных.</span><span class="sxs-lookup"><span data-stu-id="cd189-107">Contains information on developing a component that accesses data from an external data source and supplies it to downstream components in the data flow.</span></span>  
  
 [<span data-ttu-id="cd189-108">Разработка пользовательского компонента преобразования с синхронными выходами</span><span class="sxs-lookup"><span data-stu-id="cd189-108">Developing a Custom Transformation Component with Synchronous Outputs</span></span>](../extending-packages-custom-objects-data-flow-types/developing-a-custom-transformation-component-with-synchronous-outputs.md)  
 <span data-ttu-id="cd189-109">Содержит сведения о разработке компонента преобразования, выходы которого синхронизированы с входами.</span><span class="sxs-lookup"><span data-stu-id="cd189-109">Contains information on developing a transformation component whose outputs are synchronous to its inputs.</span></span> <span data-ttu-id="cd189-110">Эти компоненты не добавляют данные в поток данных, но обрабатывают проходящие через них данные.</span><span class="sxs-lookup"><span data-stu-id="cd189-110">These components do not add data to the data flow, but process data as it passes through.</span></span>  
  
 [<span data-ttu-id="cd189-111">Разработка пользовательского компонента преобразования с асинхронными выходами</span><span class="sxs-lookup"><span data-stu-id="cd189-111">Developing a Custom Transformation Component with Asynchronous Outputs</span></span>](../extending-packages-custom-objects-data-flow-types/developing-a-custom-transformation-component-with-asynchronous-outputs.md)  
 <span data-ttu-id="cd189-112">Содержит сведения о разработке компонента преобразования, выходы которого не синхронизированы с входами.</span><span class="sxs-lookup"><span data-stu-id="cd189-112">Contains information on developing a transformation component whose outputs are not synchronous to its inputs.</span></span> <span data-ttu-id="cd189-113">Эти компоненты получают данные от вышестоящих компонентов, а также добавляют данные в поток.</span><span class="sxs-lookup"><span data-stu-id="cd189-113">These components receive data from upstream components, but also add data to the dataflow.</span></span>  
  
 [<span data-ttu-id="cd189-114">Разработка пользовательского компонента назначения</span><span class="sxs-lookup"><span data-stu-id="cd189-114">Developing a Custom Destination Component</span></span>](../extending-packages-custom-objects-data-flow-types/developing-a-custom-destination-component.md)  
 <span data-ttu-id="cd189-115">Содержит сведения о разработке компонента, получающего строки от вышестоящих компонентов в потоке данных и записывающего их во внешний источник данных.</span><span class="sxs-lookup"><span data-stu-id="cd189-115">Contains information on developing a component that receives rows from upstream components in the data flow and writes them to an external data source.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="cd189-116">Справочник</span><span class="sxs-lookup"><span data-stu-id="cd189-116">Reference</span></span>  
 <xref:Microsoft.SqlServer.Dts.Pipeline>  
 <span data-ttu-id="cd189-117">Содержит классы и интерфейсы, используемые для создания пользовательских компонентов потока данных.</span><span class="sxs-lookup"><span data-stu-id="cd189-117">Contains the classes and interfaces used to create custom data flow components.</span></span>  
  
 <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper>  
 <span data-ttu-id="cd189-118">Содержит неуправляемые классы и интерфейсы задачи потока данных.</span><span class="sxs-lookup"><span data-stu-id="cd189-118">Contains the unmanaged classes and interfaces of the data flow task.</span></span> <span data-ttu-id="cd189-119">Разработчик использует их и управляемое пространство имен <xref:Microsoft.SqlServer.Dts.Pipeline> при программном построении потока данных или создании пользовательских компонентов потока данных.</span><span class="sxs-lookup"><span data-stu-id="cd189-119">The developer uses these, and the managed <xref:Microsoft.SqlServer.Dts.Pipeline> namespace, when building a data flow programmatically or creating custom data flow components.</span></span>  
  
<span data-ttu-id="cd189-120">![Значок Integration Services (маленький)](../media/dts-16.gif "Значок служб Integration Services (маленький)")  **следит за обновлениями Integration Services**</span><span class="sxs-lookup"><span data-stu-id="cd189-120">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="cd189-121">Чтобы загрузить новейшую документацию, статьи, образцы и видеоматериалы корпорации Майкрософт, а также лучшие решения участников сообщества, посетите страницу служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] на сайте MSDN:</span><span class="sxs-lookup"><span data-stu-id="cd189-121">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="cd189-122">Посетить страницу «Службы Integration Services» на сайте MSDN</span><span class="sxs-lookup"><span data-stu-id="cd189-122">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="cd189-123">Чтобы получать автоматические уведомления об этих обновлениях, подпишитесь на RSS-каналы, предлагаемые на этой странице.</span><span class="sxs-lookup"><span data-stu-id="cd189-123">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd189-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="cd189-124">See Also</span></span>  
 <span data-ttu-id="cd189-125">[Сравнение решений со скриптами и пользовательских объектов](../extending-packages-scripting/comparing-scripting-solutions-and-custom-objects.md) </span><span class="sxs-lookup"><span data-stu-id="cd189-125">[Comparing Scripting Solutions and Custom Objects](../extending-packages-scripting/comparing-scripting-solutions-and-custom-objects.md) </span></span>  
 [<span data-ttu-id="cd189-126">Разработка компонентов скрипта определенных типов</span><span class="sxs-lookup"><span data-stu-id="cd189-126">Developing Specific Types of Script Components</span></span>](../extending-packages-scripting-data-flow-script-component-types/developing-specific-types-of-script-components.md)  
  
  
