---
title: Программная загрузка и запуск локального пакета | Документы Майкрософт
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- Integration Services packages, running
- events [Integration Services], capturing
- packages [Integration Services], running
- loading packages programmatically
- Visual Basic [Integration Services]
- running packages [Integration Services]
- programmatically load and run packages [SSIS]
ms.assetid: 2f9fc1a8-a001-4c54-8c64-63b443725422
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a29faf623c02fea4fd8722c235f595f0fe4492e1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729554"
---
# <a name="loading-and-running-a-local-package-programmatically"></a><span data-ttu-id="f68c4-102">Программная загрузка и запуск локального пакета</span><span class="sxs-lookup"><span data-stu-id="f68c4-102">Loading and Running a Local Package Programmatically</span></span>
  <span data-ttu-id="f68c4-103">Пакеты служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] можно выполнять по мере необходимости или в заранее определенное время с помощью методов, описанных в разделе [Выполнение пакетов](../packages/run-integration-services-ssis-packages.md).</span><span class="sxs-lookup"><span data-stu-id="f68c4-103">You can run [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages as needed or at predetermined times by using the methods described in [Running Packages](../packages/run-integration-services-ssis-packages.md).</span></span> <span data-ttu-id="f68c4-104">Однако с помощью всего нескольких строк кода можно выполнить пакет из пользовательского приложения, такого как приложение Windows Forms, приложение командной строки, веб-форма ASP.NET, веб-служба или служба Windows.</span><span class="sxs-lookup"><span data-stu-id="f68c4-104">However, with only a few lines of code, you can also run a package from a custom application such as a Windows Forms application, a console application, an ASP.NET Web form or Web service, or a Windows service.</span></span>  
  
 <span data-ttu-id="f68c4-105">В данном разделе рассматриваются следующие темы.</span><span class="sxs-lookup"><span data-stu-id="f68c4-105">This topic discusses:</span></span>  
  
-   <span data-ttu-id="f68c4-106">Программная загрузка пакета.</span><span class="sxs-lookup"><span data-stu-id="f68c4-106">Loading a package programmatically</span></span>  
  
-   <span data-ttu-id="f68c4-107">Программное выполнение пакета.</span><span class="sxs-lookup"><span data-stu-id="f68c4-107">Running a package programmatically</span></span>  
  
 <span data-ttu-id="f68c4-108">Все методы, используемые в данном разделе для загрузки и выполнения пакетов, требуют наличия ссылки на сборку `Microsoft.SqlServer.ManagedDTS`.</span><span class="sxs-lookup"><span data-stu-id="f68c4-108">All of the methods used in this topic to load and run packages require a reference to the `Microsoft.SqlServer.ManagedDTS` assembly.</span></span> <span data-ttu-id="f68c4-109">После добавления ссылки в новый проект импортируйте пространство имен <xref:Microsoft.SqlServer.Dts.Runtime> с помощью инструкции `using` или `Imports`.</span><span class="sxs-lookup"><span data-stu-id="f68c4-109">After adding the reference in a new project, import the <xref:Microsoft.SqlServer.Dts.Runtime> namespace with a `using` or `Imports` statement.</span></span>  
  
## <a name="loading-a-package-programmatically"></a><span data-ttu-id="f68c4-110">Программная загрузка пакета</span><span class="sxs-lookup"><span data-stu-id="f68c4-110">Loading a Package Programmatically</span></span>  
 <span data-ttu-id="f68c4-111">Чтобы загрузить хранящийся локально или удаленно пакет на локальный компьютер программным путем, вызовите один из перечисленных далее методов.</span><span class="sxs-lookup"><span data-stu-id="f68c4-111">To load a package programmatically on the local computer, whether the package is stored locally or remotely, call one of the following methods:</span></span>  
  
|<span data-ttu-id="f68c4-112">Место хранения</span><span class="sxs-lookup"><span data-stu-id="f68c4-112">Storage Location</span></span>|<span data-ttu-id="f68c4-113">Вызываемый метод</span><span class="sxs-lookup"><span data-stu-id="f68c4-113">Method to Call</span></span>|  
|----------------------|--------------------|  
|<span data-ttu-id="f68c4-114">Файл</span><span class="sxs-lookup"><span data-stu-id="f68c4-114">File</span></span>|<xref:Microsoft.SqlServer.Dts.Runtime.Application.LoadPackage%2A>|  
|<span data-ttu-id="f68c4-115">Хранилище пакетов служб SSIS</span><span class="sxs-lookup"><span data-stu-id="f68c4-115">SSIS Package Store</span></span>|<xref:Microsoft.SqlServer.Dts.Runtime.Application.LoadFromDtsServer%2A>|  
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|<xref:Microsoft.SqlServer.Dts.Runtime.Application.LoadFromSqlServer%2A>|  
  
> [!IMPORTANT]  
>  <span data-ttu-id="f68c4-116">Методы класса <xref:Microsoft.SqlServer.Dts.Runtime.Application> для работы с хранилищем пакетов служб SSIS поддерживают только «.», localhost и имя сервера для локального сервера.</span><span class="sxs-lookup"><span data-stu-id="f68c4-116">The methods of the <xref:Microsoft.SqlServer.Dts.Runtime.Application> class for working with the SSIS Package Store only support ".", localhost, or the server name for the local server.</span></span> <span data-ttu-id="f68c4-117">Нельзя использовать имя «(local)».</span><span class="sxs-lookup"><span data-stu-id="f68c4-117">You cannot use "(local)".</span></span>  
  
## <a name="running-a-package-programmatically"></a><span data-ttu-id="f68c4-118">Программное выполнение пакета</span><span class="sxs-lookup"><span data-stu-id="f68c4-118">Running a Package Programmatically</span></span>  
 <span data-ttu-id="f68c4-119">Разработка пользовательского приложения в управляемом коде, которое выполняет пакет на локальном компьютере, осуществляется следующим образом.</span><span class="sxs-lookup"><span data-stu-id="f68c4-119">Developing a custom application in managed code that runs a package on the local computer requires the following approach.</span></span> <span data-ttu-id="f68c4-120">Приведенные здесь шаги проиллюстрированы образцом приложения командной строки, приведенным далее.</span><span class="sxs-lookup"><span data-stu-id="f68c4-120">The steps summarized here are demonstrated in the sample console application that follows.</span></span>  
  
#### <a name="to-run-a-package-on-the-local-computer-programmatically"></a><span data-ttu-id="f68c4-121">Программное выполнение пакета на локальном компьютере</span><span class="sxs-lookup"><span data-stu-id="f68c4-121">To run a package on the local computer programmatically</span></span>  
  
1.  <span data-ttu-id="f68c4-122">Запустите среду разработки Visual Studio и создайте новое приложение на языке программирования по своему выбору.</span><span class="sxs-lookup"><span data-stu-id="f68c4-122">Start the Visual Studio development environment, and create a new application in your preferred development language.</span></span> <span data-ttu-id="f68c4-123">В этом образце используется приложение командной строки. Однако выполнить пакет можно также из приложения Windows Forms, веб-формы ASP.NET, веб-службы или службы Windows.</span><span class="sxs-lookup"><span data-stu-id="f68c4-123">This example uses a console application; however you can also run a package from a Windows Forms application, an ASP.NET Web form or Web service, or a Windows service.</span></span>  
  
2.  <span data-ttu-id="f68c4-124">В меню **Проект** выберите пункт **Добавить ссылку** и добавьте ссылку на **Microsoft.SqlServer.ManagedDTS.dll**.</span><span class="sxs-lookup"><span data-stu-id="f68c4-124">On the **Project** menu, click **Add Reference** and add a reference to **Microsoft.SqlServer.ManagedDTS.dll**.</span></span> <span data-ttu-id="f68c4-125">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="f68c4-125">Click **OK**.</span></span>  
  
3.  <span data-ttu-id="f68c4-126">`Imports` `using` Чтобы импортировать пространство имен **Microsoft. SqlServer. DTS. Runtime** , используйте инструкцию Visual Basic или C#.</span><span class="sxs-lookup"><span data-stu-id="f68c4-126">Use the Visual Basic `Imports` statement or the C# `using` statement to import the **Microsoft.SqlServer.Dts.Runtime** namespace.</span></span>  
  
4.  <span data-ttu-id="f68c4-127">Добавьте следующий код в подпрограмму main.</span><span class="sxs-lookup"><span data-stu-id="f68c4-127">Add the following code in the main routine.</span></span> <span data-ttu-id="f68c4-128">В следующем примере представлено полное консольное приложения.</span><span class="sxs-lookup"><span data-stu-id="f68c4-128">The completed console application should look like the following example.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f68c4-129">Данный образец кода иллюстрирует загрузку пакета из файловой системы с помощью метода <xref:Microsoft.SqlServer.Dts.Runtime.Application.LoadPackage%2A>.</span><span class="sxs-lookup"><span data-stu-id="f68c4-129">The sample code demonstrates loading the package from the file system by using the <xref:Microsoft.SqlServer.Dts.Runtime.Application.LoadPackage%2A> method.</span></span> <span data-ttu-id="f68c4-130">Однако пакет можно загрузить также и из базы данных MSDB путем вызова метода <xref:Microsoft.SqlServer.Dts.Runtime.Application.LoadFromSqlServer%2A> или из пакета служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] путем вызова метода <xref:Microsoft.SqlServer.Dts.Runtime.Application.LoadFromDtsServer%2A>.</span><span class="sxs-lookup"><span data-stu-id="f68c4-130">However you can also load the package from the MSDB database by calling the <xref:Microsoft.SqlServer.Dts.Runtime.Application.LoadFromSqlServer%2A> method, or from the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package store by calling the <xref:Microsoft.SqlServer.Dts.Runtime.Application.LoadFromDtsServer%2A> method.</span></span>  
  
5.  <span data-ttu-id="f68c4-131">Запустите проект.</span><span class="sxs-lookup"><span data-stu-id="f68c4-131">Run the project.</span></span> <span data-ttu-id="f68c4-132">В образце кода выполняется пакет образца CalculatedColumns, который устанавливается вместе с образцами [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f68c4-132">The sample code executes the CalculatedColumns sample package that is installed with the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] samples.</span></span> <span data-ttu-id="f68c4-133">Результат выполнения пакета отображается в консольном окне.</span><span class="sxs-lookup"><span data-stu-id="f68c4-133">The result of package execution is displayed in the console window.</span></span>  
  
### <a name="sample-code"></a><span data-ttu-id="f68c4-134">Пример кода</span><span class="sxs-lookup"><span data-stu-id="f68c4-134">Sample Code</span></span>  
  
```vb  
Imports Microsoft.SqlServer.Dts.Runtime  
  
Module Module1  
  
  Sub Main()  
  
    Dim pkgLocation As String  
    Dim pkg As New Package  
    Dim app As New Application  
    Dim pkgResults As DTSExecResult  
  
    pkgLocation = _  
      "C:\Program Files\Microsoft SQL Server\100\Samples\Integration Services" & _  
      "\Package Samples\CalculatedColumns Sample\CalculatedColumns\CalculatedColumns.dtsx"  
    pkg = app.LoadPackage(pkgLocation, Nothing)  
    pkgResults = pkg.Execute()  
  
    Console.WriteLine(pkgResults.ToString())  
    Console.ReadKey()  
  
  End Sub  
  
End Module  
```  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
  
namespace RunFromClientAppCS  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      string pkgLocation;  
      Package pkg;  
      Application app;  
      DTSExecResult pkgResults;  
  
      pkgLocation =  
        @"C:\Program Files\Microsoft SQL Server\100\Samples\Integration Services" +  
        @"\Package Samples\CalculatedColumns Sample\CalculatedColumns\CalculatedColumns.dtsx";  
      app = new Application();  
      pkg = app.LoadPackage(pkgLocation, null);  
      pkgResults = pkg.Execute();  
  
      Console.WriteLine(pkgResults.ToString());  
      Console.ReadKey();  
    }  
  }  
}  
```  
  
## <a name="capturing-events-from-a-running-package"></a><span data-ttu-id="f68c4-135">Перехват событий в выполняющемся пакете</span><span class="sxs-lookup"><span data-stu-id="f68c4-135">Capturing Events from a Running Package</span></span>  
 <span data-ttu-id="f68c4-136">Когда пакет запускается программно, как показано в предыдущем образце, может понадобиться также перехватить ошибки и другие события, возникающие по мере выполнения пакета.</span><span class="sxs-lookup"><span data-stu-id="f68c4-136">When you run a package programmatically as shown in the preceding sample, you may also want to capture errors and other events that occur as the package executes.</span></span> <span data-ttu-id="f68c4-137">Это можно сделать, добавив класс, порожденный из класса <xref:Microsoft.SqlServer.Dts.Runtime.DefaultEvents>, и передав ссылку на этот класс при загрузке пакета.</span><span class="sxs-lookup"><span data-stu-id="f68c4-137">You can accomplish this by adding a class that inherits from the <xref:Microsoft.SqlServer.Dts.Runtime.DefaultEvents> class, and by passing a reference to that class when you load the package.</span></span> <span data-ttu-id="f68c4-138">Хотя следующий пример перехватывает только событие <xref:Microsoft.SqlServer.Dts.Runtime.DefaultEvents.OnError%2A>, существует много других событий, которые позволяет перехватывать класс <xref:Microsoft.SqlServer.Dts.Runtime.DefaultEvents>.</span><span class="sxs-lookup"><span data-stu-id="f68c4-138">Although the following example captures only the <xref:Microsoft.SqlServer.Dts.Runtime.DefaultEvents.OnError%2A> event, there are many other events that the <xref:Microsoft.SqlServer.Dts.Runtime.DefaultEvents> class lets you capture.</span></span>  
  
#### <a name="to-run-a-package-on-the-local-computer-programmatically-and-capture-package-events"></a><span data-ttu-id="f68c4-139">Программное выполнение пакета на локальном компьютере и перехват событий пакета</span><span class="sxs-lookup"><span data-stu-id="f68c4-139">To run a package on the local computer programmatically and capture package events</span></span>  
  
1.  <span data-ttu-id="f68c4-140">Пройдите по шагам в предыдущем примере, чтобы создать проект для этого примера.</span><span class="sxs-lookup"><span data-stu-id="f68c4-140">Follow the steps in the preceding example to create a project for this example.</span></span>  
  
2.  <span data-ttu-id="f68c4-141">Добавьте следующий код в подпрограмму main.</span><span class="sxs-lookup"><span data-stu-id="f68c4-141">Add the following code in the main routine.</span></span> <span data-ttu-id="f68c4-142">В следующем примере представлено полное консольное приложения.</span><span class="sxs-lookup"><span data-stu-id="f68c4-142">The completed console application should look like the following example.</span></span>  
  
3.  <span data-ttu-id="f68c4-143">Запустите проект.</span><span class="sxs-lookup"><span data-stu-id="f68c4-143">Run the project.</span></span> <span data-ttu-id="f68c4-144">В образце кода выполняется пакет образца CalculatedColumns, который устанавливается вместе с образцами [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f68c4-144">The sample code executes the CalculatedColumns sample package that is installed with the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] samples.</span></span> <span data-ttu-id="f68c4-145">Результат выполнения пакета отображается в консольном окне вместе с сообщениями о любых возникших ошибках.</span><span class="sxs-lookup"><span data-stu-id="f68c4-145">The result of package execution is displayed in the console window, along with any errors that occur.</span></span>  
  
### <a name="sample-code"></a><span data-ttu-id="f68c4-146">Пример кода</span><span class="sxs-lookup"><span data-stu-id="f68c4-146">Sample Code</span></span>  
  
```vb  
Imports Microsoft.SqlServer.Dts.Runtime  
  
