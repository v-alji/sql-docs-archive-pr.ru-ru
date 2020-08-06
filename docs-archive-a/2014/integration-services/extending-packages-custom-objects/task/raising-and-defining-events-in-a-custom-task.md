---
title: Вызов и определение событий в пользовательской задаче | Документы Майкрософт
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
- SSIS events, custom
- status information [SQL Server], task events
- custom tasks [Integration Services], events
- SSIS custom tasks, events
- IDTSComponentEvents interface
- events [Integration Services], custom
- events [Integration Services], runtime
- custom events [Integration Services]
- SSIS events, runtime
- IDTSEvents interface
ms.assetid: e0898aa1-e90c-4c4e-99d4-708a76efddfd
author: chugugrace
ms.author: chugu
ms.openlocfilehash: cb41ee60543a05b6cf10b3acda43372e20288d13
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666175"
---
# <a name="raising-and-defining-events-in-a-custom-task"></a><span data-ttu-id="069fa-102">Вызов и определение событий в пользовательской задаче</span><span class="sxs-lookup"><span data-stu-id="069fa-102">Raising and Defining Events in a Custom Task</span></span>
  <span data-ttu-id="069fa-103">Обработчиком среды выполнения служб [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] предоставляется коллекция событий, обозначающих состояние обработки задачи в ходе ее проверки и выполнения.</span><span class="sxs-lookup"><span data-stu-id="069fa-103">The [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] run-time engine provides a collection of events that provide status on the progress of a task as the task is validated and executed.</span></span> <span data-ttu-id="069fa-104">Интерфейс <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents> определяет эти события. Он передается задачам в качестве параметра методов <xref:Microsoft.SqlServer.Dts.Runtime.Executable.Validate%2A> и <xref:Microsoft.SqlServer.Dts.Runtime.Executable.Execute%2A>.</span><span class="sxs-lookup"><span data-stu-id="069fa-104">The <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents> interface defines these events, and is provided to tasks as a parameter to the <xref:Microsoft.SqlServer.Dts.Runtime.Executable.Validate%2A> and <xref:Microsoft.SqlServer.Dts.Runtime.Executable.Execute%2A> methods.</span></span>  
  
 <span data-ttu-id="069fa-105">Имеется также другой набор событий, определяемых интерфейсом <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents>, которые вызываются от имени задачи сервером задач <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>.</span><span class="sxs-lookup"><span data-stu-id="069fa-105">There is another set of events, which are defined in the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents> interface, that are raised on behalf of the task by the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>.</span></span> <span data-ttu-id="069fa-106">Сервер задач <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> вызывает события, происходящие до и после проверки и выполнения, а задача вызывает события, происходящие непосредственно во время выполнения и проверки.</span><span class="sxs-lookup"><span data-stu-id="069fa-106">The <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> raises events that occur before and after validation and execution, whereas the task raises the events that occur during execution and validation.</span></span>  
  
