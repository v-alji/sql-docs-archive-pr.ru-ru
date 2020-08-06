---
title: Практическое руководство. Развертывание модуля обработки данных на сервере отчетов | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- data processing extensions [Reporting Services], deploying
- assemblies [Reporting Services], data processing extension deployments
ms.assetid: e00dface-70f8-434b-9763-8ebee18737d2
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d606096b9f2060d3cf5b9cea1f95a5345e592383
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750512"
---
# <a name="how-to-deploy-a-data-processing-extension-to-a-report-server"></a><span data-ttu-id="2643d-102">Руководство. Развертывание модуля обработки данных на сервере отчетов</span><span class="sxs-lookup"><span data-stu-id="2643d-102">How to: Deploy a Data Processing Extension to a Report Server</span></span>
  <span data-ttu-id="2643d-103">Серверы отчетов используют модули обработки данных для получения и обработки данных в отчетах, готовых для просмотра.</span><span class="sxs-lookup"><span data-stu-id="2643d-103">Report servers use data processing extensions for retrieving and processing data in rendered reports.</span></span> <span data-ttu-id="2643d-104">Сборка модуля обработки данных развертывается на сервере отчетов как закрытая сборка.</span><span class="sxs-lookup"><span data-stu-id="2643d-104">You should deploy your data processing extension assembly to a report server as a private assembly.</span></span> <span data-ttu-id="2643d-105">Нужно также внести запись в файл конфигурации сервера отчетов RSReportServer.config.</span><span class="sxs-lookup"><span data-stu-id="2643d-105">You also need to make an entry in the report server configuration file, RSReportServer.config.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="2643d-106">Процедуры</span><span class="sxs-lookup"><span data-stu-id="2643d-106">Procedures</span></span>  
  
#### <a name="to-deploy-a-data-processing-extension-assembly"></a><span data-ttu-id="2643d-107">Развертывание сборки модуля обработки данных</span><span class="sxs-lookup"><span data-stu-id="2643d-107">To deploy a data processing extension assembly</span></span>  
  
