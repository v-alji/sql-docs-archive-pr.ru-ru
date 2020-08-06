---
title: Программное добавление задач | Документы Майкрософт
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
- tasks [Integration Services], packages
- adding package tasks
ms.assetid: 5d4652d5-228c-4238-905c-346dd8503fdf
author: chugugrace
ms.author: chugu
ms.openlocfilehash: aa61eb2fb87f45fe5b534b96280b8b4e2c21788d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658364"
---
# <a name="adding-tasks-programmatically"></a><span data-ttu-id="c8099-102">Программное добавление задач</span><span class="sxs-lookup"><span data-stu-id="c8099-102">Adding Tasks Programmatically</span></span>
  <span data-ttu-id="c8099-103">Задачи могут быть добавлены в среде выполнения к объектам следующих типов.</span><span class="sxs-lookup"><span data-stu-id="c8099-103">Tasks can be added to the following types of objects in the run-time engine:</span></span>  
  
-   <xref:Microsoft.SqlServer.Dts.Runtime.Package>  
  
-   <xref:Microsoft.SqlServer.Dts.Runtime.Sequence>  
  
-   <xref:Microsoft.SqlServer.Dts.Runtime.ForLoop>  
  
-   <xref:Microsoft.SqlServer.Dts.Runtime.ForEachLoop>  
  
-   <xref:Microsoft.SqlServer.Dts.Runtime.DtsEventHandler>  
  
 <span data-ttu-id="c8099-104">Эти классы рассматриваются как контейнеры, причем все они наследуют свойство <xref:Microsoft.SqlServer.Dts.Runtime.IDTSSequence.Executables%2A>.</span><span class="sxs-lookup"><span data-stu-id="c8099-104">These classes are considered containers, and they all inherit the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSSequence.Executables%2A> property.</span></span> <span data-ttu-id="c8099-105">Контейнеры могут содержать коллекцию задач, представляющих собой исполняемые объекты, которые обрабатываются средой выполнения во время выполнения контейнера.</span><span class="sxs-lookup"><span data-stu-id="c8099-105">Containers can contain a collection of tasks, which are executable objects processed by the runtime during execution of the container.</span></span> <span data-ttu-id="c8099-106">Порядок выполнения объектов в коллекции определяется любым набором <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint> для каждой задачи в контейнерах.</span><span class="sxs-lookup"><span data-stu-id="c8099-106">The order of execution of the objects in the collection is determined any <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint> set on each task in the containers.</span></span> <span data-ttu-id="c8099-107">Элементы управления очередностью включают ветвление выполнения в зависимости от успеха, неудачи или завершения любого объекта <xref:Microsoft.SqlServer.Dts.Runtime.Executable> в коллекции.</span><span class="sxs-lookup"><span data-stu-id="c8099-107">Precedence constraints enable execution branching based on the success, failure, or completion of an <xref:Microsoft.SqlServer.Dts.Runtime.Executable> in the collection.</span></span>  
  
 <span data-ttu-id="c8099-108">Каждый контейнер имеет коллекцию <xref:Microsoft.SqlServer.Dts.Runtime.Executables>, которая содержит отдельные объекты <xref:Microsoft.SqlServer.Dts.Runtime.Executable>.</span><span class="sxs-lookup"><span data-stu-id="c8099-108">Each container has an <xref:Microsoft.SqlServer.Dts.Runtime.Executables> collection that contains the individual <xref:Microsoft.SqlServer.Dts.Runtime.Executable> objects.</span></span> <span data-ttu-id="c8099-109">Каждая исполняемая задача наследует и реализует методы <xref:Microsoft.SqlServer.Dts.Runtime.Executable.Execute%2A> и <xref:Microsoft.SqlServer.Dts.Runtime.Executable.Validate%2A>.</span><span class="sxs-lookup"><span data-stu-id="c8099-109">Each executable task inherits and implements the <xref:Microsoft.SqlServer.Dts.Runtime.Executable.Execute%2A> method and <xref:Microsoft.SqlServer.Dts.Runtime.Executable.Validate%2A> method.</span></span> <span data-ttu-id="c8099-110">Эти два метода вызываются средой выполнения для обработки каждого объекта <xref:Microsoft.SqlServer.Dts.Runtime.Executable>.</span><span class="sxs-lookup"><span data-stu-id="c8099-110">These two methods are called by the run-time engine to process each <xref:Microsoft.SqlServer.Dts.Runtime.Executable>.</span></span>  
  
 <span data-ttu-id="c8099-111">Чтобы добавить задачу к пакету, необходим контейнер с существующей коллекцией <xref:Microsoft.SqlServer.Dts.Runtime.Executables>.</span><span class="sxs-lookup"><span data-stu-id="c8099-111">To add a task to a package, you need a container with an <xref:Microsoft.SqlServer.Dts.Runtime.Executables> existing collection.</span></span> <span data-ttu-id="c8099-112">В большинстве случаев задачей, добавляемой к коллекции, является пакет.</span><span class="sxs-lookup"><span data-stu-id="c8099-112">Most of the time, the task that you will add to the collection is a package.</span></span> <span data-ttu-id="c8099-113">Чтобы добавить новый исполняемый файл задачи в коллекцию для этого контейнера, необходимо вызвать метод <xref:Microsoft.SqlServer.Dts.Runtime.Executables.Add%2A>.</span><span class="sxs-lookup"><span data-stu-id="c8099-113">To add the new task executable into the collection for that container, you call the <xref:Microsoft.SqlServer.Dts.Runtime.Executables.Add%2A> method .</span></span> <span data-ttu-id="c8099-114">Этот метод имеет единственный параметр — строку, которая содержит специальное имя CLSID, PROGID, STOCK или свойство <xref:Microsoft.SqlServer.Dts.Runtime.TaskInfo.CreationName%2A> добавляемой задачи.</span><span class="sxs-lookup"><span data-stu-id="c8099-114">The method has a single parameter, a string, that contains the CLSID, PROGID, STOCK moniker, or <xref:Microsoft.SqlServer.Dts.Runtime.TaskInfo.CreationName%2A> of the task you are adding.</span></span>  
  