## <a name="creating-custom-events"></a><span data-ttu-id="069fa-107">Создание пользовательских событий</span><span class="sxs-lookup"><span data-stu-id="069fa-107">Creating Custom Events</span></span>  
 <span data-ttu-id="069fa-108">Разработчики пользовательских задач могут определять новые пользовательские события, создавая новый объект <xref:Microsoft.SqlServer.Dts.Runtime.EventInfo> в своей переопределенной реализации метода <xref:Microsoft.SqlServer.Dts.Runtime.Task.InitializeTask%2A>.</span><span class="sxs-lookup"><span data-stu-id="069fa-108">Custom task developers can define new, custom events by creating a new <xref:Microsoft.SqlServer.Dts.Runtime.EventInfo> in their overridden implementation of the <xref:Microsoft.SqlServer.Dts.Runtime.Task.InitializeTask%2A> method.</span></span> <span data-ttu-id="069fa-109">После создания объект <xref:Microsoft.SqlServer.Dts.Runtime.EventInfo> добавляется в коллекцию `EventInfos` с помощью метода <xref:Microsoft.SqlServer.Dts.Runtime.EventInfos.Add%2A>.</span><span class="sxs-lookup"><span data-stu-id="069fa-109">After the <xref:Microsoft.SqlServer.Dts.Runtime.EventInfo> is created, it is added to the `EventInfos` collection by using the <xref:Microsoft.SqlServer.Dts.Runtime.EventInfos.Add%2A> method.</span></span> <span data-ttu-id="069fa-110">Подпись метода <xref:Microsoft.SqlServer.Dts.Runtime.EventInfos.Add%2A> выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="069fa-110">The method signature of the <xref:Microsoft.SqlServer.Dts.Runtime.EventInfos.Add%2A> method is as follows:</span></span>  
  
 `public void Add(string eventName, string description, bool allowEventHandlers, string[] parameterNames, TypeCode[] parameterTypes, string[] parameterDescriptions);`  
  
 <span data-ttu-id="069fa-111">В следующем образце кода демонстрируется метод `InitializeTask` пользовательской задачи при создании двух пользовательских событий и указании их свойств.</span><span class="sxs-lookup"><span data-stu-id="069fa-111">The following code sample shows the `InitializeTask` method of a custom task, where two custom events are created and their properties are set.</span></span> <span data-ttu-id="069fa-112">Затем новые события добавляются в коллекцию <xref:Microsoft.SqlServer.Dts.Runtime.EventInfos>.</span><span class="sxs-lookup"><span data-stu-id="069fa-112">The new events are then added to the <xref:Microsoft.SqlServer.Dts.Runtime.EventInfos> collection.</span></span>  
  
 <span data-ttu-id="069fa-113">Первому событию присваивается имя *eventName* "**OnBeforeIncrement**" и описание *description* "**Fires after the initial value is updated**". (Срабатывает после обновления исходного значения.)</span><span class="sxs-lookup"><span data-stu-id="069fa-113">The first custom event has an *eventName* of "**OnBeforeIncrement**" and *description* of "**Fires after the initial value is updated.**"</span></span> <span data-ttu-id="069fa-114">Следующий параметр, имеющий значение `true`, указывает, что для обработки этого события разрешено создание контейнера обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="069fa-114">The next parameter, the `true` value, indicates that this event should allow an event handler container to be created to handle the event.</span></span> <span data-ttu-id="069fa-115">Обработчик событий представляет собой контейнер, обеспечивающий структуру пакета и службы для задач, как и другие контейнеры, например, пакет, Sequence, ForLoop и ForEachLoop.</span><span class="sxs-lookup"><span data-stu-id="069fa-115">The event handler is a container that provides structure in a package and services to tasks, like other containers such as the package, Sequence, ForLoop, and ForEachLoop.</span></span> <span data-ttu-id="069fa-116">Если параметр *allowEventHandlers* имеет значение `true` , <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler> для события создаются объекты.</span><span class="sxs-lookup"><span data-stu-id="069fa-116">When the *allowEventHandlers* parameter is `true`, <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler> objects are created for the event.</span></span> <span data-ttu-id="069fa-117">Любые параметры, определенные для события, становятся доступными для <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler> в его коллекции <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="069fa-117">Any parameters that were defined for the event are now available to the <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler> in the variables collection of the <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler>.</span></span>  
  
```csharp  
public override void InitializeTask(Connections connections,  
   VariableDispenser variables, IDTSInfoEvents events,  
   IDTSLogging log, EventInfos eventInfos,  
   LogEntryInfos logEntryInfos, ObjectReferenceTracker refTracker)  
{  
    this.eventInfos = eventInfos;  
    string[] paramNames = new string[1];  
    TypeCode[] paramTypes = new TypeCode[1]{TypeCode.Int32};  
    string[] paramDescriptions = new string[1];  
  
    paramNames[0] = "InitialValue";  
    paramDescriptions[0] = "The value before it is incremented.";  
  
    this.eventInfos.Add("OnBeforeIncrement",   
      "Fires before the task increments the value.",  
      true,paramNames,paramTypes,paramDescriptions);  
    this.onBeforeIncrement = this.eventInfos["OnBeforeIncrement"];  
  
    paramDescriptions[0] = "The value after it has been incremented.";  
    this.eventInfos.Add("OnAfterIncrement",  
      "Fires after the initial value is updated.",  
      true,paramNames, paramTypes,paramDescriptions);  
    this.onAfterIncrement = this.eventInfos["OnAfterIncrement"];  
}  
```  
  
