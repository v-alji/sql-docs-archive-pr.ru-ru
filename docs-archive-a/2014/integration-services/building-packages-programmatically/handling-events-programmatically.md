---
title: Программная обработка событий | Документы Майкрософт
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
- Integration Services packages, events
- SQL Server Integration Services packages, events
- SSIS events, programmatically handling
- packages [Integration Services], events
- DtsEventHandler object
- SSIS packages, events
- SSIS events
- events [Integration Services], programmatically
- tasks [Integration Services], events
- IDTSEvents interface
ms.assetid: 0f00bd66-efd5-4f12-9e1c-36195f739332
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c70d2d8909df65f775fc3a3034931bb599597068
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657856"
---
# <a name="handling-events-programmatically"></a><span data-ttu-id="f7ed1-102">Программная обработка событий</span><span class="sxs-lookup"><span data-stu-id="f7ed1-102">Handling Events Programmatically</span></span>
  <span data-ttu-id="f7ed1-103">В среде выполнения служб [!INCLUDE[ssIS](../../includes/ssis-md.md)] имеется коллекция событий, возникающих до, во время и после проверки и выполнения пакета.</span><span class="sxs-lookup"><span data-stu-id="f7ed1-103">The [!INCLUDE[ssIS](../../includes/ssis-md.md)] runtime provides a collection of events that occur before, during, and after the validation and execution of a package.</span></span> <span data-ttu-id="f7ed1-104">Эти события можно зафиксировать двумя способами.</span><span class="sxs-lookup"><span data-stu-id="f7ed1-104">These events can be captured in two ways.</span></span> <span data-ttu-id="f7ed1-105">Первый метод включает реализацию интерфейса <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents> в классе и указание класса в качестве параметра для методов `Execute` и `Validate` пакета.</span><span class="sxs-lookup"><span data-stu-id="f7ed1-105">The first method is by implementing the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents> interface in a class, and supplying the class as a parameter to the `Execute` and `Validate` methods of the package.</span></span> <span data-ttu-id="f7ed1-106">Второй метод включает создание объектов <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler>, которые могут содержать другие объекты служб [!INCLUDE[ssIS](../../includes/ssis-md.md)], например задачи и циклы, выполняемые при возникновении события <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents>.</span><span class="sxs-lookup"><span data-stu-id="f7ed1-106">The second method is by creating <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler> objects, which can contain other [!INCLUDE[ssIS](../../includes/ssis-md.md)] objects, such as tasks and loops, that are executed when an event in <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents> occurs.</span></span> <span data-ttu-id="f7ed1-107">В данном разделе описаны эти два метода и приведены примеры кода, иллюстрирующие их использование.</span><span class="sxs-lookup"><span data-stu-id="f7ed1-107">This section describes these two methods and provides code examples to demonstrate their use.</span></span>  
  