1.  <span data-ttu-id="2643d-108">Скопируйте сборку из промежуточной папки в каталог bin сервера отчетов, на котором будет использоваться модуль обработки данных.</span><span class="sxs-lookup"><span data-stu-id="2643d-108">Copy your assembly from your staging location to the bin directory of the report server on which you want to use the data processing extension.</span></span> <span data-ttu-id="2643d-109">По умолчанию каталог bin сервера отчетов находится в папке%ProgramFiles%\Microsoft SQL Server \ MSRS10_50. \<*Instance Name*> \Reporting Services\ReportServer\bin.</span><span class="sxs-lookup"><span data-stu-id="2643d-109">The default location of the report server bin directory is %ProgramFiles%\Microsoft SQL Server\MSRS10_50.\<*Instance Name*>\Reporting Services\ReportServer\bin.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="2643d-110">Этот шаг предотвратит обновление до более нового экземпляра SQL Server.</span><span class="sxs-lookup"><span data-stu-id="2643d-110">This step will prevent an upgrade to a newer instance of SQL Server.</span></span> <span data-ttu-id="2643d-111">Дополнительные сведения см. в разделе [Upgrade and Migrate Reporting Services](../../install-windows/upgrade-and-migrate-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="2643d-111">For more information, see [Upgrade and Migrate Reporting Services](../../install-windows/upgrade-and-migrate-reporting-services.md).</span></span>  
  
2.  <span data-ttu-id="2643d-112">Скопировав файл сборки, откройте файл RSReportServer.config.</span><span class="sxs-lookup"><span data-stu-id="2643d-112">After the assembly file is copied, open the RSReportServer.config file.</span></span> <span data-ttu-id="2643d-113">Файл RSReportServer.config расположен в каталоге ReportServer.</span><span class="sxs-lookup"><span data-stu-id="2643d-113">The RSReportServer.config file is located in the ReportServer directory.</span></span> <span data-ttu-id="2643d-114">Необходимо внести запись в этот файл конфигурации для файла сборки развертываемого модуля обработки данных.</span><span class="sxs-lookup"><span data-stu-id="2643d-114">You need to make an entry in the configuration file for your data processing extension assembly file.</span></span> <span data-ttu-id="2643d-115">Файл конфигурации можно открыть с помощью среды Visual Studio или простого текстового редактора (такого как Блокнот).</span><span class="sxs-lookup"><span data-stu-id="2643d-115">You can open the configuration file with Visual Studio or a simple text editor, such as Notepad.</span></span>  
  
3.  <span data-ttu-id="2643d-116">Найдите в файле RSReportServer.config элемент `Data`.</span><span class="sxs-lookup"><span data-stu-id="2643d-116">Locate the `Data` element in the RSReportServer.config file.</span></span> <span data-ttu-id="2643d-117">Запись для вновь созданного модуля обработки данных необходимо создать в месте, указанном ниже.</span><span class="sxs-lookup"><span data-stu-id="2643d-117">An entry for your newly created data processing extension should be made in the following location:</span></span>  
  
    ```  
    <Extensions>  
       <Data>  
          <Your extension configuration information goes here>  
       </Data>  
    </Extensions>  
    ```  
  
4.  <span data-ttu-id="2643d-118">Добавьте запись для развертываемого модуля обработки данных.</span><span class="sxs-lookup"><span data-stu-id="2643d-118">Add an entry for your data processing extension.</span></span> <span data-ttu-id="2643d-119">В новую запись должен входить элемент `Extension` со значениями параметров `Name` и `Type`. Запись может выглядеть, например, следующим образом:</span><span class="sxs-lookup"><span data-stu-id="2643d-119">Your entry should include an `Extension` element with values for `Name` and `Type` and might look like the following:</span></span>  
  
    ```  
    <Extension Name="ExtensionName" Type="CompanyName.ExtensionName.MyConnectionClass, MyExtensionAssembly" />  
    ```  
  
     <span data-ttu-id="2643d-120">По умолчанию `Name` — уникальное имя модуля обработки данных.</span><span class="sxs-lookup"><span data-stu-id="2643d-120">The value for `Name` is the unique name of the data processing extension.</span></span> <span data-ttu-id="2643d-121">Значение параметра `Type` представляет собой список с разделителями-запятыми, включающий полное имя пространства имен для класса, реализующего интерфейсы <xref:Microsoft.ReportingServices.Interfaces.IExtension> и <xref:Microsoft.ReportingServices.DataProcessing.IDbConnection>, а затем имя сборки поставщика (без расширения DLL).</span><span class="sxs-lookup"><span data-stu-id="2643d-121">The value for `Type` is a comma-separated list that includes an entry for the fully qualified namespace of your class that implements the <xref:Microsoft.ReportingServices.Interfaces.IExtension> and <xref:Microsoft.ReportingServices.DataProcessing.IDbConnection> interfaces, followed by the name of your assembly (not including the .dll file extension).</span></span> <span data-ttu-id="2643d-122">По умолчанию модули обработки данных являются видимыми.</span><span class="sxs-lookup"><span data-stu-id="2643d-122">By default, data processing extensions are visible.</span></span> <span data-ttu-id="2643d-123">Чтобы скрыть модуль от пользовательских интерфейсов, таких как диспетчер отчетов, добавьте атрибут `Visible` к элементу `Extension` и задайте для него значение `false`.</span><span class="sxs-lookup"><span data-stu-id="2643d-123">To hide an extension from user interfaces, such as Report Manager, add a `Visible` attribute to the `Extension` element, and set it to `false`.</span></span>  
  
5.  <span data-ttu-id="2643d-124">Необходимо создать для пользовательской сборки группу кода, которая предоставляет разрешение `FullTrust` для конкретного модуля.</span><span class="sxs-lookup"><span data-stu-id="2643d-124">Add a code group for your custom assembly that grants `FullTrust` permission for your extension.</span></span> <span data-ttu-id="2643d-125">Это можно сделать, добавив группу кода в файл rssrvpolicy.config, расположенный по умолчанию в%ProgramFiles%\Microsoft SQL Server \\<MSRS10_50. \<*Instance Name*> \Reporting Services\ReportServer.</span><span class="sxs-lookup"><span data-stu-id="2643d-125">You do this by adding the code group to the rssrvpolicy.config file located by default in %ProgramFiles%\Microsoft SQL Server\\<MSRS10_50.\<*Instance Name*>\Reporting Services\ReportServer.</span></span> <span data-ttu-id="2643d-126">Пример группы кода показан ниже.</span><span class="sxs-lookup"><span data-stu-id="2643d-126">Your code group might look like the following:</span></span>  
  
    ```  
    <CodeGroup class="UnionCodeGroup"  
       version="1"  
       PermissionSetName="FullTrust"  
       Name="MyExtensionCodeGroup"  
       Description="Code group for my data processing extension">  
          <IMembershipCondition class="UrlMembershipCondition"  
             version="1"  
             Url="C:\Program Files\Microsoft SQL Server\MSRS10_50.<Instance Name>\Reporting Services\ReportServer\bin\MyExtensionAssembly.dll"  
           />  
    </CodeGroup>  
    ```  
  
 <span data-ttu-id="2643d-127">URL-членство — это лишь одно из множества условий членства, которые могут быть заданы для модуля обработки данных.</span><span class="sxs-lookup"><span data-stu-id="2643d-127">URL membership is only one of many membership conditions you might choose for your data processing extension.</span></span> <span data-ttu-id="2643d-128">Дополнительные сведения об управлении доступом для кода в [!INCLUDE[ssCurrentUI](../../../includes/sscurrentui-md.md)] [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] см. в статье [Разработка безопасных приложений (службы Reporting Services)](../secure-development/secure-development-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="2643d-128">For more information about code access security in [!INCLUDE[ssCurrentUI](../../../includes/sscurrentui-md.md)] [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)], see [Secure Development &#40;Reporting Services&#41;](../secure-development/secure-development-reporting-services.md).</span></span>  
  
## <a name="verifying-the-deployment"></a><span data-ttu-id="2643d-129">Проверка развертывания</span><span class="sxs-lookup"><span data-stu-id="2643d-129">Verifying the Deployment</span></span>  
 <span data-ttu-id="2643d-130">Проверить, успешно ли был развернут модуль обработки данных на сервере отчетов, можно с помощью метода веб-службы <xref:ReportService2010.ReportingService2010.ListExtensions%2A>.</span><span class="sxs-lookup"><span data-stu-id="2643d-130">You can verify whether your data processing extension was deployed successfully to the report server by using the Web service <xref:ReportService2010.ReportingService2010.ListExtensions%2A> method.</span></span> <span data-ttu-id="2643d-131">Можно также открыть диспетчер отчетов и убедиться, что модуль включен в список доступных источников данных.</span><span class="sxs-lookup"><span data-stu-id="2643d-131">You can also open Report Manager and verify that your extension is included in the list of available data sources.</span></span> <span data-ttu-id="2643d-132">Дополнительные сведения о диспетчере отчетов и источниках данных см. в разделе [Создание, изменение и удаление общих источников данных (службы SSRS)](../../report-data/create-modify-and-delete-shared-data-sources-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="2643d-132">For more information about Report Manager and data sources, see [Create, Modify, and Delete Shared Data Sources &#40;SSRS&#41;](../../report-data/create-modify-and-delete-shared-data-sources-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2643d-133">См. также:</span><span class="sxs-lookup"><span data-stu-id="2643d-133">See Also</span></span>  
 <span data-ttu-id="2643d-134">[Развертывание модуля обработки данных](deploying-a-data-processing-extension.md) </span><span class="sxs-lookup"><span data-stu-id="2643d-134">[Deploying a Data Processing Extension](deploying-a-data-processing-extension.md) </span></span>  
 <span data-ttu-id="2643d-135">[Модули служб Reporting Services](../reporting-services-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="2643d-135">[Reporting Services Extensions](../reporting-services-extensions.md) </span></span>  
 <span data-ttu-id="2643d-136">[Реализация модуля обработки данных](implementing-a-data-processing-extension.md) </span><span class="sxs-lookup"><span data-stu-id="2643d-136">[Implementing a Data Processing Extension](implementing-a-data-processing-extension.md) </span></span>  
 [<span data-ttu-id="2643d-137">Библиотека модулей Reporting Services</span><span class="sxs-lookup"><span data-stu-id="2643d-137">Reporting Services Extension Library</span></span>](../reporting-services-extension-library.md)  
  
  