## <a name="task-names"></a><span data-ttu-id="c8099-115">Имена задач</span><span class="sxs-lookup"><span data-stu-id="c8099-115">Task Names</span></span>  
 <span data-ttu-id="c8099-116">Задачу можно указать по имени или идентификатору, но специальное имя `STOCK` представляет собой параметр, используемый чаще всего в методе <xref:Microsoft.SqlServer.Dts.Runtime.Executables.Add%2A>.</span><span class="sxs-lookup"><span data-stu-id="c8099-116">Although you can specify a task by name or by ID, the `STOCK` moniker is the parameter used most often in the <xref:Microsoft.SqlServer.Dts.Runtime.Executables.Add%2A> method.</span></span> <span data-ttu-id="c8099-117">Чтобы добавить задачу к исполняемому файлу, обозначенному специальным именем `STOCK`, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="c8099-117">To add a task to an executable identified by the `STOCK` moniker, use the following syntax:</span></span>  
  
```csharp  
Executable exec = package.Executables.Add("STOCK:BulkInsertTask");  
  
```  
  
```vb  
Dim exec As Executable = package.Executables.Add("STOCK:BulkInsertTask")  
  
```  
  
 <span data-ttu-id="c8099-118">В следующем списке для каждой задачи показаны имена, которые используются после специального имени `STOCK`.</span><span class="sxs-lookup"><span data-stu-id="c8099-118">The following list shows the names for each task that are used after the `STOCK` moniker.</span></span>  
  
-   <span data-ttu-id="c8099-119">ActiveXScriptTask</span><span class="sxs-lookup"><span data-stu-id="c8099-119">ActiveXScriptTask</span></span>  
  
-   <span data-ttu-id="c8099-120">BulkInsertTask</span><span class="sxs-lookup"><span data-stu-id="c8099-120">BulkInsertTask</span></span>  
  
-   <span data-ttu-id="c8099-121">ExecuteProcessTask</span><span class="sxs-lookup"><span data-stu-id="c8099-121">ExecuteProcessTask</span></span>  
  
-   <span data-ttu-id="c8099-122">ExecutePackageTask</span><span class="sxs-lookup"><span data-stu-id="c8099-122">ExecutePackageTask</span></span>  
  
-   <span data-ttu-id="c8099-123">Exec80PackageTask</span><span class="sxs-lookup"><span data-stu-id="c8099-123">Exec80PackageTask</span></span>  
  
-   <span data-ttu-id="c8099-124">FileSystemTask</span><span class="sxs-lookup"><span data-stu-id="c8099-124">FileSystemTask</span></span>  
  
-   <span data-ttu-id="c8099-125">FTPTask</span><span class="sxs-lookup"><span data-stu-id="c8099-125">FTPTask</span></span>  
  
-   <span data-ttu-id="c8099-126">MSMQTask</span><span class="sxs-lookup"><span data-stu-id="c8099-126">MSMQTask</span></span>  
  
-   <span data-ttu-id="c8099-127">PipelineTask</span><span class="sxs-lookup"><span data-stu-id="c8099-127">PipelineTask</span></span>  
  