## <a name="receiving-idtsevents-callbacks"></a><span data-ttu-id="f7ed1-108">Получение обратных вызовов IDTSEvents</span><span class="sxs-lookup"><span data-stu-id="f7ed1-108">Receiving IDTSEvents Callbacks</span></span>  
 <span data-ttu-id="f7ed1-109">Разработчики, создающие и программно выполняющие пакеты, могут получать уведомления о событиях во время проверки и выполнения с помощью интерфейса <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents>.</span><span class="sxs-lookup"><span data-stu-id="f7ed1-109">Developers who build and execute packages programmatically can receive event notifications during the validation and execution process using the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents> interface.</span></span> <span data-ttu-id="f7ed1-110">Для этого создается класс, в котором реализован интерфейс <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents>, и этот класс указывается в качестве параметра для методов `Validate` и `Execute` пакета.</span><span class="sxs-lookup"><span data-stu-id="f7ed1-110">This is done by creating a class that implements the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents> interface and providing this class as a parameter to the `Validate` and `Execute` methods of a package.</span></span> <span data-ttu-id="f7ed1-111">Методы класса затем вызываются подсистемой выполнения при возникновении события.</span><span class="sxs-lookup"><span data-stu-id="f7ed1-111">The methods of the class are then called by the run-time engine when the events occur.</span></span>  
  
 <span data-ttu-id="f7ed1-112">Класс <xref:Microsoft.SqlServer.Dts.Runtime.DefaultEvents> — это класс, в котором уже реализован интерфейс <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents>. Поэтому другой альтернативой прямой реализации <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents> является создание производного от <xref:Microsoft.SqlServer.Dts.Runtime.DefaultEvents> класса и переопределение событий, требующих отклика.</span><span class="sxs-lookup"><span data-stu-id="f7ed1-112">The <xref:Microsoft.SqlServer.Dts.Runtime.DefaultEvents> class is a class that already implements the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents> interface; therefore, another alternative to implementing <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents> directly is to derive from <xref:Microsoft.SqlServer.Dts.Runtime.DefaultEvents> and override the specific events that you want to respond to.</span></span> <span data-ttu-id="f7ed1-113">Затем этот класс указывается в качестве параметра для методов `Validate` и `Execute` класса <xref:Microsoft.SqlServer.Dts.Runtime.Package> для получения обратных вызовов событий.</span><span class="sxs-lookup"><span data-stu-id="f7ed1-113">You then provide your class as a parameter to the `Validate` and `Execute` methods of the <xref:Microsoft.SqlServer.Dts.Runtime.Package> to receive event callbacks.</span></span>  
  
 <span data-ttu-id="f7ed1-114">В следующем образце кода показан класс, производный от <xref:Microsoft.SqlServer.Dts.Runtime.DefaultEvents>, переопределяющий метод <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents.OnPreExecute%2A>.</span><span class="sxs-lookup"><span data-stu-id="f7ed1-114">The following code sample demonstrates a class that derives from <xref:Microsoft.SqlServer.Dts.Runtime.DefaultEvents>, and overrides the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents.OnPreExecute%2A> method.</span></span> <span data-ttu-id="f7ed1-115">Затем класс предоставляется как параметра `Validate` `Execute` методам и пакета.</span><span class="sxs-lookup"><span data-stu-id="f7ed1-115">The class is then provided as aparameter to the `Validate` and `Execute` methods of the package.</span></span>  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
  
namespace Microsoft.SqlServer.Dts.Samples  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      Package p = new Package();  
      MyEventsClass eventsClass = new MyEventsClass();  
  
      p.Validate(null, null, eventsClass, null);  
      p.Execute(null, null, eventsClass, null, null);  
  
      Console.Read();  
    }  
  }  
  class MyEventsClass : DefaultEvents  
  {  
    public override void OnPreExecute(Executable exec, ref bool fireAgain)  
    {  
      // TODO: Add custom code to handle the event.  
      Console.WriteLine("The PreExecute event of the " +  
        exec.ToString() + " has been raised.");  
    }  
  }  
}  
```  
  
```vb  
Imports Microsoft.SqlServer.Dts.Runtime  
  
Module Module1  
  
  Sub Main()  
  
    Dim p As Package = New Package()  
    Dim eventsClass As MyEventsClass = New MyEventsClass()  
  
    p.Validate(Nothing, Nothing, eventsClass, Nothing)  
    p.Execute(Nothing, Nothing, eventsClass, Nothing, Nothing)  
  
    Console.Read()  
  
  End Sub  
  
End Module  
  
Class MyEventsClass  
  Inherits DefaultEvents  
  
  Public Overrides Sub OnPreExecute(ByVal exec As Executable, ByRef fireAgain As Boolean)  
  
    ' TODO: Add custom code to handle the event.  
    Console.WriteLine("The PreExecute event of the " & _  
      exec.ToString() & " has been raised.")  
  
  End Sub  
  