```vb  
Public Overrides Sub InitializeTask(ByVal connections As Connections, _  
ByVal variables As VariableDispenser, ByVal events As IDTSInfoEvents, _  
ByVal log As IDTSLogging, ByVal eventInfos As EventInfos, _  
ByVal logEntryInfos As LogEntryInfos, ByVal refTracker As ObjectReferenceTracker)   
  
    Dim paramNames(0) As String  
    Dim paramTypes(0) As TypeCode = {TypeCode.Int32}  
    Dim paramDescriptions(0) As String  
  
    Me.eventInfos = eventInfos  
  
    paramNames(0) = "InitialValue"  
    paramDescriptions(0) = "The value before it is incremented."  
  
    Me.eventInfos.Add("OnBeforeIncrement", _  
      "Fires before the task increments the value.", _  
      True, paramNames, paramTypes, paramDescriptions)  
    Me.onBeforeIncrement = Me.eventInfos("OnBeforeIncrement")  
  
    paramDescriptions(0) = "The value after it has been incremented."  
    Me.eventInfos.Add("OnAfterIncrement", _  
      "Fires after the initial value is updated.", True, _  
      paramNames, paramTypes, paramDescriptions)  
    Me.onAfterIncrement = Me.eventInfos("OnAfterIncrement")  
  
End Sub  
```  
  
## <a name="raising-custom-events"></a><span data-ttu-id="069fa-118">Вызов пользовательских событий</span><span class="sxs-lookup"><span data-stu-id="069fa-118">Raising Custom Events</span></span>  
 <span data-ttu-id="069fa-119">Пользовательские события вызываются с помощью метода <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireCustomEvent%2A>.</span><span class="sxs-lookup"><span data-stu-id="069fa-119">Custom events are raised by calling the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireCustomEvent%2A> method.</span></span> <span data-ttu-id="069fa-120">В следующей строке кода вызывается пользовательское событие.</span><span class="sxs-lookup"><span data-stu-id="069fa-120">The following line of code raises a custom event.</span></span>  
  
```csharp  
componentEvents.FireCustomEvent(this.onBeforeIncrement.Name,  
   this.onBeforeIncrement.Description, ref arguments,  
   null, ref bFireOnBeforeIncrement);  
```  
  
```vb  
componentEvents.FireCustomEvent(Me.onBeforeIncrement.Name, _  
Me.onBeforeIncrement.Description, arguments, _  
Nothing,  bFireOnBeforeIncrement)  
```  
  
## <a name="sample"></a><span data-ttu-id="069fa-121">Образец</span><span class="sxs-lookup"><span data-stu-id="069fa-121">Sample</span></span>  
 <span data-ttu-id="069fa-122">В следующем примере демонстрируется задача, которая определяет пользовательское событие в методе `InitializeTask`, добавляет пользовательское событие в коллекцию <xref:Microsoft.SqlServer.Dts.Runtime.EventInfos>, а затем вызывает пользовательское событие при выполнении метода `Execute` посредством вызова метода <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireCustomEvent%2A>.</span><span class="sxs-lookup"><span data-stu-id="069fa-122">The following example shows a task that defines a custom event in the `InitializeTask` method, adds the custom event to the <xref:Microsoft.SqlServer.Dts.Runtime.EventInfos> collection, and then raises the custom event during its `Execute` method by calling the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireCustomEvent%2A> method.</span></span>  
  
