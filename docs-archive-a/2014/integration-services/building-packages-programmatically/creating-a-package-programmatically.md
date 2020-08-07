---
title: Создание пакета программным образом | Документы Майкрософт
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
- SSIS packages, creating
- Integration Services packages, creating
- packages [Integration Services], creating
- SQL Server Integration Services packages, creating
ms.assetid: e44bcc70-32d3-43e8-a84b-29aef819d5d3
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1159784fc95dd86d9d33c4354291cc7c52812982
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731974"
---
# <a name="creating-a-package-programmatically"></a><span data-ttu-id="e6562-102">Создание пакета программным способом</span><span class="sxs-lookup"><span data-stu-id="e6562-102">Creating a Package Programmatically</span></span>
  <span data-ttu-id="e6562-103">Объект <xref:Microsoft.SqlServer.Dts.Runtime.Package> представляет собой контейнер верхнего уровня для всех остальных объектов в решении служб [!INCLUDE[ssIS](../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e6562-103">The <xref:Microsoft.SqlServer.Dts.Runtime.Package> object is the top-level container for all other objects in an [!INCLUDE[ssIS](../../includes/ssis-md.md)] project solution.</span></span> <span data-ttu-id="e6562-104">Пакет, являющийся контейнером верхнего уровня, создается в качестве первого объекта, а последующие объекты добавляются в него и затем выполняются в контексте пакета.</span><span class="sxs-lookup"><span data-stu-id="e6562-104">As the top-level container, the package is the first object created, and subsequent objects are added to it, and then executed within the context of the package.</span></span> <span data-ttu-id="e6562-105">Сам пакет перемещения или преобразования данных не осуществляет.</span><span class="sxs-lookup"><span data-stu-id="e6562-105">The package itself does not move or transform data.</span></span> <span data-ttu-id="e6562-106">Для выполнения этих функций используются задачи, содержащиеся в пакете.</span><span class="sxs-lookup"><span data-stu-id="e6562-106">The package relies on the tasks it contains to perform the work.</span></span> <span data-ttu-id="e6562-107">Задачи выполняют основную работу пакета. Они определяют функциональность пакета.</span><span class="sxs-lookup"><span data-stu-id="e6562-107">Tasks perform most of the work performed by a package, and define the functionality of a package.</span></span> <span data-ttu-id="e6562-108">Пакет создается и выполняется всего тремя строками кода, однако к нему могут быть добавлены различные задачи и объекты <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager>, что обеспечивает дополнительную функциональность пакета.</span><span class="sxs-lookup"><span data-stu-id="e6562-108">A package is created and executed with just three lines of code, but various tasks and <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> objects are added to give additional functionality to your package.</span></span> <span data-ttu-id="e6562-109">В этом разделе описывается программное создание пакета.</span><span class="sxs-lookup"><span data-stu-id="e6562-109">This section discusses how to programmatically create a package.</span></span> <span data-ttu-id="e6562-110">В нем не содержатся сведения о создании задач или диспетчера соединений <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager>.</span><span class="sxs-lookup"><span data-stu-id="e6562-110">It does not provide information about how to create the tasks or the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager>.</span></span> <span data-ttu-id="e6562-111">Эти темы рассматриваются в последующих разделах.</span><span class="sxs-lookup"><span data-stu-id="e6562-111">These are covered in later sections.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e6562-112">Пример</span><span class="sxs-lookup"><span data-stu-id="e6562-112">Example</span></span>  
 <span data-ttu-id="e6562-113">При написании кода с использованием интегрированной среды разработки Visual Studio IDE необходима ссылка на библиотеку Microsoft.SqlServer.ManagedDTS.DLL, на которую ссылается инструкция `using` (`Imports` в среде Visual Basic .NET), включающая пространство имен Microsoft.SqlServer.Dts.Runtime.</span><span class="sxs-lookup"><span data-stu-id="e6562-113">To write code using the Visual Studio IDE, a reference to Microsoft.SqlServer.ManagedDTS.DLL is required in order to create a `using` statement (`Imports` in Visual Basic .NET) to the Microsoft.SqlServer.Dts.Runtime.</span></span> <span data-ttu-id="e6562-114">В следующем образце кода демонстрируется создание пустого пакета.</span><span class="sxs-lookup"><span data-stu-id="e6562-114">The following code sample demonstrates creating an empty package.</span></span>  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
  
namespace Microsoft.SqlServer.Dts.Samples  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      Package package;  
      package = new Package();  
    }  
  }  
}  
```  
  
```vb  
Imports Microsoft.SqlServer.Dts.Runtime  
  