End Class  
```  
  
## <a name="creating-dtseventhandler-objects"></a><span data-ttu-id="f7ed1-116">Создание объектов DtsEventHandler</span><span class="sxs-lookup"><span data-stu-id="f7ed1-116">Creating DtsEventHandler Objects</span></span>  
 <span data-ttu-id="f7ed1-117">Подсистема выполнения обеспечивает гибкую и мощную систему обработки событий и уведомления о них с помощью объекта <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="f7ed1-117">The run-time engine provides a robust, highly flexible event handling and notification system through the <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler> object.</span></span> <span data-ttu-id="f7ed1-118">Эти объекты позволяют создавать с помощью обработчика событий целые рабочие процессы, выполняющиеся только при возникновении события, которому принадлежит обработчик событий.</span><span class="sxs-lookup"><span data-stu-id="f7ed1-118">These objects let you design whole workflows within the event handler, which execute only when the event that the event handler belongs to occurs.</span></span> <span data-ttu-id="f7ed1-119">Объект <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler> является контейнером, выполняющимся только при возникновении соответствующего события в родительском объекте.</span><span class="sxs-lookup"><span data-stu-id="f7ed1-119">The <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler> object is a container that is executed when the corresponding event on its parent object fires.</span></span> <span data-ttu-id="f7ed1-120">Эта архитектура позволяет создавать изолированные рабочие процессы, выполняющиеся в ответ на возникновение событий в контейнере.</span><span class="sxs-lookup"><span data-stu-id="f7ed1-120">This architecture lets you create isolated workflows that are executed in response to events that occur on a container.</span></span> <span data-ttu-id="f7ed1-121">Поскольку объекты <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler> являются синхронными, выполнение не возобновляется до тех пор, пока не будут возвращены обработчики событий, связанные с событием.</span><span class="sxs-lookup"><span data-stu-id="f7ed1-121">Because <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler> objects are synchronous, execution does not resume until the event handlers that are attached to the event have returned.</span></span>  
  
 <span data-ttu-id="f7ed1-122">В следующем примере кода показано, как создать объект <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="f7ed1-122">The following code demonstrates how to create a <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler> object.</span></span> <span data-ttu-id="f7ed1-123">Код добавляет <xref:Microsoft.SqlServer.Dts.Tasks.FileSystemTask.FileSystemTask> к коллекции <xref:Microsoft.SqlServer.Dts.Runtime.Package.Executables%2A> пакета, а затем создает объект <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler> для события <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents.OnError%2A> задачи.</span><span class="sxs-lookup"><span data-stu-id="f7ed1-123">The code adds a <xref:Microsoft.SqlServer.Dts.Tasks.FileSystemTask.FileSystemTask> to the <xref:Microsoft.SqlServer.Dts.Runtime.Package.Executables%2A> collection of the package, and then creates a <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler> object for the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents.OnError%2A> event of the task.</span></span> <span data-ttu-id="f7ed1-124">Задача <xref:Microsoft.SqlServer.Dts.Tasks.FileSystemTask.FileSystemTask> добавляется к обработчику событий, который выполняется при возникновении события <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents.OnError%2A> для первой задачи <xref:Microsoft.SqlServer.Dts.Tasks.FileSystemTask.FileSystemTask>.</span><span class="sxs-lookup"><span data-stu-id="f7ed1-124">A <xref:Microsoft.SqlServer.Dts.Tasks.FileSystemTask.FileSystemTask> is added to the event handler, which is executed when the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSEvents.OnError%2A> event occurs for the first <xref:Microsoft.SqlServer.Dts.Tasks.FileSystemTask.FileSystemTask>.</span></span> <span data-ttu-id="f7ed1-125">В этом примере предполагается, что для тестирования существует файл с именем «C:\Windows\Temp\DemoFile.txt».</span><span class="sxs-lookup"><span data-stu-id="f7ed1-125">This example assumes that you have a file that is named C:\Windows\Temp\DemoFile.txt for testing.</span></span> <span data-ttu-id="f7ed1-126">При первом запуске образца файл успешно копируется и обработчик событий не вызывается.</span><span class="sxs-lookup"><span data-stu-id="f7ed1-126">The first time that you run the sample, if copies the file successfully and the event handler is not called.</span></span> <span data-ttu-id="f7ed1-127">При втором запуске образца первой задаче <xref:Microsoft.SqlServer.Dts.Tasks.FileSystemTask.FileSystemTask> не удается скопировать файл (так как для <xref:Microsoft.SqlServer.Dts.Tasks.FileSystemTask.FileSystemTask.OverwriteDestinationFile%2A> задано значение `false`), вызывается обработчик события, вторая задача <xref:Microsoft.SqlServer.Dts.Tasks.FileSystemTask.FileSystemTask> удаляет исходный файл, а пакет сообщает о сбое, так как возникла ошибка.</span><span class="sxs-lookup"><span data-stu-id="f7ed1-127">The second time you run the sample, the first <xref:Microsoft.SqlServer.Dts.Tasks.FileSystemTask.FileSystemTask> fails to copy the file (because the value of <xref:Microsoft.SqlServer.Dts.Tasks.FileSystemTask.FileSystemTask.OverwriteDestinationFile%2A> is `false`), the event handler is called, the second <xref:Microsoft.SqlServer.Dts.Tasks.FileSystemTask.FileSystemTask> deletes the source file, and the package reports failure because of the error that occurred.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f7ed1-128">Пример</span><span class="sxs-lookup"><span data-stu-id="f7ed1-128">Example</span></span>  
  
```csharp  
using System;  
using System.IO;  
using Microsoft.SqlServer.Dts.Runtime;  
using Microsoft.SqlServer.Dts.Tasks.FileSystemTask;  
  
