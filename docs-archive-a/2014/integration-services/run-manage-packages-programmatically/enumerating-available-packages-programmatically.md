---
title: Программное перечисление доступных пакетов | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- programmatically enumerate packages [SSIS]
- existence testing [Integration Services]
- enumerating packages [Integration Services]
ms.assetid: 254ec7ee-d3ff-4361-8995-46e9b9c4dc95
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 053f2e598b1cc18e68ee2182092188367ee7f10c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729557"
---
# <a name="enumerating-available-packages-programmatically"></a><span data-ttu-id="5d848-102">Программное перечисление доступных пакетов</span><span class="sxs-lookup"><span data-stu-id="5d848-102">Enumerating Available Packages Programmatically</span></span>
  <span data-ttu-id="5d848-103">Во время обработки пакетов служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] программным путем может потребоваться определить, существует ли отдельный пакет или папка, или перечислить сохраненные пакеты, которые доступны для загрузки и выполнения.</span><span class="sxs-lookup"><span data-stu-id="5d848-103">As you work programmatically with [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages, you may want to determine whether an individual package or folder exists, or to enumerate the saved packages that are available to load and execute.</span></span> <span data-ttu-id="5d848-104">Класс <xref:Microsoft.SqlServer.Dts.Runtime.Application> из пространства имен <xref:Microsoft.SqlServer.Dts.Runtime> предоставляет разнообразные методы, выполняющие эти требования.</span><span class="sxs-lookup"><span data-stu-id="5d848-104">The <xref:Microsoft.SqlServer.Dts.Runtime.Application> class of the <xref:Microsoft.SqlServer.Dts.Runtime> namespace provides a variety of methods to satisfy these requirements.</span></span>  
  
##  <a name="determining-whether-a-package-or-folder-exists"></a><a name="exists"></a> <span data-ttu-id="5d848-105">Определение существования пакета или папки</span><span class="sxs-lookup"><span data-stu-id="5d848-105">Determining Whether a Package or Folder Exists</span></span>  
 <span data-ttu-id="5d848-106">Чтобы определить программно, существует ли сохраненный пакет, вызовите один из следующих методов перед тем, как пытаться загрузить и выполнить пакет.</span><span class="sxs-lookup"><span data-stu-id="5d848-106">To determine programmatically whether a saved package exists, call one of the following methods before attempting to load and run it:</span></span>  
  
|<span data-ttu-id="5d848-107">Место хранения</span><span class="sxs-lookup"><span data-stu-id="5d848-107">Storage Location</span></span>|<span data-ttu-id="5d848-108">Вызываемый метод</span><span class="sxs-lookup"><span data-stu-id="5d848-108">Method to Call</span></span>|  
|----------------------|--------------------|  
|<span data-ttu-id="5d848-109">Хранилище пакетов служб SSIS</span><span class="sxs-lookup"><span data-stu-id="5d848-109">SSIS Package Store</span></span>|<xref:Microsoft.SqlServer.Dts.Runtime.Application.ExistsOnDtsServer%2A>|  
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|<xref:Microsoft.SqlServer.Dts.Runtime.Application.ExistsOnSqlServer%2A>|  
  
 <span data-ttu-id="5d848-110">Чтобы определить программно, существует ли папка, прежде чем пытаться перечислить сохраненные в ней пакеты, вызовите один из следующих методов.</span><span class="sxs-lookup"><span data-stu-id="5d848-110">To determine programmatically whether a folder exists before attempting to list the packages stored in it, call one of the following methods:</span></span>  
  
|<span data-ttu-id="5d848-111">Место хранения</span><span class="sxs-lookup"><span data-stu-id="5d848-111">Storage Location</span></span>|<span data-ttu-id="5d848-112">Вызываемый метод</span><span class="sxs-lookup"><span data-stu-id="5d848-112">Method to Call</span></span>|  
|----------------------|--------------------|  
|<span data-ttu-id="5d848-113">Хранилище пакетов служб SSIS</span><span class="sxs-lookup"><span data-stu-id="5d848-113">SSIS Package Store</span></span>|<xref:Microsoft.SqlServer.Dts.Runtime.Application.FolderExistsOnDtsServer%2A>|  
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|<xref:Microsoft.SqlServer.Dts.Runtime.Application.FolderExistsOnSqlServer%2A>|  
  
 [<span data-ttu-id="5d848-114">Вверх</span><span class="sxs-lookup"><span data-stu-id="5d848-114">Back to top</span></span>](#top)  
  
##  <a name="enumerating-available-packages"></a><a name="listing"></a> <span data-ttu-id="5d848-115">Перечисление доступных пакетов</span><span class="sxs-lookup"><span data-stu-id="5d848-115">Enumerating Available Packages</span></span>  
 <span data-ttu-id="5d848-116">Чтобы получить программным путем список сохраненных пакетов, вызовите один из следующих методов.</span><span class="sxs-lookup"><span data-stu-id="5d848-116">To obtain a list of saved packages programmatically, call one of the following methods:</span></span>  
  
|<span data-ttu-id="5d848-117">Место хранения</span><span class="sxs-lookup"><span data-stu-id="5d848-117">Storage Location</span></span>|<span data-ttu-id="5d848-118">Вызываемый метод</span><span class="sxs-lookup"><span data-stu-id="5d848-118">Method to Call</span></span>|  
|----------------------|--------------------|  
|<span data-ttu-id="5d848-119">Хранилище пакетов служб SSIS</span><span class="sxs-lookup"><span data-stu-id="5d848-119">SSIS Package Store</span></span>|<xref:Microsoft.SqlServer.Dts.Runtime.Application.GetDtsServerPackageInfos%2A>|  
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|<xref:Microsoft.SqlServer.Dts.Runtime.Application.GetPackageInfos%2A>|  
  
 <span data-ttu-id="5d848-120">Приложения командной строки в следующих образцах иллюстрируют использование этих методов.</span><span class="sxs-lookup"><span data-stu-id="5d848-120">The following samples are console applications that demonstrate the use of these methods.</span></span>  
  
###  <a name="example-ssis-package-store"></a><a name="listing_store"></a> <span data-ttu-id="5d848-121">Пример (хранилище пакетов служб SSIS)</span><span class="sxs-lookup"><span data-stu-id="5d848-121">Example (SSIS Package Store)</span></span>  
 <span data-ttu-id="5d848-122">Используйте метод <xref:Microsoft.SqlServer.Dts.Runtime.Application.GetDtsServerPackageInfos%2A> для перечисления пакетов, сохраненных в хранилище пакетов служб SSIS.</span><span class="sxs-lookup"><span data-stu-id="5d848-122">Use the <xref:Microsoft.SqlServer.Dts.Runtime.Application.GetDtsServerPackageInfos%2A> method to list packages stored in the SSIS Package Store.</span></span> <span data-ttu-id="5d848-123">Местом хранения по умолчанию, которое управляется хранилищем пакетов служб SSIS, является файловая система и MSDB.</span><span class="sxs-lookup"><span data-stu-id="5d848-123">The default storage locations that are managed by the SSIS Package store are File System and MSDB.</span></span> <span data-ttu-id="5d848-124">В этих местах можно создать дополнительные логические папки.</span><span class="sxs-lookup"><span data-stu-id="5d848-124">You can create additional logical folders within these locations.</span></span>  
  
```vb  
Imports Microsoft.SqlServer.Dts.Runtime  
  
Module Module1  
  
  Sub Main()  
  
    Dim sqlFolder As String  
    Dim sqlServer As String  
  
    Dim ssisApplication As Application  
    Dim sqlPackages As PackageInfos  
    Dim sqlPackage As PackageInfo  
  
    sqlServer = "."  
  
    ssisApplication = New Application()  
  
    ' Get packages stored in MSDB.  
    sqlFolder = "MSDB"  
    sqlPackages = ssisApplication.GetDtsServerPackageInfos(sqlFolder, sqlServer)  
    If sqlPackages.Count > 0 Then  
      Console.WriteLine("Packages stored in MSDB:")  
      For Each sqlPackage In sqlPackages  
        Console.WriteLine(sqlPackage.Name)  
      Next  
      Console.WriteLine()  
    End If  
  
    ' Get packages stored in the File System.  
    sqlFolder = "File System"  
    sqlPackages = ssisApplication.GetDtsServerPackageInfos(sqlFolder, sqlServer)  
    If sqlPackages.Count > 0 Then  
      Console.WriteLine("Packages stored in the File System:")  
      For Each sqlPackage In sqlPackages  
        Console.WriteLine(sqlPackage.Name)  
      Next  
    End If  
  
    Console.Read()  
  
  End Sub  
  
End Module  
```  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
  
namespace EnumeratePackagesSSIS_CS  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
  
      string sqlFolder;  
      string sqlServer;  
  
      Application ssisApplication;  
      PackageInfos sqlPackages;  
  
      sqlServer = ".";  
  
      ssisApplication = new Application();  
  
      // Get packages stored in MSDB.  
      sqlFolder = "MSDB";  
      sqlPackages = ssisApplication.GetDtsServerPackageInfos(sqlFolder, sqlServer);  
      if (sqlPackages.Count > 0)  
      {  
        Console.WriteLine("Packages stored in MSDB:");  
        foreach (PackageInfo sqlPackage in sqlPackages)  
        {  
          Console.WriteLine(sqlPackage.Name);  
        }  
        Console.WriteLine();  
      }  
  
      // Get packages stored in the File System.  
      sqlFolder = "File System";  
      sqlPackages = ssisApplication.GetDtsServerPackageInfos(sqlFolder, sqlServer);  
      if (sqlPackages.Count > 0)  
      {  
        Console.WriteLine("Packages stored in the File System:");  
        foreach (PackageInfo sqlPackage in sqlPackages)  
        {  
          Console.WriteLine(sqlPackage.Name);  
        }  
      }  
  
      Console.Read();  
  
    }  
  
  }  
  
}  
```  
  
 [<span data-ttu-id="5d848-125">Вверх</span><span class="sxs-lookup"><span data-stu-id="5d848-125">Back to top</span></span>](#top)  
  
###  <a name="example-sql-server"></a><a name="listing_sql"></a> <span data-ttu-id="5d848-126">Пример (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="5d848-126">Example (SQL Server)</span></span>  
 <span data-ttu-id="5d848-127">Используйте метод <xref:Microsoft.SqlServer.Dts.Runtime.Application.GetPackageInfos%2A> для перечисления пакетов служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], хранящихся в экземпляре [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5d848-127">Use the <xref:Microsoft.SqlServer.Dts.Runtime.Application.GetPackageInfos%2A> method to list [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages that are stored in an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
```vb  
Imports Microsoft.SqlServer.Dts.Runtime  
  
