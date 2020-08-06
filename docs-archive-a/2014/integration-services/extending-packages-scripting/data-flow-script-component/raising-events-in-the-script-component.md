---
title: Вызов событий в компоненте скрипта | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- Script component [Integration Services], raising events
ms.assetid: bb389073-e1d0-4794-8d29-c8b293b6a5e3
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 78eb44239f4e58e43bdd65c41d5fdeb58d053a6c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665424"
---
# <a name="raising-events-in-the-script-component"></a><span data-ttu-id="ba48e-102">Вызов событий в компоненте скрипта</span><span class="sxs-lookup"><span data-stu-id="ba48e-102">Raising Events in the Script Component</span></span>
  <span data-ttu-id="ba48e-103">События позволяют сообщать об ошибках и предупреждениях, а также передавать другие сведения, например о ходе выполнения задачи или ее состоянии, в пакет, содержащий задачу.</span><span class="sxs-lookup"><span data-stu-id="ba48e-103">Events provide a way to report errors, warnings, and other information, such as task progress or status, to the containing package.</span></span> <span data-ttu-id="ba48e-104">Пакет предоставляет обработчики событий для управления уведомлениями о событиях.</span><span class="sxs-lookup"><span data-stu-id="ba48e-104">The package provides event handlers for managing event notifications.</span></span> <span data-ttu-id="ba48e-105">Компонент скрипта может формировать события путем вызова методов свойства <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.ComponentMetaData%2A> класса `ScriptMain`.</span><span class="sxs-lookup"><span data-stu-id="ba48e-105">The Script component can raise events by calling methods on the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.ComponentMetaData%2A> property of the `ScriptMain` class.</span></span> <span data-ttu-id="ba48e-106">Дополнительные сведения о том, как пакеты службы [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] обрабатывают события, см. в разделе [Обработчики событий в службах Integration Services (SSIS)](../../integration-services-ssis-event-handlers.md).</span><span class="sxs-lookup"><span data-stu-id="ba48e-106">For more information about how [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] packages handle events, see [Integration Services &#40;SSIS&#41; Event Handlers](../../integration-services-ssis-event-handlers.md).</span></span>  
  
 <span data-ttu-id="ba48e-107">События могут регистрироваться любым регистратором, включенным в пакете.</span><span class="sxs-lookup"><span data-stu-id="ba48e-107">Events can be logged to any log provider that is enabled in the package.</span></span> <span data-ttu-id="ba48e-108">Регистраторы сохраняют сведения о событиях в хранилище данных.</span><span class="sxs-lookup"><span data-stu-id="ba48e-108">Log providers store information about events in a data store.</span></span> <span data-ttu-id="ba48e-109">Компонент скрипта также может использовать метод <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.Log%2A> для записи данных в регистратор, не формируя событий.</span><span class="sxs-lookup"><span data-stu-id="ba48e-109">The Script component can also use the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.Log%2A> method to log information to a log provider without raising an event.</span></span> <span data-ttu-id="ba48e-110">Дополнительные сведения об использовании метода <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.Log%2A> см. в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="ba48e-110">For more information about how to use the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.Log%2A> method, see the following section.</span></span>  
  
 <span data-ttu-id="ba48e-111">Для формирования события задача «Скрипт» вызывает один из следующих методов интерфейса <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> свойства <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.ComponentMetaData%2A>:</span><span class="sxs-lookup"><span data-stu-id="ba48e-111">To raise an event, the Script task calls one of the following methods of the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> interface exposed by the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.ComponentMetaData%2A> property:</span></span>  
  
|<span data-ttu-id="ba48e-112">Событие</span><span class="sxs-lookup"><span data-stu-id="ba48e-112">Event</span></span>|<span data-ttu-id="ba48e-113">Description</span><span class="sxs-lookup"><span data-stu-id="ba48e-113">Description</span></span>|  
|-----------|-----------------|  
|<xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireCustomEvent%2A>|<span data-ttu-id="ba48e-114">Вызывает в пакете определяемое пользователем событие.</span><span class="sxs-lookup"><span data-stu-id="ba48e-114">Raises a user-defined custom event in the package.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireError%2A>|<span data-ttu-id="ba48e-115">Извещает пакет об ошибке.</span><span class="sxs-lookup"><span data-stu-id="ba48e-115">Informs the package of an error condition.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireInformation%2A>|<span data-ttu-id="ba48e-116">Передает сведения пользователю.</span><span class="sxs-lookup"><span data-stu-id="ba48e-116">Provides information to the user.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireProgress%2A>|<span data-ttu-id="ba48e-117">Информирует пакет о ходе выполнения компонента.</span><span class="sxs-lookup"><span data-stu-id="ba48e-117">Informs the package of the progress of the component.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireWarning%2A>|<span data-ttu-id="ba48e-118">Информирует пакет о том, что компонент находится в состоянии, требующем уведомления пользователя, но не являющемся ошибкой.</span><span class="sxs-lookup"><span data-stu-id="ba48e-118">Informs the package that the component is in a state that warrants user notification, but is not an error condition.</span></span>|  
  
 <span data-ttu-id="ba48e-119">Ниже приведен простой пример формирования события ошибки:</span><span class="sxs-lookup"><span data-stu-id="ba48e-119">Here is a simple example of raising an Error event:</span></span>  
  
 `Dim myMetadata as IDTSComponentMetaData100`  
  
 `myMetaData = Me.ComponentMetaData`  
  
 `myMetaData.FireError(...)`  
  
<span data-ttu-id="ba48e-120">![Значок Integration Services (маленький)](../../media/dts-16.gif "Значок служб Integration Services (маленький)")  **следит за обновлениями Integration Services**</span><span class="sxs-lookup"><span data-stu-id="ba48e-120">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="ba48e-121">Чтобы загрузить новейшую документацию, статьи, образцы и видеоматериалы корпорации Майкрософт, а также лучшие решения участников сообщества, посетите страницу служб [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] на сайте MSDN:</span><span class="sxs-lookup"><span data-stu-id="ba48e-121">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="ba48e-122">Посетить страницу «Службы Integration Services» на сайте MSDN</span><span class="sxs-lookup"><span data-stu-id="ba48e-122">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="ba48e-123">Чтобы получать автоматические уведомления об этих обновлениях, подпишитесь на RSS-каналы, предлагаемые на этой странице.</span><span class="sxs-lookup"><span data-stu-id="ba48e-123">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba48e-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="ba48e-124">See Also</span></span>  
 <span data-ttu-id="ba48e-125">[Обработчики событий в службах Integration Services (SSIS)](../../integration-services-ssis-event-handlers.md) </span><span class="sxs-lookup"><span data-stu-id="ba48e-125">[Integration Services &#40;SSIS&#41; Event Handlers](../../integration-services-ssis-event-handlers.md) </span></span>  
 [<span data-ttu-id="ba48e-126">Добавление обработчика событий к пакету</span><span class="sxs-lookup"><span data-stu-id="ba48e-126">Add an Event Handler to a Package</span></span>](../../add-an-event-handler-to-a-package.md)  
  
  