namespace Microsoft.SqlServer.Dts.Samples  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      string f = "DemoFile.txt";  
      Executable e;  
      TaskHost th;  
      FileSystemTask fst;  
  
      Package p = new Package();  
  
      p.Variables.Add("sourceFile", true, String.Empty,  
        @"C:\Windows\Temp\" + f);  
      p.Variables.Add("destinationFile", true, String.Empty,  
        Path.Combine(Directory.GetCurrentDirectory(), f));  
  
      // Create a first File System task and add it to the package.  
      // This task tries to copy a file from one folder to another.  
      e = p.Executables.Add("STOCK:FileSystemTask");  
      th = e as TaskHost;  
      th.Name = "FileSystemTask1";  
      fst = th.InnerObject as FileSystemTask;  
  
      fst.Operation = DTSFileSystemOperation.CopyFile;  
      fst.OverwriteDestinationFile = false;  
      fst.Source = "sourceFile";  
      fst.IsSourcePathVariable = true;  
      fst.Destination = "destinationFile";  
      fst.IsDestinationPathVariable = true;  
  
      // Add an event handler for the FileSystemTask's OnError event.  
      DtsEventHandler ehOnError = (DtsEventHandler)th.EventHandlers.Add("OnError");  
  
      // Create a second File System task and add it to the event handler.  
      // This task deletes the source file if the event handler is called.  
      e = ehOnError.Executables.Add("STOCK:FileSystemTask");  
      th = e as TaskHost;  
      th.Name = "FileSystemTask2";  
      fst = th.InnerObject as FileSystemTask;  
  
      fst.Operation = DTSFileSystemOperation.DeleteFile;  
      fst.Source = "sourceFile";  
      fst.IsSourcePathVariable = true;  
  
      DTSExecResult vr = p.Validate(null, null, null, null);  
      Console.WriteLine("ValidationResult = " + vr.ToString());  
      if (vr == DTSExecResult.Success)  
      {  
        DTSExecResult er = p.Execute(null, null, null, null, null);  
        Console.WriteLine("ExecutionResult = " + er.ToString());  
        if (er == DTSExecResult.Failure)  
          if (!File.Exists(@"C:\Windows\Temp\" + f))  
            Console.WriteLine("Source file has been deleted by the event handler.");  
      }  
      Console.Read();  
    }  
  }  
}  
```  
  
```vb  
Imports System.IO  
Imports Microsoft.SqlServer.Dts.Runtime  
Imports Microsoft.SqlServer.Dts.Tasks.FileSystemTask  
  