-   <span data-ttu-id="c8099-128">ScriptTask</span><span class="sxs-lookup"><span data-stu-id="c8099-128">ScriptTask</span></span>  
  
-   <span data-ttu-id="c8099-129">SendMailTask</span><span class="sxs-lookup"><span data-stu-id="c8099-129">SendMailTask</span></span>  
  
-   <span data-ttu-id="c8099-130">SQLTask</span><span class="sxs-lookup"><span data-stu-id="c8099-130">SQLTask</span></span>  
  
-   <span data-ttu-id="c8099-131">TransferStoredProceduresTask</span><span class="sxs-lookup"><span data-stu-id="c8099-131">TransferStoredProceduresTask</span></span>  
  
-   <span data-ttu-id="c8099-132">TransferLoginsTask</span><span class="sxs-lookup"><span data-stu-id="c8099-132">TransferLoginsTask</span></span>  
  
-   <span data-ttu-id="c8099-133">TransferErrorMessagesTask</span><span class="sxs-lookup"><span data-stu-id="c8099-133">TransferErrorMessagesTask</span></span>  
  
-   <span data-ttu-id="c8099-134">TransferJobsTask</span><span class="sxs-lookup"><span data-stu-id="c8099-134">TransferJobsTask</span></span>  
  
-   <span data-ttu-id="c8099-135">TransferObjectsTask</span><span class="sxs-lookup"><span data-stu-id="c8099-135">TransferObjectsTask</span></span>  
  
-   <span data-ttu-id="c8099-136">TransferDatabaseTask</span><span class="sxs-lookup"><span data-stu-id="c8099-136">TransferDatabaseTask</span></span>  
  
-   <span data-ttu-id="c8099-137">WebServiceTask</span><span class="sxs-lookup"><span data-stu-id="c8099-137">WebServiceTask</span></span>  
  
-   <span data-ttu-id="c8099-138">WmiDataReaderTask</span><span class="sxs-lookup"><span data-stu-id="c8099-138">WmiDataReaderTask</span></span>  
  
-   <span data-ttu-id="c8099-139">WmiEventWatcherTask</span><span class="sxs-lookup"><span data-stu-id="c8099-139">WmiEventWatcherTask</span></span>  
  
-   <span data-ttu-id="c8099-140">XMLTask</span><span class="sxs-lookup"><span data-stu-id="c8099-140">XMLTask</span></span>  
  
 <span data-ttu-id="c8099-141">Если предпочтительным является более явный синтаксис или если задача, которую требуется добавить, не имеет специального имени STOCK, то можно добавить задачу к исполняемому файлу, используя ее длинное имя.</span><span class="sxs-lookup"><span data-stu-id="c8099-141">If you prefer a more explicit syntax, or if the task that you want to add does not have a STOCK moniker, you can add the task to the executable using its long name.</span></span> <span data-ttu-id="c8099-142">Этот синтаксис требует, чтобы был также указан номер версии задачи.</span><span class="sxs-lookup"><span data-stu-id="c8099-142">This syntax requires that you also specify the version number of the task.</span></span>  
  
```csharp  
Executable exec = package.Executables.Add(  
  "Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptTask, " +  
  "Microsoft.SqlServer.ScriptTask, Version=10.0.000.0, " +  
  "Culture=neutral, PublicKeyToken=89845dcd8080cc91");  
```  
  
```vb  
Dim exec As Executable = package.Executables.Add( _  
  "Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptTask, " & _  
  "Microsoft.SqlServer.ScriptTask, Version=10.0.000.0, " & _  
  "Culture=neutral, PublicKeyToken=89845dcd8080cc91")  
```  
  
 <span data-ttu-id="c8099-143">Можно получить длинное имя для задачи программным путем без обязательного указания версии задачи с помощью свойства **AssemblyQualifiedName** класса, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="c8099-143">You can obtain the long name for the task programmatically, without having to specify the task version, by using the **AssemblyQualifiedName** property of the class, as shown in the following example.</span></span> <span data-ttu-id="c8099-144">В этом примере необходима ссылка на сборку Microsoft.SqlServer.SQLTask.</span><span class="sxs-lookup"><span data-stu-id="c8099-144">This example requires a reference to the Microsoft.SqlServer.SQLTask assembly.</span></span>  
  
```csharp  
using Microsoft.SqlServer.Dts.Tasks.ExecuteSQLTask;  
...  
      Executable exec = package.Executables.Add(  
        typeof(Microsoft.SqlServer.Dts.Tasks.ExecuteSQLTask.ExecuteSQLTask).AssemblyQualifiedName);  
```  
  