Module Module1  
  
  Sub Main()  
  
    Dim package As Package  
    package = New Package  
  
  End Sub  
  
End Module  
```  
  
 <span data-ttu-id="e6562-115">Чтобы скомпилировать и выполнить образец, нажмите клавишу F5 в среде Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="e6562-115">To compile and run the sample, press F5 in Visual Studio.</span></span> <span data-ttu-id="e6562-116">Чтобы выполнить сборку кода с использованием компилятора C# **csc.exe** в командной строке, используйте следующие команды и ссылки на файлы, заменив заполнитель *\<filename>* именем файла CS или VB и задав имя выходного файла *\<outputfilename>* по своему усмотрению.</span><span class="sxs-lookup"><span data-stu-id="e6562-116">To build the code using the C# compiler, **csc.exe**, at the command prompt to compile, use the following command and file references, replacing the *\<filename>* with the name of the .cs or .vb file, and giving it an *\<outputfilename>* of your choice.</span></span>  
  
 <span data-ttu-id="e6562-117">**csc /target:library /out: \<outputfilename>.dll \<filename>.cs /r:Microsoft.SqlServer.Managed DTS.dll" /r:System.dll**</span><span class="sxs-lookup"><span data-stu-id="e6562-117">**csc /target:library /out: \<outputfilename>.dll \<filename>.cs /r:Microsoft.SqlServer.Managed DTS.dll" /r:System.dll**</span></span>  
  
 <span data-ttu-id="e6562-118">Чтобы выполнить сборку кода с помощью компилятора среды Visual Basic .NET **vbc.exe**, в командной строке используйте следующие команды и ссылки на файлы.</span><span class="sxs-lookup"><span data-stu-id="e6562-118">To build the code using the Visual Basic .NET compiler, **vbc.exe**, at the command prompt to compile, use the following command and file references.</span></span>  
  
 <span data-ttu-id="e6562-119">**vbc /target:library /out: \<outputfilename>.dll \<filename>.vb /r:Microsoft.SqlServer.Managed DTS.dll" /r:System.dll**</span><span class="sxs-lookup"><span data-stu-id="e6562-119">**vbc /target:library /out: \<outputfilename>.dll \<filename>.vb /r:Microsoft.SqlServer.Managed DTS.dll" /r:System.dll**</span></span>  
  
 <span data-ttu-id="e6562-120">Можно также создать пакет, загрузив существующий пакет, сохраненный на диске, в файловой системе или в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e6562-120">You can also create a package by loading an existing package that was saved on disk, in the file system, or to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="e6562-121">Отличие состоит в том, что сначала создается объект <xref:Microsoft.SqlServer.Dts.Runtime.Application>, а затем объект пакета заполняется одним из перегруженных методов приложения: методом `LoadPackage` для неструктурированных файлов, методом `LoadFromSQLServer` для пакетов, сохраненных в службах [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], или методом <xref:Microsoft.SqlServer.Dts.Runtime.Application.LoadFromDtsServer%2A> для пакетов, сохраненных в файловой системе.</span><span class="sxs-lookup"><span data-stu-id="e6562-121">The difference is that the <xref:Microsoft.SqlServer.Dts.Runtime.Application> object is first created, and then the package object is filled by one of the Application's overloaded methods: `LoadPackage` for flat files, `LoadFromSQLServer` for packages saved to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], or <xref:Microsoft.SqlServer.Dts.Runtime.Application.LoadFromDtsServer%2A> for packages saved to the file system.</span></span> <span data-ttu-id="e6562-122">В следующем примере с диска загружается существующий пакет, а затем просматриваются некоторые свойства этого пакета.</span><span class="sxs-lookup"><span data-stu-id="e6562-122">The following example loads an existing package from disk, and then views several properties on the package.</span></span>  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
  
namespace Microsoft.SqlServer.Dts.Samples  
{  
  class ApplicationTests  
  {  
    static void Main(string[] args)  
    {  
      // The variable pkg points to the location of the  
      // ExecuteProcess package sample that was installed with  
      // the SSIS samples.  
      string pkg = @"C:\Program Files\Microsoft SQL Server\100\Samples\Integration Services" +  
        @"\Package Samples\ExecuteProcess Sample\ExecuteProcess\UsingExecuteProcess.dtsx";  
  
      Application app = new Application();  
      Package p = app.LoadPackage(pkg, null);  
  
      // Now that the package is loaded, we can query on  
      // its properties.  
      int n = p.Configurations.Count;  
      DtsProperty p2 = p.Properties["VersionGUID"];  
      DTSProtectionLevel pl = p.ProtectionLevel;  
  
      Console.WriteLine("Number of configurations = " + n.ToString());  
      Console.WriteLine("VersionGUID = " + (string)p2.GetValue(p));  
      Console.WriteLine("ProtectionLevel = " + pl.ToString());  
      Console.Read();  
    }  
  }  
}  
```  
  