Module Module1  
  
  Sub Main()  
  
    Dim pkgLocation As String  
    Dim pkg As New Package  
    Dim app As New Application  
    Dim pkgResults As DTSExecResult  
  
    Dim eventListener As New EventListener()  
  
    pkgLocation = _  
      "C:\Program Files\Microsoft SQL Server\100\Samples\Integration Services" & _  
      "\Package Samples\CalculatedColumns Sample\CalculatedColumns\CalculatedColumns.dtsx"  
    pkg = app.LoadPackage(pkgLocation, eventListener)  
    pkgResults = pkg.Execute(Nothing, Nothing, eventListener, Nothing, Nothing)  
  
    Console.WriteLine(pkgResults.ToString())  
    Console.ReadKey()  
  
  End Sub  
  
End Module  
  
Class EventListener  
  Inherits DefaultEvents  
  
  Public Overrides Function OnError(ByVal source As Microsoft.SqlServer.Dts.Runtime.DtsObject, _  
    ByVal errorCode As Integer, ByVal subComponent As String, ByVal description As String, _  
    ByVal helpFile As String, ByVal helpContext As Integer, _  
    ByVal idofInterfaceWithError As String) As Boolean  
  
    ' Add application-specific diagnostics here.  
    Console.WriteLine("Error in {0}/{1} : {2}", source, subComponent, description)  
    Return False  
  
  End Function  
  