Module Module1  
  
  Sub Main()  
  
    Dim f As String = "DemoFile.txt"  
    Dim e As Executable  
    Dim th As TaskHost  
    Dim fst As FileSystemTask  
  
    Dim p As Package = New Package()  
  
    p.Variables.Add("sourceFile", True, String.Empty, _  
      "C:\Windows\Temp\" & f)  
    p.Variables.Add("destinationFile", True, String.Empty, _  
      Path.Combine(Directory.GetCurrentDirectory(), f))  
  
    ' Create a first File System task and add it to the package.  
    ' This task tries to copy a file from one folder to another.  
    e = p.Executables.Add("STOCK:FileSystemTask")  
    th = CType(e, TaskHost)  
    th.Name = "FileSystemTask1"  
    fst = CType(th.InnerObject, FileSystemTask)  
  
    fst.Operation = DTSFileSystemOperation.CopyFile  
    fst.OverwriteDestinationFile = False  
    fst.Source = "sourceFile"  
    fst.IsSourcePathVariable = True  
    fst.Destination = "destinationFile"  
    fst.IsDestinationPathVariable = True  
  
    ' Add an event handler for the FileSystemTask's OnError event.  
    Dim ehOnError As DtsEventHandler = CType(th.EventHandlers.Add("OnError"), DtsEventHandler)  
  
    ' Create a second File System task and add it to the event handler.  
    ' This task deletes the source file if the event handler is called.  
    e = ehOnError.Executables.Add("STOCK:FileSystemTask")  
    th = CType(e, TaskHost)  
    th.Name = "FileSystemTask1"  
    fst = CType(th.InnerObject, FileSystemTask)  
  
    fst.Operation = DTSFileSystemOperation.DeleteFile  
    fst.Source = "sourceFile"  
    fst.IsSourcePathVariable = True  
  
    Dim vr As DTSExecResult = p.Validate(Nothing, Nothing, Nothing, Nothing)  
    Console.WriteLine("ValidationResult = " + vr.ToString())  
    If vr = DTSExecResult.Success Then  
      Dim er As DTSExecResult = p.Execute(Nothing, Nothing, Nothing, Nothing, Nothing)  
      Console.WriteLine("ExecutionResult = " + er.ToString())  
      If er = DTSExecResult.Failure Then  
        If Not File.Exists("C:\Windows\Temp\" + f) Then  
          Console.WriteLine("Source file has been deleted by the event handler.")  
        End If  
      End If  
    End If  
    Console.Read()  
  
  End Sub  
  
End Module  
```  
  
<span data-ttu-id="f7ed1-129">![Значок Integration Services (маленький)](../media/dts-16.gif "Значок служб Integration Services (маленький)")  **следит за обновлениями Integration Services**</span><span class="sxs-lookup"><span data-stu-id="f7ed1-129">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="f7ed1-130">Чтобы загрузить новейшую документацию, статьи, образцы и видеоматериалы корпорации Майкрософт, а также лучшие решения участников сообщества, посетите страницу служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] на сайте MSDN:</span><span class="sxs-lookup"><span data-stu-id="f7ed1-130">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="f7ed1-131">Посетить страницу «Службы Integration Services» на сайте MSDN</span><span class="sxs-lookup"><span data-stu-id="f7ed1-131">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="f7ed1-132">Чтобы получать автоматические уведомления об этих обновлениях, подпишитесь на RSS-каналы, предлагаемые на этой странице.</span><span class="sxs-lookup"><span data-stu-id="f7ed1-132">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7ed1-133">См. также:</span><span class="sxs-lookup"><span data-stu-id="f7ed1-133">See Also</span></span>  
 <span data-ttu-id="f7ed1-134">[Обработчики событий в службах Integration Services (SSIS)](../integration-services-ssis-event-handlers.md) </span><span class="sxs-lookup"><span data-stu-id="f7ed1-134">[Integration Services &#40;SSIS&#41; Event Handlers](../integration-services-ssis-event-handlers.md) </span></span>  
 [<span data-ttu-id="f7ed1-135">Добавление обработчика событий к пакету</span><span class="sxs-lookup"><span data-stu-id="f7ed1-135">Add an Event Handler to a Package</span></span>](../add-an-event-handler-to-a-package.md)  
  
  
