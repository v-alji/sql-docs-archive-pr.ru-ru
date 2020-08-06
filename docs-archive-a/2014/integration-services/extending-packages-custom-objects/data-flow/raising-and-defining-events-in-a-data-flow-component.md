---
title: Вызов и определение событий в компоненте потока данных | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- data flow components [Integration Services], events
- events [Integration Services], custom
- custom events [Integration Services]
- custom data flow components [Integration Services], events
- events [Integration Services], raising
- predefined events [Integration Services]
ms.assetid: 1d8c5358-9384-47a8-b7cb-7b0650384119
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 25f4572f8a8af829145da4e4d685f5dddad4a29a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729642"
---
# <a name="raising-and-defining-events-in-a-data-flow-component"></a><span data-ttu-id="8e22b-102">Вызов и определение событий в компоненте потока данных</span><span class="sxs-lookup"><span data-stu-id="8e22b-102">Raising and Defining Events in a Data Flow Component</span></span>
  <span data-ttu-id="8e22b-103">Разработчики компонентов могут создавать подмножество событий, определенных в интерфейсе <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents>, вызывая методы, доступ к которым определяется свойством <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ComponentMetaData%2A>.</span><span class="sxs-lookup"><span data-stu-id="8e22b-103">Component developers can raise a subset of the events defined in the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents> interface by calling the methods exposed on the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ComponentMetaData%2A> property.</span></span> <span data-ttu-id="8e22b-104">Можно также определять пользовательские события, используя коллекцию <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.EventInfos%2A>, и создавать эти события с помощью метода <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireCustomEvent%2A>.</span><span class="sxs-lookup"><span data-stu-id="8e22b-104">You can also define custom events by using the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.EventInfos%2A> collection, and raise them during execution by using the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireCustomEvent%2A> method.</span></span> <span data-ttu-id="8e22b-105">В данном разделе описывается разработка и вызов событий, а также содержатся рекомендации по вызову событий во время разработки.</span><span class="sxs-lookup"><span data-stu-id="8e22b-105">This section describes how to create and raise an event, and provides guidelines on when you should raise events at design time.</span></span>

## <a name="raising-events"></a><span data-ttu-id="8e22b-106">Вызов событий</span><span class="sxs-lookup"><span data-stu-id="8e22b-106">Raising Events</span></span>
 <span data-ttu-id="8e22b-107">Компоненты вызывают события с помощью методов **Fire\<X>** интерфейса <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100>.</span><span class="sxs-lookup"><span data-stu-id="8e22b-107">Components raise events by using the **Fire\<X>** methods of the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> interface.</span></span> <span data-ttu-id="8e22b-108">События можно вызывать во время разработки и во время выполнения компонента.</span><span class="sxs-lookup"><span data-stu-id="8e22b-108">You can raise events during component design and execution.</span></span> <span data-ttu-id="8e22b-109">Обычно во время разработки методы <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireError%2A> и <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireWarning%2A> вызываются в процессе проверки компонента.</span><span class="sxs-lookup"><span data-stu-id="8e22b-109">Typically, during component design, the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireError%2A> and <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireWarning%2A> methods are called during validation.</span></span> <span data-ttu-id="8e22b-110">Эти события выводят сообщения на панели **Список ошибок** среды [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)] и обеспечивают отзыв для пользователей компонента в случаях, когда он неправильно настроен.</span><span class="sxs-lookup"><span data-stu-id="8e22b-110">These events display messages in the **Error List** pane of [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)] and provide feedback to users of the component when a component is incorrectly configured.</span></span>

 <span data-ttu-id="8e22b-111">Компоненты могут также вызывать события в любой момент во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="8e22b-111">Components can also raise events at any point during execution.</span></span> <span data-ttu-id="8e22b-112">События позволяют разработчикам компонента предоставлять отзыв пользователям компонента в процессе его работы.</span><span class="sxs-lookup"><span data-stu-id="8e22b-112">Events allow component developers to provide feedback to users of the component as it executes.</span></span> <span data-ttu-id="8e22b-113">Вызов метода <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireError%2A> во время выполнения, скорее всего, приведет к аварийному завершению работы всего пакета.</span><span class="sxs-lookup"><span data-stu-id="8e22b-113">Calling the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireError%2A> method during execution is likely to fail the package.</span></span>

## <a name="defining-and-raising-custom-events"></a><span data-ttu-id="8e22b-114">Определение и вызов пользовательских событий</span><span class="sxs-lookup"><span data-stu-id="8e22b-114">Defining and Raising Custom Events</span></span>