```vb  
Imports Microsoft.SqlServer.Dts.Tasks.ExecuteSQLTask  
...  
    Dim exec As Executable = package.Executables.Add( _  
      GetType(Microsoft.SqlServer.Dts.Tasks.ExecuteSQLTask.ExecuteSQLTask).AssemblyQualifiedName)  
```  
  
 <span data-ttu-id="c8099-145">В следующем примере кода показано, как создать коллекцию <xref:Microsoft.SqlServer.Dts.Runtime.Executables> из нового пакета, а затем добавить задачи «Файловая система» и «Массовая вставка» в коллекцию с использованием их специальных имен `STOCK`.</span><span class="sxs-lookup"><span data-stu-id="c8099-145">The following code example shows how to create an <xref:Microsoft.SqlServer.Dts.Runtime.Executables> collection from a new package, and then add a File System task and a Bulk Insert task to the collection, by using their `STOCK` monikers.</span></span> <span data-ttu-id="c8099-146">В этом примере необходимы ссылки на сборки Microsoft.SqlServer.BulkInsertTask и Microsoft.SqlServer.FileSystemTask.</span><span class="sxs-lookup"><span data-stu-id="c8099-146">This example requires a reference to the Microsoft.SqlServer.FileSystemTask and Microsoft.SqlServer.BulkInsertTask assemblies.</span></span>  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
using Microsoft.SqlServer.Dts.Tasks.FileSystemTask;  
using Microsoft.SqlServer.Dts.Tasks.BulkInsertTask;  
  
namespace Microsoft.SqlServer.Dts.Samples  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      Package p = new Package();  
      // Add a File System task to the package.  
      Executable exec1 = p.Executables.Add("STOCK:FileSystemTask");  
      TaskHost thFileSystemTask = exec1 as TaskHost;  
      // Add a Bulk Insert task to the package.  
      Executable exec2 = p.Executables.Add("STOCK:BulkInsertTask");  
      TaskHost thBulkInsertTask = exec2 as TaskHost;  
  
      // Iterate through the package Executables collection.  
      Executables pExecs = p.Executables;  
      foreach (Executable pExec in pExecs)  
      {  
        TaskHost taskHost = (TaskHost)pExec;  
        Console.WriteLine("Type {0}", taskHost.InnerObject.ToString());  
      }  
      Console.Read();  
    }  
  }  
}  
```  
  
```vb  
Imports Microsoft.SqlServer.Dts.Runtime  
Imports Microsoft.SqlServer.Dts.Tasks.FileSystemTask  
Imports Microsoft.SqlServer.Dts.Tasks.BulkInsertTask  
  
Module Module1  
  
  Sub Main()  
  
    Dim p As Package = New Package()  
    ' Add a File System task to the package.  
    Dim exec1 As Executable = p.Executables.Add("STOCK:FileSystemTask")  
    Dim thFileSystemTask As TaskHost = CType(exec1, TaskHost)  
    ' Add a Bulk Insert task to the package.  
    Dim exec2 As Executable = p.Executables.Add("STOCK:BulkInsertTask")  
    Dim thBulkInsertTask As TaskHost = CType(exec2, TaskHost)  
  
    ' Iterate through the package Executables collection.  
    Dim pExecs As Executables = p.Executables  
    Dim pExec As Executable  
    For Each pExec In pExecs  
      Dim taskHost As TaskHost = CType(pExec, TaskHost)  
      Console.WriteLine("Type {0}", taskHost.InnerObject.ToString())  
    Next  
    Console.Read()  
  
  End Sub  
  