Module Module1  
  
  Sub Main()  
  
    Dim sqlFolder As String  
    Dim sqlServer As String  
    Dim sqlUser As String  
    Dim sqlPassword As String  
  
    Dim ssisApplication As Application  
    Dim sqlPackages As PackageInfos  
    Dim sqlPackage As PackageInfo  
  
    sqlFolder = String.Empty  
    sqlServer = "(local)"  
    sqlUser = String.Empty  
    sqlPassword = String.Empty  
  
    ssisApplication = New Application()  
  
    sqlPackages = ssisApplication.GetPackageInfos(sqlFolder, sqlServer, sqlUser, sqlPassword)  
  
    For Each sqlPackage In sqlPackages  
      Console.WriteLine(sqlPackage.Name)  
    Next  
  
    Console.Read()  
  
  End Sub  
  
End Module  
```  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
  
namespace EnumeratePackagesSql_CS  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
  
      string sqlFolder;  
      string sqlServer;  
      string sqlUser;  
      string sqlPassword;  
  
      Application ssisApplication;  
      PackageInfos sqlPackages;  
  
      sqlFolder = String.Empty;  
      sqlServer = "(local)";  
      sqlUser = String.Empty;  
      sqlPassword = String.Empty;  
  
      ssisApplication = new Application();  
  
      sqlPackages = ssisApplication.GetPackageInfos(sqlFolder, sqlServer, sqlUser, sqlPassword);  
  
      foreach (PackageInfo sqlPackage in sqlPackages)  
      {  
        Console.WriteLine(sqlPackage.Name);  
      }  
  
      Console.Read();  
  
    }  
  }  
}  
```  
  
 [<span data-ttu-id="5d848-128">Вверх</span><span class="sxs-lookup"><span data-stu-id="5d848-128">Back to top</span></span>](#top)  
  
<span data-ttu-id="5d848-129">![Значок Integration Services (маленький)](../media/dts-16.gif "Значок служб Integration Services (маленький)")  **следит за обновлениями Integration Services**</span><span class="sxs-lookup"><span data-stu-id="5d848-129">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="5d848-130">Чтобы загрузить новейшую документацию, статьи, образцы и видеоматериалы корпорации Майкрософт, а также лучшие решения участников сообщества, посетите страницу служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] на сайте MSDN:</span><span class="sxs-lookup"><span data-stu-id="5d848-130">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="5d848-131">Посетить страницу «Службы Integration Services» на сайте MSDN</span><span class="sxs-lookup"><span data-stu-id="5d848-131">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="5d848-132">Чтобы получать автоматические уведомления об этих обновлениях, подпишитесь на RSS-каналы, предлагаемые на этой странице.</span><span class="sxs-lookup"><span data-stu-id="5d848-132">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d848-133">См. также:</span><span class="sxs-lookup"><span data-stu-id="5d848-133">See Also</span></span>  
 [<span data-ttu-id="5d848-134">Управление пакетами (службы SSIS)</span><span class="sxs-lookup"><span data-stu-id="5d848-134">Package Management &#40;SSIS Service&#41;</span></span>](../service/package-management-ssis-service.md)  
  
  