```csharp  
[DtsTask(DisplayName = "CustomEventTask")]  
    public class CustomEventTask : Task  
    {  
        public override DTSExecResult Execute(Connections connections,   
          VariableDispenser variableDispenser, IDTSComponentEvents componentEvents,  
           IDTSLogging log, object transaction)  
        {  
            bool fireAgain;  
            object[] args = new object[1] { "The value of the parameter." };  
            componentEvents.FireCustomEvent( "MyCustomEvent",   
              "Firing the custom event.", ref args,  
              "CustomEventTask" , ref fireAgain );  
            return DTSExecResult.Success;  
        }  
  
        public override void InitializeTask(Connections connections,  
          VariableDispenser variableDispenser, IDTSInfoEvents events,  
          IDTSLogging log, EventInfos eventInfos,  
          LogEntryInfos logEntryInfos, ObjectReferenceTracker refTracker)  
        {  
            string[] names = new string[1] {"Parameter1"};  
            TypeCode[] types = new TypeCode[1] {TypeCode.String};  
            string[] descriptions = new string[1] {"Parameter description." };  
  
            eventInfos.Add("MyCustomEvent",  
             "Fires when my interesting event happens.",  
             true, names, types, descriptions);  
  
        }  
   }  
```  
  
```vb  
<DtsTask(DisplayName = "CustomEventTask")> _   
    Public Class CustomEventTask  
     Inherits Task  
        Public Overrides Function Execute(ByVal connections As Connections, _  
          ByVal variableDispenser As VariableDispenser, _  
          ByVal componentEvents As IDTSComponentEvents, _  
          ByVal log As IDTSLogging, ByVal transaction As Object) _  
          As DTSExecResult  
  
            Dim fireAgain As Boolean  
            Dim args() As Object =  New Object(1) {"The value of the parameter."}  
  
            componentEvents.FireCustomEvent("MyCustomEvent", _  
              "Firing the custom event.", args, _  
              "CustomEventTask" ,  fireAgain)  
            Return DTSExecResult.Success  
        End Function  
  
        Public Overrides  Sub InitializeTask(ByVal connections As Connections, _  
          ByVal variableDispenser As VariableDispenser,  
          ByVal events As IDTSInfoEvents,  
          ByVal log As IDTSLogging, ByVal eventInfos As EventInfos, ByVal logEnTryInfos As LogEnTryInfos, ByVal refTracker As ObjectReferenceTracker)  
  
            Dim names() As String =  New String(1) {"Parameter1"}  
            Dim types() As TypeCode =  New TypeCode(1) {TypeCode.String}  
            Dim descriptions() As String =  New String(1) {"Parameter description."}  
  
            eventInfos.Add("MyCustomEvent", _  
              "Fires when my interesting event happens.", _  
              True, names, types, descriptions)  
  
        End Sub  
  
    End Class  
```  
  
<span data-ttu-id="069fa-123">![Значок Integration Services (маленький)](../../media/dts-16.gif "Значок служб Integration Services (маленький)")  **следит за обновлениями Integration Services**</span><span class="sxs-lookup"><span data-stu-id="069fa-123">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="069fa-124">Чтобы загрузить новейшую документацию, статьи, образцы и видеоматериалы корпорации Майкрософт, а также лучшие решения участников сообщества, посетите страницу служб [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] на сайте MSDN:</span><span class="sxs-lookup"><span data-stu-id="069fa-124">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="069fa-125">Посетить страницу «Службы Integration Services» на сайте MSDN</span><span class="sxs-lookup"><span data-stu-id="069fa-125">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="069fa-126">Чтобы получать автоматические уведомления об этих обновлениях, подпишитесь на RSS-каналы, предлагаемые на этой странице.</span><span class="sxs-lookup"><span data-stu-id="069fa-126">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="069fa-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="069fa-127">See Also</span></span>  
 <span data-ttu-id="069fa-128">[Обработчики событий в службах Integration Services (SSIS)](../../integration-services-ssis-event-handlers.md) </span><span class="sxs-lookup"><span data-stu-id="069fa-128">[Integration Services &#40;SSIS&#41; Event Handlers](../../integration-services-ssis-event-handlers.md) </span></span>  
 [<span data-ttu-id="069fa-129">Добавление обработчика событий к пакету</span><span class="sxs-lookup"><span data-stu-id="069fa-129">Add an Event Handler to a Package</span></span>](../../add-an-event-handler-to-a-package.md)  
  
  