End Module  
```  
  
 <span data-ttu-id="c8099-147">**Образец вывода:**</span><span class="sxs-lookup"><span data-stu-id="c8099-147">**Sample Output:**</span></span>  
  
 `Type Microsoft.SqlServer.Dts.Tasks.FileSystemTask.FileSystemTask`  
  
 `Type Microsoft.SqlServer.Dts.Tasks.BulkInsertTask.BulkInsertTask`  
  
## <a name="taskhost-container"></a><span data-ttu-id="c8099-148">Контейнер TaskHost</span><span class="sxs-lookup"><span data-stu-id="c8099-148">TaskHost Container</span></span>  
 <span data-ttu-id="c8099-149">Класс <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> представляет собой контейнер, который не появляется в графическом пользовательском интерфейсе, но очень важен в программировании.</span><span class="sxs-lookup"><span data-stu-id="c8099-149">The <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> class is a container that does not appear in the graphical user interface, but is very important in programming.</span></span> <span data-ttu-id="c8099-150">Этот класс является оболочкой для каждой задачи.</span><span class="sxs-lookup"><span data-stu-id="c8099-150">This class is a wrapper for every task.</span></span> <span data-ttu-id="c8099-151">Задачи, добавляемые к пакету с помощью метода <xref:Microsoft.SqlServer.Dts.Runtime.Executables.Add%2A> как объекты <xref:Microsoft.SqlServer.Dts.Runtime.Executable>, могут быть приведены как объекты <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>.</span><span class="sxs-lookup"><span data-stu-id="c8099-151">Tasks that are added to the package by using the <xref:Microsoft.SqlServer.Dts.Runtime.Executables.Add%2A> method as an <xref:Microsoft.SqlServer.Dts.Runtime.Executable> object can be cast as a <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> object.</span></span> <span data-ttu-id="c8099-152">Если задача приведена как <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>, появляется возможность использовать в задаче дополнительные свойства и методы.</span><span class="sxs-lookup"><span data-stu-id="c8099-152">When a task is cast as a <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>, you can use additional properties and methods on the task.</span></span> <span data-ttu-id="c8099-153">Кроме того, можно получить доступ к самой задаче с помощью свойства <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.InnerObject%2A> объекта <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>.</span><span class="sxs-lookup"><span data-stu-id="c8099-153">Also, the task itself can be accessed through the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.InnerObject%2A> property of the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>.</span></span> <span data-ttu-id="c8099-154">В зависимости от конкретных потребностей, может быть решено оставить задачу в качестве объекта <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>, чтобы можно было использовать свойства задачи с помощью коллекции <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.Properties%2A>.</span><span class="sxs-lookup"><span data-stu-id="c8099-154">Depending on your needs, you may decide to keep the task as a <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> object so that you can use the properties of the task through the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.Properties%2A> collection.</span></span> <span data-ttu-id="c8099-155">Преимущество использования коллекции <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.Properties%2A> состоит в том, что может быть написан более общий код.</span><span class="sxs-lookup"><span data-stu-id="c8099-155">The advantage of using the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.Properties%2A> is that you can write more generic code.</span></span> <span data-ttu-id="c8099-156">Если для задачи требуется весьма конкретный код, необходимо привести задачу к соответствующему ей объекту.</span><span class="sxs-lookup"><span data-stu-id="c8099-156">If you need very specific code for a task, then you should cast the task to its appropriate object.</span></span>  
  
 <span data-ttu-id="c8099-157">В следующем примере кода показано, как привести объект <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> (thBulkInsertTask), который содержит задачу <xref:Microsoft.SqlServer.Dts.Tasks.BulkInsertTask.BulkInsertTask>, к объекту <xref:Microsoft.SqlServer.Dts.Tasks.BulkInsertTask.BulkInsertTask>.</span><span class="sxs-lookup"><span data-stu-id="c8099-157">The following code example shows how to cast a <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>, thBulkInsertTask, that contains a <xref:Microsoft.SqlServer.Dts.Tasks.BulkInsertTask.BulkInsertTask>, to a <xref:Microsoft.SqlServer.Dts.Tasks.BulkInsertTask.BulkInsertTask> object.</span></span>  
  
```csharp  
BulkInsertTask myTask = thBulkInsertTask.InnerObject as BulkInsertTask;  
```  
  
```vb  
Dim myTask As BulkInsertTask = CType(thBulkInsertTask.InnerObject, BulkInsertTask)  
```  
  
 <span data-ttu-id="c8099-158">В следующем примере кода показано, как привести исполняемый файл к объекту <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>, а затем с помощью свойства <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.InnerObject%2A> определить, какого типа исполняемый файл содержится на этом узле.</span><span class="sxs-lookup"><span data-stu-id="c8099-158">The following code example shows how to cast the executable to a <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>, and then use the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.InnerObject%2A> property to determine which type of executable is contained by the host.</span></span>  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
using Microsoft.SqlServer.Dts.Tasks.FileSystemTask;  
using Microsoft.SqlServer.Dts.Tasks.BulkInsertTask;  
  
namespace Microsoft.SqlServer.Dts.Samples  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      Package p = new Package();  
      // Add a File System task to the package.  
      Executable exec1 = p.Executables.Add("STOCK:FileSystemTask");  
      TaskHost thFileSystemTask1 = exec1 as TaskHost;  
      // Add a Bulk Insert task to the package.  
      Executable exec2 = p.Executables.Add("STOCK:BulkInsertTask");  
      TaskHost thFileSystemTask2 = exec2 as TaskHost;  
  
      // Iterate through the package Executables collection.  
      Executables pExecs = p.Executables;  
      foreach (Executable pExec in pExecs)  
      {  
        TaskHost taskHost = (TaskHost)pExec;  
        if (taskHost.InnerObject is Microsoft.SqlServer.Dts.Tasks.FileSystemTask.FileSystemTask)  
        {  
          // Do work with FileSystemTask here.  
          Console.WriteLine("Found task of type {0}", taskHost.InnerObject.ToString());  
        }  
        else if (taskHost.InnerObject is Microsoft.SqlServer.Dts.Tasks.BulkInsertTask.BulkInsertTask)  
        {  
          // Do work with BulkInsertTask here.  
          Console.WriteLine("Found task of type {0}", taskHost.InnerObject.ToString());  
        }  
        // Add additional statements to check InnerObject, if desired.  
      }  
      Console.Read();  
    }  
  }  
}  
```  
  