### <a name="defining-a-custom-event"></a><span data-ttu-id="8e22b-115">Разработка пользовательского события</span><span class="sxs-lookup"><span data-stu-id="8e22b-115">Defining a Custom Event</span></span>
 <span data-ttu-id="8e22b-116">Пользовательские события создаются с помощью метода <xref:Microsoft.SqlServer.Dts.Runtime.Wrapper.IDTSEventInfos100.Add%2A> коллекции <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.EventInfos%2A>.</span><span class="sxs-lookup"><span data-stu-id="8e22b-116">Custom events are created by calling the <xref:Microsoft.SqlServer.Dts.Runtime.Wrapper.IDTSEventInfos100.Add%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.EventInfos%2A> collection.</span></span> <span data-ttu-id="8e22b-117">Эта коллекция создается задачей потока данных и предоставляется разработчику компонента как свойство через базовый класс <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent>.</span><span class="sxs-lookup"><span data-stu-id="8e22b-117">This collection is set by the data flow task and provided as a property to the component developer through the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent> base class.</span></span> <span data-ttu-id="8e22b-118">Этот класс содержит пользовательские события, определенные задачей потока данных, и пользовательские события, определенные компонентом с помощью вызова метода <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.RegisterEvents%2A>.</span><span class="sxs-lookup"><span data-stu-id="8e22b-118">This class contains custom events defined by the data flow task and custom events defined by the component during the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.RegisterEvents%2A> method.</span></span>

 <span data-ttu-id="8e22b-119">Пользовательские события компонента не сохраняются в коде XML пакета.</span><span class="sxs-lookup"><span data-stu-id="8e22b-119">The custom events of a component are not persisted in the package XML.</span></span> <span data-ttu-id="8e22b-120">Поэтому метод <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.RegisterEvents%2A> вызывается и во время разработки, и во время выполнения, чтобы компонент мог определить события, которые вызывает.</span><span class="sxs-lookup"><span data-stu-id="8e22b-120">Therefore, the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.RegisterEvents%2A> method is called during both design and execution to allow the component to define the events it raises.</span></span>

 <span data-ttu-id="8e22b-121">Параметр *allowEventHandlers* метода <xref:Microsoft.SqlServer.Dts.Runtime.Wrapper.IDTSEventInfos100.Add%2A> указывает, позволяет ли компонент создавать для этого события объекты <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="8e22b-121">The *allowEventHandlers* parameter of the <xref:Microsoft.SqlServer.Dts.Runtime.Wrapper.IDTSEventInfos100.Add%2A> method specifies whether the component allows <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler> objects to be created for the event.</span></span> <span data-ttu-id="8e22b-122">Следует заметить, что объекты <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandlers> являются синхронными.</span><span class="sxs-lookup"><span data-stu-id="8e22b-122">Note that <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandlers> are synchronous.</span></span> <span data-ttu-id="8e22b-123">Поэтому компонент не возобновляет выполнение, пока объект <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler>, принадлежащий пользовательскому событию, не закончил работу.</span><span class="sxs-lookup"><span data-stu-id="8e22b-123">Therefore the component does not resume execution until an <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler> attached to the custom event has finished executing.</span></span> <span data-ttu-id="8e22b-124">Если параметр *allowEventHandlers* имеет значение `true` , каждый параметр события автоматически становится доступным для всех <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler> объектов через переменные, создаваемые и заполняемые автоматически [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] средой выполнения.</span><span class="sxs-lookup"><span data-stu-id="8e22b-124">If the *allowEventHandlers* parameter is `true`, each parameter of the event is automatically made available to any <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler> objects through variables that are created and populated automatically by the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] runtime.</span></span>

### <a name="raising-a-custom-event"></a><span data-ttu-id="8e22b-125">Вызов пользовательского события</span><span class="sxs-lookup"><span data-stu-id="8e22b-125">Raising a Custom Event</span></span>
 <span data-ttu-id="8e22b-126">Компоненты вызывают пользовательские события с помощью метода <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireCustomEvent%2A>, передавая ему имя, текст и параметры события.</span><span class="sxs-lookup"><span data-stu-id="8e22b-126">Components raise custom events by calling the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireCustomEvent%2A> method, and providing the name, text, and parameters of the event.</span></span> <span data-ttu-id="8e22b-127">Если параметр *allowEventHandlers* имеет значение `true` , то все <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandlers> , что создается для пользовательского события, выполняется [!INCLUDE[ssIS](../../../includes/ssis-md.md)] подсистемой среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="8e22b-127">If the *allowEventHandlers* parameter is `true`, any <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandlers> that are created for the custom event are executed by the [!INCLUDE[ssIS](../../../includes/ssis-md.md)] run-time engine.</span></span>