End Class  
```  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
  
namespace RunFromClientAppWithEventsCS  
{  
  class MyEventListener : DefaultEvents  
  {  
    public override bool OnError(DtsObject source, int errorCode, string subComponent,   
      string description, string helpFile, int helpContext, string idofInterfaceWithError)  
    {  
      // Add application-specific diagnostics here.  
      Console.WriteLine("Error in {0}/{1} : {2}", source, subComponent, description);  
      return false;  
    }  
  }  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      string pkgLocation;  
      Package pkg;  
      Application app;  
      DTSExecResult pkgResults;  
  
      MyEventListener eventListener = new MyEventListener();  
  
      pkgLocation =  
        @"C:\Program Files\Microsoft SQL Server\100\Samples\Integration Services" +  
        @"\Package Samples\CalculatedColumns Sample\CalculatedColumns\CalculatedColumns.dtsx";  
      app = new Application();  
      pkg = app.LoadPackage(pkgLocation, eventListener);  
      pkgResults = pkg.Execute(null, null, eventListener, null, null);  
  
      Console.WriteLine(pkgResults.ToString());  
      Console.ReadKey();  
    }  
  }  
}  
```  
  
<span data-ttu-id="f68c4-147">![Значок Integration Services (маленький)](../media/dts-16.gif "Значок служб Integration Services (маленький)")  **следит за обновлениями Integration Services**</span><span class="sxs-lookup"><span data-stu-id="f68c4-147">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="f68c4-148">Чтобы загрузить новейшую документацию, статьи, образцы и видеоматериалы корпорации Майкрософт, а также лучшие решения участников сообщества, посетите страницу служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] на сайте MSDN:</span><span class="sxs-lookup"><span data-stu-id="f68c4-148">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="f68c4-149">Посетить страницу «Службы Integration Services» на сайте MSDN</span><span class="sxs-lookup"><span data-stu-id="f68c4-149">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="f68c4-150">Чтобы получать автоматические уведомления об этих обновлениях, подпишитесь на RSS-каналы, предлагаемые на этой странице.</span><span class="sxs-lookup"><span data-stu-id="f68c4-150">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f68c4-151">См. также:</span><span class="sxs-lookup"><span data-stu-id="f68c4-151">See Also</span></span>  
 <span data-ttu-id="f68c4-152">[Основные сведения о различиях между локальным и удаленным выполнением](../run-manage-packages-programmatically/understanding-the-differences-between-local-and-remote-execution.md) </span><span class="sxs-lookup"><span data-stu-id="f68c4-152">[Understanding the Differences between Local and Remote Execution](../run-manage-packages-programmatically/understanding-the-differences-between-local-and-remote-execution.md) </span></span>  
 <span data-ttu-id="f68c4-153">[Программная загрузка и запуск удаленного пакета](../run-manage-packages-programmatically/loading-and-running-a-remote-package-programmatically.md) </span><span class="sxs-lookup"><span data-stu-id="f68c4-153">[Loading and Running a Remote Package Programmatically](../run-manage-packages-programmatically/loading-and-running-a-remote-package-programmatically.md) </span></span>  
 [<span data-ttu-id="f68c4-154">Загрузка выхода локального пакета</span><span class="sxs-lookup"><span data-stu-id="f68c4-154">Loading the Output of a Local Package</span></span>](../run-manage-packages-programmatically/loading-the-output-of-a-local-package.md)  
  
  