```vb  
Imports Microsoft.SqlServer.Dts.Runtime  
Imports Microsoft.SqlServer.Dts.Tasks.FileSystemTask  
Imports Microsoft.SqlServer.Dts.Tasks.BulkInsertTask  
  
Module Module1  
  
  Sub Main()  
  
    Dim p As Package = New Package()  
    ' Add a File System task to the package.  
    Dim exec1 As Executable = p.Executables.Add("STOCK:FileSystemTask")  
    Dim thFileSystemTask1 As TaskHost = CType(exec1, TaskHost)  
    ' Add a Bulk Insert task to the package.  
    Dim exec2 As Executable = p.Executables.Add("STOCK:BulkInsertTask")  
    Dim thFileSystemTask2 As TaskHost = CType(exec2, TaskHost)  
  
    ' Iterate through the package Executables collection.  
    Dim pExecs As Executables = p.Executables  
    Dim pExec As Executable  
    For Each pExec In pExecs  
      Dim taskHost As TaskHost = CType(pExec, TaskHost)  
      If TypeOf taskHost.InnerObject Is Microsoft.SqlServer.Dts.Tasks.FileSystemTask.FileSystemTask Then  
        ' Do work with FileSystemTask here.  
        Console.WriteLine("Found task of type {0}", taskHost.InnerObject.ToString())  
      ElseIf TypeOf taskHost.InnerObject Is Microsoft.SqlServer.Dts.Tasks.BulkInsertTask.BulkInsertTask Then  
        ' Do work with BulkInsertTask here.  
        Console.WriteLine("Found task of type {0}", taskHost.InnerObject.ToString())  
      End If  
      ' Add additional statements to check InnerObject, if desired.  
    Next  
    Console.Read()  
  
  End Sub  
  
End Module  
```  
  
 <span data-ttu-id="c8099-159">**Образец вывода:**</span><span class="sxs-lookup"><span data-stu-id="c8099-159">**Sample Output:**</span></span>  
  
 `Found task of type Microsoft.SqlServer.Dts.Tasks.FileSystemTask.FileSystemTask`  
  
 `Found task of type Microsoft.SqlServer.Dts.Tasks.BulkInsertTask.BulkInsertTask`  
  
 <span data-ttu-id="c8099-160">Инструкция <xref:Microsoft.SqlServer.Dts.Runtime.Executables.Add%2A> возвращает исполняемый файл, который приведен к объекту <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>, из вновь созданного объекта <xref:Microsoft.SqlServer.Dts.Runtime.Executable>.</span><span class="sxs-lookup"><span data-stu-id="c8099-160">The <xref:Microsoft.SqlServer.Dts.Runtime.Executables.Add%2A> statement returns an executable that is cast to a <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> object from the newly created <xref:Microsoft.SqlServer.Dts.Runtime.Executable> object.</span></span>  
  
 <span data-ttu-id="c8099-161">Чтобы задать свойства или вызвать методы нового объекта, можно воспользоваться одним из двух способов.</span><span class="sxs-lookup"><span data-stu-id="c8099-161">To set properties or to call methods on the new object, you have two options:</span></span>  
  
1.  <span data-ttu-id="c8099-162">Применить коллекцию <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.Properties%2A> объекта <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>.</span><span class="sxs-lookup"><span data-stu-id="c8099-162">Use the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.Properties%2A> collection of the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>.</span></span> <span data-ttu-id="c8099-163">Например, для получения свойства объекта применить инструкцию `th.Properties["propertyname"].GetValue(th))`.</span><span class="sxs-lookup"><span data-stu-id="c8099-163">For example, to obtain a property from the object, use `th.Properties["propertyname"].GetValue(th))`.</span></span> <span data-ttu-id="c8099-164">Чтобы задать свойство, использовать инструкцию `th.Properties["propertyname"].SetValue(th, <value>);`.</span><span class="sxs-lookup"><span data-stu-id="c8099-164">To set a property, use `th.Properties["propertyname"].SetValue(th, <value>);`.</span></span>  
  
