---
title: Программная загрузка и запуск удаленного пакета | Документы Майкрософт
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- Integration Services packages, running
- packages [Integration Services], running
- remote packages [Integration Services]
ms.assetid: 9f6ef376-3408-46bf-b5fa-fc7b18c689c9
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 06565140ae8ea3603461e2944e242aa91213de47
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87740154"
---
# <a name="loading-and-running-a-remote-package-programmatically"></a><span data-ttu-id="4706b-102">Программная загрузка и запуск удаленного пакета</span><span class="sxs-lookup"><span data-stu-id="4706b-102">Loading and Running a Remote Package Programmatically</span></span>
  <span data-ttu-id="4706b-103">Чтобы выполнить удаленные пакеты с локального компьютера, на котором не установлены службы [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], запустите пакеты таким образом, чтобы они выполнялись на удаленном компьютере, на котором установлены службы [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4706b-103">To run remote packages from a local computer that does not have [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] installed, start the packages so that they run on the remote computer on which [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] is installed.</span></span> <span data-ttu-id="4706b-104">Чтобы запустить пакеты на удаленном компьютере с локального компьютера, понадобится агент [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], веб-служба или удаленный компонент.</span><span class="sxs-lookup"><span data-stu-id="4706b-104">You do this by having the local computer use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent, a Web service, or a remote component to start the packages on the remote computer.</span></span> <span data-ttu-id="4706b-105">Если попытаться запустить удаленные пакеты непосредственно с локального компьютера, пакеты будут загружены на локальный компьютер и будут запущены оттуда.</span><span class="sxs-lookup"><span data-stu-id="4706b-105">If you try to start the remote packages directly from the local computer, the packages will load onto and try to run from the local computer.</span></span> <span data-ttu-id="4706b-106">Если на локальном компьютере не установлены службы [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], запуск пакетов окажется невозможен.</span><span class="sxs-lookup"><span data-stu-id="4706b-106">If the local computer does not have [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] installed, the packages will not run.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4706b-107">Невозможно выполнять пакеты вне среды [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)] на клиентском компьютере, если не установлены службы [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]. Условия вашей лицензии на [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] могут не допускать установку служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] на дополнительных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="4706b-107">You cannot run packages outside [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)] on a client computer that does not have [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] installed, and the terms of your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] licensing might not let you install [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] on additional computers.</span></span> <span data-ttu-id="4706b-108">Службы [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] являются серверным компонентом и не могут устанавливаться на клиентских компьютерах.</span><span class="sxs-lookup"><span data-stu-id="4706b-108">[!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] is a server component and is not redistributable to client computers.</span></span>  
  
 <span data-ttu-id="4706b-109">В качестве альтернативы можно запустить удаленный пакет с локального компьютера, на котором установлены службы [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4706b-109">Alternately, you can run a remote package from a local computer that has [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] installed.</span></span> <span data-ttu-id="4706b-110">Дополнительные сведения см. в разделе [Программная загрузка и запуск локального пакета](../run-manage-packages-programmatically/loading-and-running-a-local-package-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="4706b-110">For more information, see [Loading and Running a Local Package Programmatically](../run-manage-packages-programmatically/loading-and-running-a-local-package-programmatically.md).</span></span>  
  
##  <a name="running-a-remote-package-on-the-remote-computer"></a><a name="top"></a> <span data-ttu-id="4706b-111">Запуск удаленного пакета на удаленном компьютере</span><span class="sxs-lookup"><span data-stu-id="4706b-111">Running a Remote Package on the Remote Computer</span></span>  
 <span data-ttu-id="4706b-112">Как упоминалось выше, существует несколько способов выполнения удаленного пакета на удаленном сервере.</span><span class="sxs-lookup"><span data-stu-id="4706b-112">As mentioned above, there are multiple ways in which you can run a remote package on a remote server:</span></span>  
  
-   [<span data-ttu-id="4706b-113">Использовать агент SQL Server, чтобы запустить удаленный пакет программным способом</span><span class="sxs-lookup"><span data-stu-id="4706b-113">Use SQL Server Agent to run the remote package programmatically</span></span>](#agent)  
  
-   [<span data-ttu-id="4706b-114">Использовать веб-службы или удаленный компонент, чтобы запустить удаленный пакет программным способом</span><span class="sxs-lookup"><span data-stu-id="4706b-114">Use a Web service or remote component to run the remote package programmatically</span></span>](#service)  
  
 <span data-ttu-id="4706b-115">Практически все методы, которые используются в этом разделе для загрузки и сохранения пакетов, требуют наличия ссылки на сборку `Microsoft.SqlServer.ManagedDTS`.</span><span class="sxs-lookup"><span data-stu-id="4706b-115">Almost all the methods that are used in this topic to load and save packages require a reference to the `Microsoft.SqlServer.ManagedDTS` assembly.</span></span> <span data-ttu-id="4706b-116">Исключением является ADO.NETый подход, продемонстрированный в этом разделе для исполнения хранимой процедуры **sp_start_job** , для которой требуется только ссылка на `System.Data` .</span><span class="sxs-lookup"><span data-stu-id="4706b-116">The exception is the ADO.NET approach demonstrated in this topic for executing the **sp_start_job** stored procedure, which requires only a reference to `System.Data`.</span></span> <span data-ttu-id="4706b-117">После добавления ссылки на сборку `Microsoft.SqlServer.ManagedDTS` в новый проект импортируйте пространство имен <xref:Microsoft.SqlServer.Dts.Runtime> с инструкцией `using` или `Imports`.</span><span class="sxs-lookup"><span data-stu-id="4706b-117">After you add the reference to the `Microsoft.SqlServer.ManagedDTS` assembly in a new project, import the <xref:Microsoft.SqlServer.Dts.Runtime> namespace with a `using` or `Imports` statement.</span></span>  
  
###  <a name="using-sql-server-agent-to-run-a-remote-package-programmatically-on-the-server"></a><a name="agent"></a> <span data-ttu-id="4706b-118">Использование агента SQL Server для выполнения удаленного пакета программным способом на сервере</span><span class="sxs-lookup"><span data-stu-id="4706b-118">Using SQL Server Agent to Run a Remote Package Programmatically on the Server</span></span>  
 <span data-ttu-id="4706b-119">В следующем образце кода демонстрируется, как программным способом использовать агент [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] для выполнения удаленного пакета на сервере.</span><span class="sxs-lookup"><span data-stu-id="4706b-119">The following code sample demonstrates how to programmatically use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to run a remote package on the server.</span></span> <span data-ttu-id="4706b-120">В образце кода вызывается системная хранимая процедура **sp_start_job**, которая запускает задание агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4706b-120">The code sample calls the system stored procedure, **sp_start_job**, which launches a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job.</span></span> <span data-ttu-id="4706b-121">Задание, запускаемое процедурой, называется `RunSSISPackage` и расположено на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="4706b-121">The job that the procedure launches is named `RunSSISPackage`, and this job is on the remote computer.</span></span> <span data-ttu-id="4706b-122">Затем задание `RunSSISPackage` запускает пакет на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="4706b-122">The `RunSSISPackage` job then runs the package on the remote computer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4706b-123">Значение возврата хранимой процедуры **sp_start_job** указывает, удалось ли хранимой процедуре успешно запустить задание агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4706b-123">The return value of the **sp_start_job** stored procedure indicates whether the stored procedure was able to start the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job successfully.</span></span> <span data-ttu-id="4706b-124">Значение возврата не указывает на успешное или неуспешное выполнение пакета.</span><span class="sxs-lookup"><span data-stu-id="4706b-124">The return value does not indicate whether the package succeeded or failed.</span></span>  
  
 <span data-ttu-id="4706b-125">Сведения об устранении неполадок в пакетах, запускаемых из агента заданий [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], см. в статье базы знаний [Пакет служб SSIS не выполняется при вызове пакета из шага задания агента SQL Server](https://support.microsoft.com/kb/918760).</span><span class="sxs-lookup"><span data-stu-id="4706b-125">For information on troubleshooting packages that are run from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs, see the Microsoft article, [An SSIS package does not run when you call the SSIS package from a SQL Server Agent job step](https://support.microsoft.com/kb/918760).</span></span>  
  
### <a name="sample-code"></a><span data-ttu-id="4706b-126">Пример кода</span><span class="sxs-lookup"><span data-stu-id="4706b-126">Sample Code</span></span>  
  
```vb  
Imports System.Data  
Imports System.Data.SqlClient  
  
Module Module1  
  
  Sub Main()  
  
    Dim jobConnection As SqlConnection  
    Dim jobCommand As SqlCommand  
    Dim jobReturnValue As SqlParameter  
    Dim jobParameter As SqlParameter  
    Dim jobResult As Integer  
  
    jobConnection = New SqlConnection("Data Source=(local);Initial Catalog=msdb;Integrated Security=SSPI")  
    jobCommand = New SqlCommand("sp_start_job", jobConnection)  
    jobCommand.CommandType = CommandType.StoredProcedure  
  
    jobReturnValue = New SqlParameter("@RETURN_VALUE", SqlDbType.Int)  
    jobReturnValue.Direction = ParameterDirection.ReturnValue  
    jobCommand.Parameters.Add(jobReturnValue)  
  
    jobParameter = New SqlParameter("@job_name", SqlDbType.VarChar)  
    jobParameter.Direction = ParameterDirection.Input  
    jobCommand.Parameters.Add(jobParameter)  
    jobParameter.Value = "RunSSISPackage"  
  
    jobConnection.Open()  
    jobCommand.ExecuteNonQuery()  
    jobResult = DirectCast(jobCommand.Parameters("@RETURN_VALUE").Value, Integer)  
    jobConnection.Close()  
  
    Select Case jobResult  
      Case 0  
        Console.WriteLine("SQL Server Agent job, RunSISSPackage, started successfully.")  
      Case Else  
        Console.WriteLine("SQL Server Agent job, RunSISSPackage, failed to start.")  
    End Select  
    Console.Read()  
  
  End Sub  
  
End Module  
```  
  
```csharp  
using System;  
using System.Data;  
using System.Data.SqlClient;  
  
namespace LaunchSSISPackageAgent_CS  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      SqlConnection jobConnection;  
      SqlCommand jobCommand;  
      SqlParameter jobReturnValue;  
      SqlParameter jobParameter;  
      int jobResult;  
  
      jobConnection = new SqlConnection("Data Source=(local);Initial Catalog=msdb;Integrated Security=SSPI");  
      jobCommand = new SqlCommand("sp_start_job", jobConnection);  
      jobCommand.CommandType = CommandType.StoredProcedure;  
  
      jobReturnValue = new SqlParameter("@RETURN_VALUE", SqlDbType.Int);  
      jobReturnValue.Direction = ParameterDirection.ReturnValue;  
      jobCommand.Parameters.Add(jobReturnValue);  
  
      jobParameter = new SqlParameter("@job_name", SqlDbType.VarChar);  
      jobParameter.Direction = ParameterDirection.Input;  
      jobCommand.Parameters.Add(jobParameter);  
      jobParameter.Value = "RunSSISPackage";  
  
      jobConnection.Open();  
      jobCommand.ExecuteNonQuery();  
      jobResult = (Int32)jobCommand.Parameters["@RETURN_VALUE"].Value;  
      jobConnection.Close();  
  
      switch (jobResult)  
      {  
        case 0:  
          Console.WriteLine("SQL Server Agent job, RunSISSPackage, started successfully.");  
          break;  
        default:  
          Console.WriteLine("SQL Server Agent job, RunSISSPackage, failed to start.");  
          break;  
      }  
      Console.Read();  
    }  
  }  
}  
```  
  
 
  
###  <a name="using-a-web-service-or-remote-component-to-run-a-remote-package-programmatically"></a><a name="service"></a> <span data-ttu-id="4706b-127">Использование веб-службы или удаленного компонента для запуска удаленного пакета программным способом</span><span class="sxs-lookup"><span data-stu-id="4706b-127">Using a Web Service or Remote Component to Run a Remote Package Programmatically</span></span>  
 <span data-ttu-id="4706b-128">В предыдущем решении для запуска пакетов программным способом на сервере не требовалось размещать какой-либо пользовательский код на сервере.</span><span class="sxs-lookup"><span data-stu-id="4706b-128">The previous solution for running packages programmatically on the server does not require any custom code on the server.</span></span> <span data-ttu-id="4706b-129">Однако, возможно, предпочтительным окажется решение, не зависящее от агента SQL Server для выполнения пакетов.</span><span class="sxs-lookup"><span data-stu-id="4706b-129">However, you may prefer a solution that does not rely on SQL Server Agent to execute packages.</span></span> <span data-ttu-id="4706b-130">В следующем примере демонстрируется веб-служба, которая может быть создана на сервере для локального запуска пакетов служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], и тестовое приложение, которое можно использовать для вызова веб-службы с клиентского компьютера.</span><span class="sxs-lookup"><span data-stu-id="4706b-130">The following example demonstrates a Web service that can be created on the server to start [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages locally, and a test application that can be used to call the Web service from a client computer.</span></span> <span data-ttu-id="4706b-131">Если предпочтительней создать удаленный компонент вместо веб-службы, можно использовать ту же логику кода после внесения незначительных изменений в удаленный компонент.</span><span class="sxs-lookup"><span data-stu-id="4706b-131">If you prefer to create a remote component instead of a Web service, you can use the same code logic with very few changes in a remote component.</span></span> <span data-ttu-id="4706b-132">Однако для удаленного компонента может потребоваться более сложная настройка, чем для веб-службы.</span><span class="sxs-lookup"><span data-stu-id="4706b-132">However a remote component may require more extensive configuration than a Web service.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="4706b-133">Веб-служба (с настройками по умолчанию для проверки подлинности и авторизации) обычно не имеет достаточных разрешений для доступа к SQL Server или файловой системе, чтобы загрузить и выполнить пакеты.</span><span class="sxs-lookup"><span data-stu-id="4706b-133">With its default settings for authentication and authorization, a Web service generally does not have sufficient permissions to access SQL Server or the file system to load and execute packages.</span></span> <span data-ttu-id="4706b-134">Возможно, потребуется назначить соответствующие разрешения для веб-службы путем настройки ее проверки подлинности и авторизации в файле **web.config** и назначения необходимых разрешений для доступа к базе данных и файловой системе.</span><span class="sxs-lookup"><span data-stu-id="4706b-134">You may have to assign appropriate permissions to the Web service by configuring its authentication and authorization settings in the **web.config** file and assigning database and file system permissions as appropriate.</span></span> <span data-ttu-id="4706b-135">Подробное обсуждение разрешений на доступ к базе данных и файловой системе из Интернета выходит за область этого раздела.</span><span class="sxs-lookup"><span data-stu-id="4706b-135">A complete discussion of Web, database, and file system permissions is beyond the scope of this topic.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="4706b-136">Методы класса <xref:Microsoft.SqlServer.Dts.Runtime.Application> для работы с хранилищем пакетов служб SSIS поддерживают только имена «.», localhost и имя сервера для локального сервера.</span><span class="sxs-lookup"><span data-stu-id="4706b-136">The methods of the <xref:Microsoft.SqlServer.Dts.Runtime.Application> class for working with the SSIS Package Store support only ".", localhost, or the server name for the local server.</span></span> <span data-ttu-id="4706b-137">Нельзя использовать имя «(local)».</span><span class="sxs-lookup"><span data-stu-id="4706b-137">You cannot use "(local)".</span></span>  
  
### <a name="sample-code"></a><span data-ttu-id="4706b-138">Пример кода</span><span class="sxs-lookup"><span data-stu-id="4706b-138">Sample Code</span></span>  
 <span data-ttu-id="4706b-139">В следующем образце кода демонстрируется, как создать и проверить веб-службу.</span><span class="sxs-lookup"><span data-stu-id="4706b-139">The following code samples show how to create and test the Web service.</span></span>  
  
#### <a name="creating-the-web-service"></a><span data-ttu-id="4706b-140">Создание веб-службы</span><span class="sxs-lookup"><span data-stu-id="4706b-140">Creating the Web Service</span></span>  
 <span data-ttu-id="4706b-141">Пакет служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] может быть загружен непосредственно из файла, непосредственно с сервера SQL Server либо из хранилища пакетов служб SSIS, которое управляет хранением пакетов в SQL Server и специальных папках файловой системы.</span><span class="sxs-lookup"><span data-stu-id="4706b-141">An [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package can be loaded directly from a file, directly from SQL Server, or from the SSIS Package Store, which manages package storage in both SQL Server and special file system folders.</span></span> <span data-ttu-id="4706b-142">Этот образец поддерживает все доступные параметры с помощью конструкции `Select Case` или `switch`, чтобы выбрать подходящий синтаксис для запуска пакета и соответствующего объединения его входных аргументов.</span><span class="sxs-lookup"><span data-stu-id="4706b-142">This sample supports all the available options by using a `Select Case` or `switch` construct to select the appropriate syntax for starting the package and to concatenate the input arguments appropriately.</span></span> <span data-ttu-id="4706b-143">Метод веб-службы LaunchPackage возвращает результат выполнения пакета как целое число вместо значения <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult>, чтобы для клиентских компьютеров не требовалась ссылка на какие-либо сборки служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4706b-143">The LaunchPackage Web service method returns the result of package execution as an integer instead of a <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult> value so that client computers do not require a reference to any [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] assemblies.</span></span>  
  
###### <a name="to-create-a-web-service-to-run-packages-on-the-server-programmatically"></a><span data-ttu-id="4706b-144">Создание веб-службы для запуска пакетов на сервере программным способом</span><span class="sxs-lookup"><span data-stu-id="4706b-144">To create a Web service to run packages on the server programmatically</span></span>  
  
1.  <span data-ttu-id="4706b-145">Откройте среду Visual Studio и создайте проект веб-службы на предпочитаемом языке программирования.</span><span class="sxs-lookup"><span data-stu-id="4706b-145">Open Visual Studio and create a Web service project in your preferred programming language.</span></span> <span data-ttu-id="4706b-146">В образце кода для проекта используется имя LaunchSSISPackageService.</span><span class="sxs-lookup"><span data-stu-id="4706b-146">The sample code uses the name LaunchSSISPackageService for the project.</span></span>  
  
2.  <span data-ttu-id="4706b-147">Добавьте ссылку на `Microsoft.SqlServer.ManagedDTS` и добавьте `Imports` `using` инструкцию или в файл кода для пространства имен **Microsoft. SqlServer. DTS. Runtime** .</span><span class="sxs-lookup"><span data-stu-id="4706b-147">Add a reference to `Microsoft.SqlServer.ManagedDTS` and add an `Imports` or `using` statement to the code file for the **Microsoft.SqlServer.Dts.Runtime** namespace.</span></span>  
  
3.  <span data-ttu-id="4706b-148">Вставьте образец кода из метода веб-службы LaunchPackage в класс.</span><span class="sxs-lookup"><span data-stu-id="4706b-148">Paste the sample code for the LaunchPackage Web service method into the class.</span></span> <span data-ttu-id="4706b-149">(В этом образце приводится полное содержимое окна кода.)</span><span class="sxs-lookup"><span data-stu-id="4706b-149">(The sample shows the whole contents of the code window.)</span></span>  
  
4.  <span data-ttu-id="4706b-150">Постройте и проверьте веб-службу, предоставив набор допустимых значений для входных аргументов метода LaunchPackage, указывающих на существующий пакет.</span><span class="sxs-lookup"><span data-stu-id="4706b-150">Build and test the Web service by providing a set of valid values for the input arguments of the LaunchPackage method that point to an existing package.</span></span> <span data-ttu-id="4706b-151">Например, если пакет package1.dtsx хранится на сервере в папке C:\My Packages, передайте «file» в качестве значения sourceType, «C:\My Packages» в качестве значения sourceLocation и «package1» (без расширения файла) в качестве значения packageName.</span><span class="sxs-lookup"><span data-stu-id="4706b-151">For example, if package1.dtsx is stored on the server in C:\My Packages, pass "file" as the value of the sourceType, "C:\My Packages" as the value of sourceLocation, and "package1" (without the extension) as the value of packageName.</span></span>  
  
```vb  
Imports System.Web  
Imports System.Web.Services  
Imports System.Web.Services.Protocols  
Imports Microsoft.SqlServer.Dts.Runtime  
Imports System.IO  
  
<WebService(Namespace:="http://dtsue/")> _  
<WebServiceBinding(ConformsTo:=WsiProfiles.BasicProfile1_1)> _  
<Global.Microsoft.VisualBasic.CompilerServices.DesignerGenerated()> _  
Public Class LaunchSSISPackageService  
  Inherits System.Web.Services.WebService  
  
  ' LaunchPackage Method Parameters:  
  ' 1. sourceType: file, sql, dts  
  ' 2. sourceLocation: file system folder, (none), logical folder  
  ' 3. packageName: for file system, ".dtsx" extension is appended  
  
  <WebMethod()> _  
  Public Function LaunchPackage( _  
    ByVal sourceType As String, _  
    ByVal sourceLocation As String, _  
    ByVal packageName As String) As Integer 'DTSExecResult  
  
    Dim packagePath As String  
    Dim myPackage As Package  
    Dim integrationServices As New Application  
  
    ' Combine path and file name.  
    packagePath = Path.Combine(sourceLocation, packageName)  
  
    Select Case sourceType  
      Case "file"  
        ' Package is stored as a file.  
        ' Add extension if not present.  
        If String.IsNullOrEmpty(Path.GetExtension(packagePath)) Then  
          packagePath = String.Concat(packagePath, ".dtsx")  
        End If  
        If File.Exists(packagePath) Then  
          myPackage = integrationServices.LoadPackage(packagePath, Nothing)  
        Else  
          Throw New ApplicationException( _  
            "Invalid file location: " & packagePath)  
        End If  
      Case "sql"  
        ' Package is stored in MSDB.  
        ' Combine logical path and package name.  
        If integrationServices.ExistsOnSqlServer(packagePath, ".", String.Empty, String.Empty) Then  
          myPackage = integrationServices.LoadFromSqlServer( _  
            packageName, "(local)", String.Empty, String.Empty, Nothing)  
        Else  
          Throw New ApplicationException( _  
            "Invalid package name or location: " & packagePath)  
        End If  
      Case "dts"  
        ' Package is managed by SSIS Package Store.  
        ' Default logical paths are File System and MSDB.  
        If integrationServices.ExistsOnDtsServer(packagePath, ".") Then  
          myPackage = integrationServices.LoadFromDtsServer(packagePath, "localhost", Nothing)  
        Else  
          Throw New ApplicationException( _  
            "Invalid package name or location: " & packagePath)  
        End If  
      Case Else  
        Throw New ApplicationException( _  
          "Invalid sourceType argument: valid values are 'file', 'sql', and 'dts'.")  
    End Select  
  
    Return myPackage.Execute()  
  
  End Function  
  
End Class  
```  
  
```csharp  
using System;  
using System.Web;  
using System.Web.Services;  
using System.Web.Services.Protocols;  
using Microsoft.SqlServer.Dts.Runtime;  
using System.IO;  
  
[WebService(Namespace = "http://dtsue/")]  
[WebServiceBinding(ConformsTo = WsiProfiles.BasicProfile1_1)]  
public class LaunchSSISPackageServiceCS : System.Web.Services.WebService  
{  
  public LaunchSSISPackageServiceCS()  
  {  
    }  
  
  // LaunchPackage Method Parameters:  
  // 1. sourceType: file, sql, dts  
  // 2. sourceLocation: file system folder, (none), logical folder  
  // 3. packageName: for file system, ".dtsx" extension is appended  
  
  [WebMethod]  
  public int LaunchPackage(string sourceType, string sourceLocation, string packageName)  
  {   
  
    string packagePath;  
    Package myPackage;  
    Application integrationServices = new Application();  
  
    // Combine path and file name.  
    packagePath = Path.Combine(sourceLocation, packageName);  
  
    switch(sourceType)  
    {  
      case "file":  
        // Package is stored as a file.  
        // Add extension if not present.  
        if (String.IsNullOrEmpty(Path.GetExtension(packagePath)))  
        {  
          packagePath = String.Concat(packagePath, ".dtsx");  
        }  
        if (File.Exists(packagePath))  
        {  
          myPackage = integrationServices.LoadPackage(packagePath, null);  
        }  
        else  
        {  
          throw new ApplicationException("Invalid file location: "+packagePath);  
        }  
        break;  
      case "sql":  
        // Package is stored in MSDB.  
        // Combine logical path and package name.  
        if (integrationServices.ExistsOnSqlServer(packagePath, ".", String.Empty, String.Empty))  
        {  
          myPackage = integrationServices.LoadFromSqlServer(packageName, "(local)", String.Empty, String.Empty, null);  
        }  
        else  
        {  
          throw new ApplicationException("Invalid package name or location: "+packagePath);  
        }  
        break;  
      case "dts":  
        // Package is managed by SSIS Package Store.  
        // Default logical paths are File System and MSDB.  
        if (integrationServices.ExistsOnDtsServer(packagePath, "."))  
        {  
          myPackage = integrationServices.LoadFromDtsServer(packagePath, "localhost", null);  
        }  
        else  
        {  
          throw new ApplicationException("Invalid package name or location: "+packagePath);  
        }  
        break;  
      default:  
        throw new ApplicationException("Invalid sourceType argument: valid values are 'file', 'sql', and 'dts'.");  
    }  
  
    return (Int32)myPackage.Execute();  
  
  }  
  
}  
```  
  
#### <a name="testing-the-web-service"></a><span data-ttu-id="4706b-152">Проверка веб-службы</span><span class="sxs-lookup"><span data-stu-id="4706b-152">Testing the Web Service</span></span>  
 <span data-ttu-id="4706b-153">В следующем образце приложения командной строки для запуска пакета используется веб-служба.</span><span class="sxs-lookup"><span data-stu-id="4706b-153">The following sample console application uses the Web service to run a package.</span></span> <span data-ttu-id="4706b-154">Метод веб-службы LaunchPackage возвращает результат выполнения пакета как целое число вместо значения <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult>, чтобы для клиентских компьютеров не требовалась ссылка на какие-либо сборки служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4706b-154">The LaunchPackage method of the Web service returns the result of package execution as an integer instead of a <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult> value so that client computers do not require a reference to any [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] assemblies.</span></span> <span data-ttu-id="4706b-155">В образце создается закрытое перечисление, значения которого отражают значения <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult>, составляя отчет о результатах выполнения.</span><span class="sxs-lookup"><span data-stu-id="4706b-155">The sample creates a private enumeration whose values mirror the <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult> values to report the results of execution.</span></span>  
  
###### <a name="to-create-a-console-application-to-test-the-web-service"></a><span data-ttu-id="4706b-156">Создание приложения командной строки для проверки веб-службы</span><span class="sxs-lookup"><span data-stu-id="4706b-156">To create a console application to test the Web service</span></span>  
  
1.  <span data-ttu-id="4706b-157">В среде Visual Studio добавьте новое приложение командной строки на предпочитаемом языке программирования в то же решение, в котором содержится проект веб-службы.</span><span class="sxs-lookup"><span data-stu-id="4706b-157">In Visual Studio, add a new console application, using your preferred programming language, to the same solution that contains the Web service project.</span></span> <span data-ttu-id="4706b-158">В образце кода для проекта используется имя LaunchSSISPackageTest.</span><span class="sxs-lookup"><span data-stu-id="4706b-158">The sample code uses the name LaunchSSISPackageTest for the project.</span></span>  
  
2.  <span data-ttu-id="4706b-159">Определите новое приложение командной строки как автоматически загружаемый проект в решении.</span><span class="sxs-lookup"><span data-stu-id="4706b-159">Set the new console application as the startup project in the solution.</span></span>  
  
3.  <span data-ttu-id="4706b-160">Добавьте веб-ссылку в проект веб-службы.</span><span class="sxs-lookup"><span data-stu-id="4706b-160">Add a Web reference for the Web service project.</span></span> <span data-ttu-id="4706b-161">При необходимости измените декларацию переменной в образце кода на имя, назначенное для объекта учетной записи-посредника веб-службы.</span><span class="sxs-lookup"><span data-stu-id="4706b-161">If necessary, adjust the variable declaration in the sample code for the name that you assign to the Web service proxy object.</span></span>  
  
4.  <span data-ttu-id="4706b-162">Вставьте образец кода для подпрограммы Main и закрытого перечисления в код.</span><span class="sxs-lookup"><span data-stu-id="4706b-162">Paste the sample code for the Main routine and the private enumeration into the code.</span></span> <span data-ttu-id="4706b-163">(В этом образце приводится полное содержимое окна кода.)</span><span class="sxs-lookup"><span data-stu-id="4706b-163">(The sample shows the whole contents of the code window.)</span></span>  
  
5.  <span data-ttu-id="4706b-164">Измените строку кода, которой вызывается метод LaunchPackage, и укажите допустимые значения для входных аргументов, которые указывают на существующий пакет.</span><span class="sxs-lookup"><span data-stu-id="4706b-164">Edit the line of code that calls the LaunchPackage method to provide a set of valid values for the input arguments that point to an existing package.</span></span> <span data-ttu-id="4706b-165">Например, если пакет package1.dtsx хранится на сервере в папке C:\My Packages, передайте «file» в качестве значения параметра `sourceType`, «C:\My Packages» — в качестве значения параметра `sourceLocation` и «package1» (без расширения файла) — в качестве значения параметра `packageName`.</span><span class="sxs-lookup"><span data-stu-id="4706b-165">For example, if package1.dtsx is stored on the server in C:\My Packages, pass "file" as the value of `sourceType`, "C:\My Packages" as the value of `sourceLocation`, and "package1" (without the extension) as the value of `packageName`.</span></span>  
  
```vb  
Module LaunchSSISPackageTest  
  
  Sub Main()  
  
    Dim launchPackageService As New LaunchSSISPackageService.LaunchSSISPackageService  
    Dim packageResult As Integer  
  
    Try  
      packageResult = launchPackageService.LaunchPackage("sql", String.Empty, "SimpleTestPackage")  
    Catch ex As Exception  
      ' The type of exception returned by a Web service is:  
      '  System.Web.Services.Protocols.SoapException  
      Console.WriteLine("The following exception occurred: " & ex.Message)  
    End Try  
  
    Console.WriteLine(CType(packageResult, PackageExecutionResult).ToString)  
    Console.ReadKey()  
  
  End Sub  
  
  Private Enum PackageExecutionResult  
    PackageSucceeded  
    PackageFailed  
    PackageCompleted  
    PackageWasCancelled  
  End Enum  
  
End Module  
```  
  
```csharp  
using System;  
  
namespace LaunchSSISPackageSvcTestCS  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      LaunchSSISPackageServiceCS.LaunchSSISPackageServiceCS launchPackageService = new LaunchSSISPackageServiceCS.LaunchSSISPackageServiceCS();  
      int packageResult = 0;  
  
      try  
      {  
        packageResult = launchPackageService.LaunchPackage("sql", String.Empty, "SimpleTestPackage");  
      }  
      catch (Exception ex)  
      {  
        // The type of exception returned by a Web service is:  
        //  System.Web.Services.Protocols.SoapException  
        Console.WriteLine("The following exception occurred: " + ex.Message);  
      }  
  
      Console.WriteLine(((PackageExecutionResult)packageResult).ToString());  
      Console.ReadKey();  
  
    }  
  
    private enum PackageExecutionResult  
    {  
      PackageSucceeded,  
      PackageFailed,  
      PackageCompleted,  
      PackageWasCancelled  
    };  
  
  }  
}  
```  
  

  
## <a name="external-resources"></a><span data-ttu-id="4706b-166">Внешние ресурсы</span><span class="sxs-lookup"><span data-stu-id="4706b-166">External Resources</span></span>  
  
-   <span data-ttu-id="4706b-167">Видеоролик [Как автоматизировать выполнение пакета служб SSIS с помощью агента SQL Server (видеоматериалы по SQL Server)](https://technet.microsoft.com/sqlserver/ff686764.aspx) на сайте technet.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="4706b-167">Video, [How to: Automate SSIS Package Execution by Using the SQL Server Agent (SQL Server Video)](https://technet.microsoft.com/sqlserver/ff686764.aspx), on technet.microsoft.com</span></span>  
  
<span data-ttu-id="4706b-168">![Значок Integration Services (маленький)](../media/dts-16.gif "Значок служб Integration Services (маленький)")  **следит за обновлениями Integration Services**</span><span class="sxs-lookup"><span data-stu-id="4706b-168">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="4706b-169">Чтобы загрузить новейшую документацию, статьи, образцы и видеоматериалы корпорации Майкрософт, а также лучшие решения участников сообщества, посетите страницу служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] на сайте MSDN:</span><span class="sxs-lookup"><span data-stu-id="4706b-169">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="4706b-170">Посетить страницу «Службы Integration Services» на сайте MSDN</span><span class="sxs-lookup"><span data-stu-id="4706b-170">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="4706b-171">Чтобы получать автоматические уведомления об этих обновлениях, подпишитесь на RSS-каналы, предлагаемые на этой странице.</span><span class="sxs-lookup"><span data-stu-id="4706b-171">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4706b-172">См. также:</span><span class="sxs-lookup"><span data-stu-id="4706b-172">See Also</span></span>  
 <span data-ttu-id="4706b-173">[Основные сведения о различиях между локальным и удаленным выполнением](../run-manage-packages-programmatically/understanding-the-differences-between-local-and-remote-execution.md) </span><span class="sxs-lookup"><span data-stu-id="4706b-173">[Understanding the Differences between Local and Remote Execution](../run-manage-packages-programmatically/understanding-the-differences-between-local-and-remote-execution.md) </span></span>  
 <span data-ttu-id="4706b-174">[Программная загрузка и запуск локального пакета](../run-manage-packages-programmatically/loading-and-running-a-local-package-programmatically.md) </span><span class="sxs-lookup"><span data-stu-id="4706b-174">[Loading and Running a Local Package Programmatically](../run-manage-packages-programmatically/loading-and-running-a-local-package-programmatically.md) </span></span>  
 [<span data-ttu-id="4706b-175">Загрузка выхода локального пакета</span><span class="sxs-lookup"><span data-stu-id="4706b-175">Loading the Output of a Local Package</span></span>](../run-manage-packages-programmatically/loading-the-output-of-a-local-package.md)  
  
  