### <a name="custom-event-sample"></a><span data-ttu-id="8e22b-128">Образец пользовательского события</span><span class="sxs-lookup"><span data-stu-id="8e22b-128">Custom Event Sample</span></span>
 <span data-ttu-id="8e22b-129">Следующий пример кода демонстрирует компонент, который определяет пользовательское событие с помощью метода <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.RegisterEvents%2A>, а затем вызывает это событие во время выполнения с помощью метода <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireCustomEvent%2A>.</span><span class="sxs-lookup"><span data-stu-id="8e22b-129">The following code example shows a component that defines a custom event during the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.RegisterEvents%2A> method, and then raises the event at run time by calling the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireCustomEvent%2A> method.</span></span>

```csharp
public override void RegisterEvents()
{
    string [] parameterNames = new string[2]{"RowCount", "StartTime"};
    ushort [] parameterTypes = new ushort[2]{ DtsConvert.VarTypeFromTypeCode(TypeCode.Int32), DtsConvert.VarTypeFromTypeCode(TypeCode.DateTime)};
    string [] parameterDescriptions = new string[2]{"The number of rows to sort.", "The start time of the Sort operation."};
    EventInfos.Add("StartingSort","Fires when the component begins sorting the rows.",false,ref parameterNames, ref parameterTypes, ref parameterDescriptions);
}
public override void ProcessInput(int inputID, PipelineBuffer buffer)
{
    while (buffer.NextRow())
    {
       // Process buffer rows.
    }

    IDTSEventInfo100 eventInfo = EventInfos["StartingSort"];
    object []arguments = new object[2]{buffer.RowCount, DateTime.Now };
    ComponentMetaData.FireCustomEvent("StartingSort", "Beginning sort operation.", ref arguments, ComponentMetaData.Name, ref FireSortEventAgain);
}
```

```vb
Public  Overrides Sub RegisterEvents() 
  Dim parameterNames As String() = New String(2) {"RowCount", "StartTime"} 
  Dim parameterTypes As System.UInt16() = New System.UInt16(2) {DtsConvert.VarTypeFromTypeCode(TypeCode.Int32), DtsConvert.VarTypeFromTypeCode(TypeCode.DateTime)} 
  Dim parameterDescriptions As String() = New String(2) {"The number of rows to sort.", "The start time of the Sort operation."} 
  EventInfos.Add("StartingSort", "Fires when the component begins sorting the rows.", False, parameterNames, parameterTypes, parameterDescriptions) 
End Sub 

Public  Overrides Sub ProcessInput(ByVal inputID As Integer, ByVal buffer As PipelineBuffer) 
  While buffer.NextRow 
  End While 
  Dim eventInfo As IDTSEventInfo100 = EventInfos("StartingSort") 
  Dim arguments As Object() = New Object(2) {buffer.RowCount, DateTime.Now} 
  ComponentMetaData.FireCustomEvent("StartingSort", _
    "Beginning sort operation.", arguments, _
    ComponentMetaData.Name, FireSortEventAgain) 
End Sub
```

<span data-ttu-id="8e22b-130">![Значок Integration Services (маленький)](../../media/dts-16.gif "Значок служб Integration Services (маленький)")  **следит за обновлениями Integration Services**</span><span class="sxs-lookup"><span data-stu-id="8e22b-130">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="8e22b-131">Чтобы загрузить новейшую документацию, статьи, образцы и видеоматериалы корпорации Майкрософт, а также лучшие решения участников сообщества, посетите страницу служб [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] на сайте MSDN:</span><span class="sxs-lookup"><span data-stu-id="8e22b-131">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="8e22b-132">Посетить страницу «Службы Integration Services» на сайте MSDN</span><span class="sxs-lookup"><span data-stu-id="8e22b-132">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="8e22b-133">Чтобы получать автоматические уведомления об этих обновлениях, подпишитесь на RSS-каналы, предлагаемые на этой странице.</span><span class="sxs-lookup"><span data-stu-id="8e22b-133">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="8e22b-134">См. также:</span><span class="sxs-lookup"><span data-stu-id="8e22b-134">See Also</span></span>
 <span data-ttu-id="8e22b-135">[Integration Services &#40;служб SSIS&#41; обработчики событий](../../integration-services-ssis-event-handlers.md) [Добавление обработчика событий в пакет](../../add-an-event-handler-to-a-package.md)</span><span class="sxs-lookup"><span data-stu-id="8e22b-135">[Integration Services &#40;SSIS&#41; Event Handlers](../../integration-services-ssis-event-handlers.md) [Add an Event Handler to a Package](../../add-an-event-handler-to-a-package.md)</span></span>