2.  <span data-ttu-id="c8099-165">Привести свойство <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.InnerObject%2A> объекта <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> к классу задачи.</span><span class="sxs-lookup"><span data-stu-id="c8099-165">Cast the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.InnerObject%2A> of the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> to the task class.</span></span> <span data-ttu-id="c8099-166">Например, чтобы привести задачу «Массовая вставка» к задаче <xref:Microsoft.SqlServer.Dts.Tasks.BulkInsertTask.BulkInsertTask> после ее добавления в пакет в качестве <xref:Microsoft.SqlServer.Dts.Runtime.Executable> и последующего приведения к <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>, можно использовать оператор `BulkInsertTask myTask = th.InnerObject as BulkInsertTask;`.</span><span class="sxs-lookup"><span data-stu-id="c8099-166">For example, to cast the Bulk Insert task to a <xref:Microsoft.SqlServer.Dts.Tasks.BulkInsertTask.BulkInsertTask> after it has been added to a package as an <xref:Microsoft.SqlServer.Dts.Runtime.Executable> and subsequently cast to a <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>, use `BulkInsertTask myTask = th.InnerObject as BulkInsertTask;`.</span></span>  
  
 <span data-ttu-id="c8099-167">Использование в коде класса <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> вместо приведения к классу, зависящему от задачи, предоставляет следующие преимущества.</span><span class="sxs-lookup"><span data-stu-id="c8099-167">Using the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> class in code, instead of casting to the task-specific class has the following advantages:</span></span>  
  
-   <span data-ttu-id="c8099-168">Поставщик <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost><xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.Properties%2A> не требует ссылки на сборку в коде.</span><span class="sxs-lookup"><span data-stu-id="c8099-168">The <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost><xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.Properties%2A> provider does not require a reference to the assembly in the code.</span></span>  
  
-   <span data-ttu-id="c8099-169">Можно разрабатывать код общих подпрограмм, способных работать в любой задаче, поскольку нет необходимости знать имя задачи во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="c8099-169">You can code generic routines that work for any task, because you do not have to know the name of the task at compile time.</span></span> <span data-ttu-id="c8099-170">Такие общие подпрограммы включают методы, в которых имя задачи передается методу, а код метода работает во всех задачах.</span><span class="sxs-lookup"><span data-stu-id="c8099-170">Such generic routines include methods where you pass in the name of the task to the method, and the method code works for all tasks.</span></span> <span data-ttu-id="c8099-171">Это удобный способ создания тестового кода.</span><span class="sxs-lookup"><span data-stu-id="c8099-171">This is a good method for writing test code.</span></span>  
  
 <span data-ttu-id="c8099-172">Приведение от класса <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> к классу, зависящему от задачи, позволяет достичь следующих преимуществ:</span><span class="sxs-lookup"><span data-stu-id="c8099-172">Casting from the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost> to the task-specific class has the following advantages:</span></span>  
  
-   <span data-ttu-id="c8099-173">Проект разрабатывается в среде Visual Studio, поэтому обеспечивается возможность автоматического завершения инструкций (с помощью технологии IntelliSense).</span><span class="sxs-lookup"><span data-stu-id="c8099-173">The Visual Studio project gives you statement completion (IntelliSense).</span></span>  
  
-   <span data-ttu-id="c8099-174">Код может работать быстрее.</span><span class="sxs-lookup"><span data-stu-id="c8099-174">The code may run faster.</span></span>  
  
-   <span data-ttu-id="c8099-175">Объекты, зависящие от задачи, обеспечивают применение раннего связывания и завершающую оптимизацию.</span><span class="sxs-lookup"><span data-stu-id="c8099-175">Task-specific objects enable early binding and the resulting optimizations.</span></span> <span data-ttu-id="c8099-176">Дополнительные сведения о раннем и позднем связывании см. в подразделе «Раннее и позднее связывание» в разделе «Основные понятия языка Visual Basic».</span><span class="sxs-lookup"><span data-stu-id="c8099-176">For more information about early and late binding, see the topic "Early and Late Binding" in Visual Basic Language Concepts.</span></span>  
  
 <span data-ttu-id="c8099-177">В следующем примере кода раскрывается понятие повторного использования кода задачи.</span><span class="sxs-lookup"><span data-stu-id="c8099-177">The following code example expands on the concept of reusing task code.</span></span> <span data-ttu-id="c8099-178">Вместо приведения задач к конкретным эквивалентным им классам в этом примере кода показано, как привести исполняемый файл к объекту <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>, а затем воспользоваться коллекцией <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.Properties%2A> для написания общего кода для всех задач.</span><span class="sxs-lookup"><span data-stu-id="c8099-178">Instead of casting tasks to their specific class equivalents, the code example shows how to cast the executable to a <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>, and then uses the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost.Properties%2A> to write generic code against all the tasks.</span></span>  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
  