```vb  
Imports Microsoft.SqlServer.Dts.Runtime  
  
Module ApplicationTests  
  
  Sub Main()  
  
    ' The variable pkg points to the location of the  
    ' ExecuteProcess package sample that was installed with  
    ' the SSIS samples.  
    Dim pkg As String = _  
      "C:\Program Files\Microsoft SQL Server\100\Samples\Integration Services" & _  
      "\Package Samples\ExecuteProcess Sample\ExecuteProcess\UsingExecuteProcess.dtsx"  
  
    Dim app As Application = New Application()  
    Dim p As Package = app.LoadPackage(pkg, Nothing)  
  
    ' Now that the package is loaded, we can query on  
    ' its properties.  
    Dim n As Integer = p.Configurations.Count  
    Dim p2 As DtsProperty = p.Properties("VersionGUID")  
    Dim pl As DTSProtectionLevel = p.ProtectionLevel  
  
    Console.WriteLine("Number of configurations = " & n.ToString())  
    Console.WriteLine("VersionGUID = " & CType(p2.GetValue(p), String))  
    Console.WriteLine("ProtectionLevel = " & pl.ToString())  
    Console.Read()  
  
  End Sub  
  
End Module  
```  
  
 <span data-ttu-id="e6562-123">**Образец вывода:**</span><span class="sxs-lookup"><span data-stu-id="e6562-123">**Sample Output:**</span></span>  
  
 `Number of configurations = 2`  
  
 `VersionGUID = {09016682-89B8-4406-AAC9-AF1E527FF50F}`  
  
 `ProtectionLevel = DontSaveSensitive`  
  
## <a name="external-resources"></a><span data-ttu-id="e6562-124">Внешние ресурсы</span><span class="sxs-lookup"><span data-stu-id="e6562-124">External Resources</span></span>  
  
-   <span data-ttu-id="e6562-125">Запись в блоге [Образец API-интерфейса ― источник OleDB и назначение OleDB](https://go.microsoft.com/fwlink/?LinkId=220824) на сайте blogs.msdn.com.</span><span class="sxs-lookup"><span data-stu-id="e6562-125">Blog entry, [API Sample - OleDB source and OleDB destination](https://go.microsoft.com/fwlink/?LinkId=220824), on blogs.msdn.com.</span></span>  
  
-   <span data-ttu-id="e6562-126">Запись в блоге [EzAPI — обновление для SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=243223) на сайте blogs.msdn.com.</span><span class="sxs-lookup"><span data-stu-id="e6562-126">Blog entry, [EzAPI - Updated for SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=243223), on blogs.msdn.com.</span></span>  
  
<span data-ttu-id="e6562-127">![Значок Integration Services (маленький)](../media/dts-16.gif "Значок служб Integration Services (маленький)")  **следит за обновлениями Integration Services**</span><span class="sxs-lookup"><span data-stu-id="e6562-127">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="e6562-128">Чтобы загрузить новейшую документацию, статьи, образцы и видеоматериалы корпорации Майкрософт, а также лучшие решения участников сообщества, посетите страницу служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] на сайте MSDN:</span><span class="sxs-lookup"><span data-stu-id="e6562-128">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="e6562-129">Посетить страницу «Службы Integration Services» на сайте MSDN</span><span class="sxs-lookup"><span data-stu-id="e6562-129">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="e6562-130">Чтобы получать автоматические уведомления об этих обновлениях, подпишитесь на RSS-каналы, предлагаемые на этой странице.</span><span class="sxs-lookup"><span data-stu-id="e6562-130">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6562-131">См. также:</span><span class="sxs-lookup"><span data-stu-id="e6562-131">See Also</span></span>  
 [<span data-ttu-id="e6562-132">Программное добавление задач</span><span class="sxs-lookup"><span data-stu-id="e6562-132">Adding Tasks Programmatically</span></span>](../building-packages-programmatically/adding-tasks-programmatically.md)  
  
  