namespace Microsoft.SqlServer.Dts.Samples  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      Package package = new Package();  
  
      string[] tasks = { "STOCK:SQLTask", "STOCK:ScriptTask",   
        "STOCK:ExecuteProcessTask", "STOCK:PipelineTask",   
        "STOCK:FTPTask", "STOCK:SendMailTask", "STOCK:MSMQTask" };  
  
      foreach (string s in tasks)  
      {  
        TaskHost taskhost = package.Executables.Add(s) as TaskHost;  
        DtsProperties props = taskhost.Properties;  
        Console.WriteLine("Enumerating properties on " + taskhost.Name);  
        Console.WriteLine(" TaskHost.InnerObject is " + taskhost.InnerObject.ToString());  
        Console.WriteLine();  
  
        foreach (DtsProperty prop in props)  
        {  
          Console.WriteLine("Properties for " + prop.Name);  
          Console.WriteLine("Name : " + prop.Name);  
          Console.WriteLine("Type : " + prop.Type.ToString());  
          Console.WriteLine("Readable : " + prop.Get.ToString());  
          Console.WriteLine("Writable : " + prop.Set.ToString());  
          Console.WriteLine();  
        }  
      }  
      Console.Read();  
    }  
  }  
}  
```  
  
```vb  
Imports Microsoft.SqlServer.Dts.Runtime  
  
Module Module1  
  
  Sub Main()  
  
    Dim package As Package = New Package()  
  
    Dim tasks() As String = New String() {"STOCK:SQLTask", "STOCK:ScriptTask", _  
              "STOCK:ExecuteProcessTask", "STOCK:PipelineTask", _  
              "STOCK:FTPTask", "STOCK:SendMailTask", "STOCK:MSMQTask"}  
  
    For Each s As String In tasks  
  
      Dim taskhost As TaskHost = CType(package.Executables.Add(s), TaskHost)  
      Dim props As DtsProperties = taskhost.Properties  
      Console.WriteLine("Enumerating properties on " & taskhost.Name)  
      Console.WriteLine(" TaskHost.InnerObject is " & taskhost.InnerObject.ToString())  
      Console.WriteLine()  
  
      For Each prop As DtsProperty In props  
        Console.WriteLine("Properties for " + prop.Name)  
        Console.WriteLine(" Name : " + prop.Name)  
        Console.WriteLine(" Type : " + prop.Type.ToString())  
        Console.WriteLine(" Readable : " + prop.Get.ToString())  
        Console.WriteLine(" Writable : " + prop.Set.ToString())  
        Console.WriteLine()  
      Next  
  
    Next  
    Console.Read()  
  
  End Sub  
  
End Module  
```  
  
## <a name="external-resources"></a><span data-ttu-id="c8099-179">Внешние ресурсы</span><span class="sxs-lookup"><span data-stu-id="c8099-179">External Resources</span></span>  
 <span data-ttu-id="c8099-180">Запись в блоге [EzAPI — обновление для SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=243223) на сайте blogs.msdn.com.</span><span class="sxs-lookup"><span data-stu-id="c8099-180">Blog entry, [EzAPI - Updated for SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=243223), on blogs.msdn.com.</span></span>  
  
<span data-ttu-id="c8099-181">![Значок Integration Services (маленький)](../media/dts-16.gif "Значок служб Integration Services (маленький)")  **следит за обновлениями Integration Services**</span><span class="sxs-lookup"><span data-stu-id="c8099-181">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="c8099-182">Чтобы загрузить новейшую документацию, статьи, образцы и видеоматериалы корпорации Майкрософт, а также лучшие решения участников сообщества, посетите страницу служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] на сайте MSDN:</span><span class="sxs-lookup"><span data-stu-id="c8099-182">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="c8099-183">Посетить страницу «Службы Integration Services» на сайте MSDN</span><span class="sxs-lookup"><span data-stu-id="c8099-183">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="c8099-184">Чтобы получать автоматические уведомления об этих обновлениях, подпишитесь на RSS-каналы, предлагаемые на этой странице.</span><span class="sxs-lookup"><span data-stu-id="c8099-184">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8099-185">См. также:</span><span class="sxs-lookup"><span data-stu-id="c8099-185">See Also</span></span>  
 [<span data-ttu-id="c8099-186">Соединение задач программным образом</span><span class="sxs-lookup"><span data-stu-id="c8099-186">Connecting Tasks Programmatically</span></span>](../building-packages-programmatically/connecting-tasks-programmatically.md)  
  
  
