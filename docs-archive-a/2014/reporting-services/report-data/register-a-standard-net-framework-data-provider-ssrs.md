---
title: Регистрация стандартного поставщика данных .NET Framework (службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- reports [Reporting Services], data
- .NET Framework data providers for Reporting Services
- data processing extensions [Reporting Services]
- data providers [Reporting Services]
- data retrieval [Reporting Services]
- Reporting Services, data sources
ms.assetid: d92add64-e93c-4598-8508-55d1bc46acf6
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 5fd26f9c7fa163d9e6005d42e24c7b1483987f3e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729093"
---
# <a name="register-a-standard-net-framework-data-provider-ssrs"></a><span data-ttu-id="425c9-102">Регистрация стандартного поставщика данных .NET Framework (службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="425c9-102">Register a Standard .NET Framework Data Provider (SSRS)</span></span>
  <span data-ttu-id="425c9-103">Чтобы набор данных отчета служб [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] получал данные с помощью поставщика данных [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] сторонней разработки, необходимо развернуть и зарегистрировать сборку поставщика данных [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] в двух местах: на клиенте, используемом для разработки отчета, и на сервере отчетов.</span><span class="sxs-lookup"><span data-stu-id="425c9-103">To use a third-party [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] data provider to retrieve data for a [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] report dataset, you need to deploy and register the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] data provider assembly in two locations: on the report authoring client and on the report server.</span></span> <span data-ttu-id="425c9-104">На клиенте поставщик данных должен быть зарегистрирован в качестве типа источника данных и связан с конструктором запросов.</span><span class="sxs-lookup"><span data-stu-id="425c9-104">On the report authoring client, you must register the data provider as a data source type and associate it with a query designer.</span></span> <span data-ttu-id="425c9-105">После этого этот поставщик может быть выбран в качестве типа источника данных при создании набора данных для отчета.</span><span class="sxs-lookup"><span data-stu-id="425c9-105">You can then select this data provider as a type of data source when you create a report dataset.</span></span> <span data-ttu-id="425c9-106">При этом откроется связанный конструктор запросов, помогающий создавать запросы для этого типа источников данных.</span><span class="sxs-lookup"><span data-stu-id="425c9-106">The associated query designer opens to help you create queries for this data source type.</span></span> <span data-ttu-id="425c9-107">На сервере отчетов поставщик данных необходимо зарегистрировать в качестве типа источника данных.</span><span class="sxs-lookup"><span data-stu-id="425c9-107">On the report server, you must register the data provider as a data source type.</span></span> <span data-ttu-id="425c9-108">После этого может производиться обработка опубликованных отчетов, которые в качестве источника данных используют этот поставщик.</span><span class="sxs-lookup"><span data-stu-id="425c9-108">You can then process published reports that retrieve data from a data source using this data provider.</span></span>  
  
 <span data-ttu-id="425c9-109">Поставщикам данных сторонней разработки не обязательно обеспечивать все функции, реализуемые модулями обработки данных служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="425c9-109">Third-party data providers do not necessarily provide all the functionality available with the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] data processing extensions.</span></span> <span data-ttu-id="425c9-110">Дополнительные сведения см. в разделе [Источники данных, поддерживаемые службами Reporting Services (SSRS)](../create-deploy-and-manage-mobile-and-paginated-reports.md).</span><span class="sxs-lookup"><span data-stu-id="425c9-110">For more information, see [Data Sources Supported by Reporting Services &#40;SSRS&#41;](../create-deploy-and-manage-mobile-and-paginated-reports.md).</span></span> <span data-ttu-id="425c9-111">Дополнительные сведения о расширении функций поставщика данных платформы[!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)]</span><span class="sxs-lookup"><span data-stu-id="425c9-111">To learn about extending the functionality of a .[!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)]</span></span> <span data-ttu-id="425c9-112">см. в разделе [Реализация модуля обработки данных](../extensions/data-processing/implementing-a-data-processing-extension.md).</span><span class="sxs-lookup"><span data-stu-id="425c9-112">data provider, see [Implementing a Data Processing Extension](../extensions/data-processing/implementing-a-data-processing-extension.md).</span></span>  
  
 <span data-ttu-id="425c9-113">Для установки и регистрации поставщиков данных необходимы учетные данные администратора.</span><span class="sxs-lookup"><span data-stu-id="425c9-113">You need administrator credentials to install and register data providers.</span></span>  
  
## <a name="registering-a-net-framework-data-provider-on-the-report-server"></a><span data-ttu-id="425c9-114">Регистрация поставщика данных .NET Framework на сервере отчетов</span><span class="sxs-lookup"><span data-stu-id="425c9-114">Registering a .NET Framework Data Provider on the Report Server</span></span>  
 <span data-ttu-id="425c9-115">Для обработки опубликованных отчетов, использующих этот поставщик данных [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] на сервере отчетов, на нем необходимо установить сборку.</span><span class="sxs-lookup"><span data-stu-id="425c9-115">In order to process published reports that use this [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] data provider on the report server, you need to install the assembly on the report server.</span></span> <span data-ttu-id="425c9-116">Необходимо изменить два файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="425c9-116">You must modify two configuration files.</span></span> <span data-ttu-id="425c9-117">Регистрация поставщика данных производится в файле rsreportserver.config.</span><span class="sxs-lookup"><span data-stu-id="425c9-117">Modify rsreportserver.config to register the data provider.</span></span> <span data-ttu-id="425c9-118">Чтобы предоставить права доступа к коду сборки необходимо изменить файл rssrvpolicy.config.</span><span class="sxs-lookup"><span data-stu-id="425c9-118">Modify rssrvpolicy.config to grant code access security permissions for the assembly.</span></span>  
  
#### <a name="to-install-a-data-provider-assembly-on-the-report-server"></a><span data-ttu-id="425c9-119">Установка сборки поставщика данных на сервер отчетов</span><span class="sxs-lookup"><span data-stu-id="425c9-119">To install a data provider assembly on the report server</span></span>  
  
1.  <span data-ttu-id="425c9-120">Перейдите в каталог bin по умолчанию сервера отчетов, на котором планируется использование поставщика данных [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="425c9-120">Navigate to the default location of the bin directory on the report server on which you want to use the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] data provider.</span></span> <span data-ttu-id="425c9-121">По умолчанию каталог bin сервера отчетов находится в папке *\<drive>* : \Program Files\Microsoft SQL Server \ MSRS10_50. Мссклсервер\репортинг Services\ReportServer\bin.</span><span class="sxs-lookup"><span data-stu-id="425c9-121">The default location of the report server bin directory is *\<drive>*:\Program Files\Microsoft SQL Server\MSRS10_50.MSSQLSERVER\Reporting Services\ReportServer\bin.</span></span>  
  
2.  <span data-ttu-id="425c9-122">Скопируйте сборку из промежуточной папки в каталог bin сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="425c9-122">Copy your assembly from your staging location to the bin directory of the report server.</span></span> <span data-ttu-id="425c9-123">Можно также загрузить сборку в глобальный кэш сборок (GAC).</span><span class="sxs-lookup"><span data-stu-id="425c9-123">Alternatively, you can load your assembly in the global assembly cache (GAC).</span></span> <span data-ttu-id="425c9-124">Дополнительные сведения см. в разделе [Работа со сборками и глобальным кэшем сборок](https://go.microsoft.com/fwlink/?linkid=63912) в документации по пакету SDK платформы [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] на веб-узле MSDN.</span><span class="sxs-lookup"><span data-stu-id="425c9-124">For more information, see [Working with Assemblies and the Global Assembly Cache](https://go.microsoft.com/fwlink/?linkid=63912) in the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] SDK documentation on MSDN.</span></span>  
  
#### <a name="to-register-a-net-data-provider-on-the-report-server"></a><span data-ttu-id="425c9-125">Регистрация сборки поставщика данных на сервере отчетов</span><span class="sxs-lookup"><span data-stu-id="425c9-125">To register a .NET data provider on the report server</span></span>  
  
1.  <span data-ttu-id="425c9-126">Создайте резервную копию файла RSReportServer.config в папке ReportServer, в которую вложен каталог bin.</span><span class="sxs-lookup"><span data-stu-id="425c9-126">Make a backup of the RSReportServer.config file in the ReportServer parent directory for bin.</span></span>  
  
2.  <span data-ttu-id="425c9-127">Откройте файл RSReportServer.config. Это можно сделать в среде [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] или в любом текстовом редакторе (например в Блокноте).</span><span class="sxs-lookup"><span data-stu-id="425c9-127">Open RSReportServer.config. You can open the configuration file with [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] or a simple text editor, such as Notepad.</span></span>  
  
3.  <span data-ttu-id="425c9-128">Найдите в файле RSReportServer.config элемент `Data`.</span><span class="sxs-lookup"><span data-stu-id="425c9-128">Locate the `Data` element in the RSReportServer.config file.</span></span> <span data-ttu-id="425c9-129">Элемент для поставщика данных [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] необходимо создать в месте, указанном ниже.</span><span class="sxs-lookup"><span data-stu-id="425c9-129">An entry for the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] data provider should be made in the following location:</span></span>  
  
    ```  
    <Extensions>  
       <Data>  
          <Extension Your data provider configuration information goes here />  
       </Data>  
    </Extensions>  
    ```  
  
4.  <span data-ttu-id="425c9-130">Добавьте элемент для поставщика данных [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="425c9-130">Add an entry for the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] data provider.</span></span>  
  
    |<span data-ttu-id="425c9-131">attribute</span><span class="sxs-lookup"><span data-stu-id="425c9-131">Attribute</span></span>|<span data-ttu-id="425c9-132">Description</span><span class="sxs-lookup"><span data-stu-id="425c9-132">Description</span></span>|  
    |---------------|-----------------|  
    |`Name`|<span data-ttu-id="425c9-133">Уникальное имя поставщика данных, например **MyNETDataProvider**.</span><span class="sxs-lookup"><span data-stu-id="425c9-133">Provide a unique name for the data provider, for example, **MyNETDataProvider**.</span></span> <span data-ttu-id="425c9-134">Длина атрибута `Name` не должна превышать 255 символов.</span><span class="sxs-lookup"><span data-stu-id="425c9-134">The maximum length for the `Name` attribute is 255 characters.</span></span> <span data-ttu-id="425c9-135">Имя должно быть уникальным среди всех элементов, вложенных в элемент `Extension` файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="425c9-135">The name must be unique among all entries within the `Extension` element of a configuration file.</span></span> <span data-ttu-id="425c9-136">Указываемое здесь значение выводится в раскрывающемся списке типов источников данных при создании нового источника данных.</span><span class="sxs-lookup"><span data-stu-id="425c9-136">The value you include here appears in the drop-down list of data source types when you create a new data source.</span></span>|  
    |`Type`|<span data-ttu-id="425c9-137">Список с разделителями-запятыми, включающий полное имя пространства имен для класса, реализующего интерфейс <xref:System.Data.IDbConnection> , а затем имя сборки поставщика [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] (без расширения DLL).</span><span class="sxs-lookup"><span data-stu-id="425c9-137">Enter a comma-separated list that includes the fully qualified namespace of the class that implements the <xref:System.Data.IDbConnection> interface, followed by the name of the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] data provider assembly (not including the .dll file name extension).</span></span>|  
  
     <span data-ttu-id="425c9-138">Например, для DLL-файла, развертываемого в каталоге bin сервера отчетов новый элемент может выглядеть следующим образом.</span><span class="sxs-lookup"><span data-stu-id="425c9-138">For example, the entry might resemble the following for a DLL deployed to the report server bin directory:</span></span>  
  
    ```  
    <Extension Name="MyNETDataProvider" Type="CompanyName.ExtensionName.DataProviderConnectionClass, DataProviderAssembly" />   
    ```  
  
     <span data-ttu-id="425c9-139">При загрузке сборки в глобальный кэш сборок необходимо указать свойства строгого имени.</span><span class="sxs-lookup"><span data-stu-id="425c9-139">If you load your assembly into the global assembly cache (GAC), you must provide the strong name properties.</span></span> <span data-ttu-id="425c9-140">Пример:</span><span class="sxs-lookup"><span data-stu-id="425c9-140">For example:</span></span>  
  
    ```  
    <Extension Name="MyNETDataProvider" Type="CompanyName.ExtensionName.DataProviderConnectionClass, DataProviderAssembly,Version=1.0.0.0, Culture=neutral, PublicKeyToken=MyPublicToken"/>  
    ```  
  
#### <a name="to-set-the-code-group-policy-for-a-net-data-provider"></a><span data-ttu-id="425c9-141">Настройка групповой политики кода для поставщика данных .NET</span><span class="sxs-lookup"><span data-stu-id="425c9-141">To set the code group policy for a .NET data provider</span></span>  
  
1.  <span data-ttu-id="425c9-142">Создайте резервную копию файла rssrvpolicy.config в папке ReportServer, в которую вложен каталог bin.</span><span class="sxs-lookup"><span data-stu-id="425c9-142">Make a backup copy of the rssrvpolicy.config file in the ReportServer parent directory for bin.</span></span>  
  
2.  <span data-ttu-id="425c9-143">Откройте файл rssrvpolicy.config. Это можно сделать в среде [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] или в любом текстовом редакторе (например, в Блокноте).</span><span class="sxs-lookup"><span data-stu-id="425c9-143">Open rssrvpolicy.config. You can open the configuration file with [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] or a simple text editor such as Notepad.</span></span>  
  
3.  <span data-ttu-id="425c9-144">Найдите в файле rssrvpolicy.config элемент `CodeGroup`.</span><span class="sxs-lookup"><span data-stu-id="425c9-144">Locate the `CodeGroup` element in the rssrvpolicy.config file.</span></span>  
  
4.  <span data-ttu-id="425c9-145">Добавьте группу кода для сборки поставщика данных, предоставляющую разрешение `FullTrust`,</span><span class="sxs-lookup"><span data-stu-id="425c9-145">Add a code group for the data provider assembly that grants `FullTrust` permission.</span></span> <span data-ttu-id="425c9-146">как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="425c9-146">Your code group might resemble the following:</span></span>  
  
    ```  
    <CodeGroup class="UnionCodeGroup"  
       version="1"  
       PermissionSetName="FullTrust"  
       Name="ThisDataProviderCodeGroup"  
       Description="Code group for the .NET data provider">  
          <IMembershipCondition class="UrlMembershipCondition"  
             version="1"  
             Url=  
    "C:\Program Files\Microsoft SQL Server\MSRS10_50.MSSQLSERVER\Reporting Services\ReportServer\bin\DataProviderAssembly.dll"  
           />  
    </CodeGroup>  
    ```  
  
 <span data-ttu-id="425c9-147">Членство URL — это лишь одно из множества условий членства, которые должны быть заданы для поставщика данных.</span><span class="sxs-lookup"><span data-stu-id="425c9-147">URL membership is only one of many membership conditions you might select for the data provider.</span></span>  
  
### <a name="verifying-the-deployment-and-registration"></a><span data-ttu-id="425c9-148">Проверка развертывания и регистрация</span><span class="sxs-lookup"><span data-stu-id="425c9-148">Verifying the Deployment and Registration</span></span>  
 <span data-ttu-id="425c9-149">Успешность развертывания поставщика данных на сервере отчетов можно проверить по его наличию в списке источников данных, открыв диспетчер отчетов.</span><span class="sxs-lookup"><span data-stu-id="425c9-149">You can verify whether the data provider was deployed successfully to the report server by opening Report Manager and verifying that the data provider is included in the list of available data sources.</span></span> <span data-ttu-id="425c9-150">Дополнительные сведения о диспетчере отчетов и источниках данных см. в разделе [Создание, изменение и удаление общих источников данных (службы SSRS)](create-modify-and-delete-shared-data-sources-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="425c9-150">For more information about Report Manager and data sources, see [Create, Modify, and Delete Shared Data Sources &#40;SSRS&#41;](create-modify-and-delete-shared-data-sources-ssrs.md).</span></span>  
  
## <a name="registering-a-net-framework-data-provider-on-the-report-designer-client"></a><span data-ttu-id="425c9-151">Регистрация поставщика данных .NET Framework на клиенте конструктора отчетов</span><span class="sxs-lookup"><span data-stu-id="425c9-151">Registering a .NET Framework Data Provider on the Report Designer Client</span></span>  
 <span data-ttu-id="425c9-152">Для разработки отчетов, которые используют в качестве источника данных поставщик данных [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] , необходимо установить сборку на клиентский компьютер, на котором запускается конструктор отчетов.</span><span class="sxs-lookup"><span data-stu-id="425c9-152">In order to author reports that use this [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] data provider for a data source, you must install the assembly on your client computer that runs Report Designer.</span></span> <span data-ttu-id="425c9-153">Необходимо изменить два файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="425c9-153">You must modify two configuration files.</span></span> <span data-ttu-id="425c9-154">Измените файл RSReportDesigner.config для регистрации поставщика данных как источника данных и использования обычного конструктора запросов.</span><span class="sxs-lookup"><span data-stu-id="425c9-154">Modify RSReportDesigner.config to register the data provider as a data source and to use the generic query designer.</span></span> <span data-ttu-id="425c9-155">Чтобы предоставить права доступа к коду сборки, измените файл RSPreviewPolicy.config.</span><span class="sxs-lookup"><span data-stu-id="425c9-155">Modify RSPreviewPolicy.config to grant code access security permissions for the data provider assembly.</span></span>  
  
#### <a name="to-install-a-data-provider-assembly-on-the-report-designer-client"></a><span data-ttu-id="425c9-156">Установка сборки поставщика данных на клиенте конструктора отчетов</span><span class="sxs-lookup"><span data-stu-id="425c9-156">To install a data provider assembly on the Report Designer client</span></span>  
  
1.  <span data-ttu-id="425c9-157">Перейдите в каталог по умолчанию PrivateAssemblies на клиенте конструктора отчетов, на котором будет использоваться поставщик данных [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="425c9-157">Navigate to the default location of the PrivateAssemblies directory on the Report Designer client on which you want to use the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] data provider.</span></span> <span data-ttu-id="425c9-158">Расположением каталога PrivateAssemblies по умолчанию является *\<drive>* : \Program Files\Microsoft Visual Studio 9.0 \ Common7\IDE\PrivateAssemblies.</span><span class="sxs-lookup"><span data-stu-id="425c9-158">The default location of the PrivateAssemblies directory is *\<drive>*:\Program Files\Microsoft Visual Studio 9.0\Common7\IDE\PrivateAssemblies.</span></span>  
  
2.  <span data-ttu-id="425c9-159">Скопируйте сборку из промежуточной папки в каталог PrivateAssemblies клиента конструктора отчетов.</span><span class="sxs-lookup"><span data-stu-id="425c9-159">Copy your assembly from your staging location to the PrivateAssemblies directory of the Report Designer client.</span></span> <span data-ttu-id="425c9-160">Можно также загрузить сборку в глобальный кэш сборок (GAC).</span><span class="sxs-lookup"><span data-stu-id="425c9-160">Alternatively, you can load your assembly in the global assembly cache (GAC).</span></span> <span data-ttu-id="425c9-161">Дополнительные сведения см. в разделе [Работа со сборками и глобальным кэшем сборок](https://go.microsoft.com/fwlink/?linkid=63912) в документации по пакету SDK платформы [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] на веб-узле MSDN.</span><span class="sxs-lookup"><span data-stu-id="425c9-161">For more information, see [Working with Assemblies and the Global Assembly Cache](https://go.microsoft.com/fwlink/?linkid=63912) in the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] SDK documentation on MSDN.</span></span>  
  
#### <a name="to-register-a-net-data-provider-on-the-report-designer-client"></a><span data-ttu-id="425c9-162">Регистрация сборки поставщика данных на клиенте конструктора отчетов</span><span class="sxs-lookup"><span data-stu-id="425c9-162">To register a .NET data provider on the Report Designer client</span></span>  
  
1.  <span data-ttu-id="425c9-163">Создайте резервную копию файла RSReportDesigner.config в каталоге PrivateAssemblies.</span><span class="sxs-lookup"><span data-stu-id="425c9-163">Make a backup copy of the RSReportDesigner.config file in the PrivateAssemblies directory.</span></span>  
  
2.  <span data-ttu-id="425c9-164">Откройте файл RSReportDesigner.config с помощью среды [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] или простого текстового редактора (например, Блокнота).</span><span class="sxs-lookup"><span data-stu-id="425c9-164">Open RSReportDesigner.config with [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] or a simple text editor such as Notepad.</span></span>  
  
3.  <span data-ttu-id="425c9-165">Найдите в файле RSReportDesigner.config элемент `Data`.</span><span class="sxs-lookup"><span data-stu-id="425c9-165">Locate the `Data` element in the RSReportDesigner.config file.</span></span> <span data-ttu-id="425c9-166">Элемент для поставщика данных необходимо создать в месте, указанном ниже.</span><span class="sxs-lookup"><span data-stu-id="425c9-166">An entry for the data provider should be made in the following location:</span></span>  
  
    ```  
    <Extensions>  
       <Data>  
          <Extension Your data provider configuration information goes here />  
       </Data>  
    </Extensions>  
    ```  
  
4.  <span data-ttu-id="425c9-167">Добавьте элемент для поставщика данных.</span><span class="sxs-lookup"><span data-stu-id="425c9-167">Add an entry for the data provider.</span></span>  
  
    |<span data-ttu-id="425c9-168">attribute</span><span class="sxs-lookup"><span data-stu-id="425c9-168">Attribute</span></span>|<span data-ttu-id="425c9-169">Описание</span><span class="sxs-lookup"><span data-stu-id="425c9-169">Description</span></span>|  
    |---------------|-----------------|  
    |`Name`|<span data-ttu-id="425c9-170">Уникальное имя поставщика данных, например **MyNETDataProvider**.</span><span class="sxs-lookup"><span data-stu-id="425c9-170">Provide a unique name for the data provider, for example, **MyNETDataProvider**.</span></span> <span data-ttu-id="425c9-171">Длина атрибута `Name` не должна превышать 255 символов.</span><span class="sxs-lookup"><span data-stu-id="425c9-171">The maximum length for the `Name` attribute is 255 characters.</span></span> <span data-ttu-id="425c9-172">Имя должно быть уникальным среди всех элементов, вложенных в элемент `Extension` файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="425c9-172">The name must be unique among all entries within the `Extension` element of a configuration file.</span></span> <span data-ttu-id="425c9-173">Указанное здесь значение отображается в раскрывающемся списке типов источников данных при создании нового источника данных.</span><span class="sxs-lookup"><span data-stu-id="425c9-173">The value that you include here appears in the drop-down list of data source types when you create a new data source.</span></span>|  
    |`Type`|<span data-ttu-id="425c9-174">Список с разделителями-запятыми, включающий полное имя пространства имен для класса, реализующего интерфейс <xref:System.Data.IDbConnection> , а затем имя сборки поставщика [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] (без расширения DLL).</span><span class="sxs-lookup"><span data-stu-id="425c9-174">Enter a comma-separated list that includes the fully qualified namespace of the class that implements the <xref:System.Data.IDbConnection> interface, followed by the name of the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] data provider assembly (not including the .dll file name extension).</span></span>|  
  
     <span data-ttu-id="425c9-175">Например, для DLL-файла, развертываемого в каталоге PrivateAssemblies [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] , новый элемент может выглядеть следующим образом.</span><span class="sxs-lookup"><span data-stu-id="425c9-175">For example, the entry might resemble the following for a DLL deployed to the [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] PrivateAssemblies directory:</span></span>  
  
    ```  
    <Extension Name="MyNETDataProvider" Type="CompanyName.ExtensionName.DataProviderConnectionClass, DataProviderAssembly" />   
    ```  
  
     <span data-ttu-id="425c9-176">Если сборка загружена в глобальный кэш сборок, необходимо задать свойства строгого имени.</span><span class="sxs-lookup"><span data-stu-id="425c9-176">If you load your assembly into the GAC, you must provide the strong name properties.</span></span> <span data-ttu-id="425c9-177">Пример:</span><span class="sxs-lookup"><span data-stu-id="425c9-177">For example:</span></span>  
  
    ```  
    <Extension Name="MyNETDataProvider" Type="CompanyName.ExtensionName.DataProviderConnectionClass, DataProviderAssembly, Version=1.0.0.0, Culture=neutral, PublicKeyToken=MyPublicToken"/>  
    ```  
  
5.  <span data-ttu-id="425c9-178">Найдите в файле RSReportDesigner.config элемент `Designer`.</span><span class="sxs-lookup"><span data-stu-id="425c9-178">Locate the `Designer` element in the RSReportDesigner.config file.</span></span> <span data-ttu-id="425c9-179">Элемент для поставщика данных [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] необходимо создать в месте, указанном ниже.</span><span class="sxs-lookup"><span data-stu-id="425c9-179">An entry for the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] data provider should be made in the following location:</span></span>  
  
    ```  
    <Extensions>  
       <Designer>  
          <Your data provider configuration information goes here>  
       </Designer>  
    </Extensions>  
    ```  
  
6.  <span data-ttu-id="425c9-180">Добавьте в файл RSReportDesigner.config после элемента `Designer` следующий элемент.</span><span class="sxs-lookup"><span data-stu-id="425c9-180">Add the following entry to the RSReportDesigner.config file under the `Designer` element.</span></span> <span data-ttu-id="425c9-181">Атрибут `Name` необходимо заменить именем, которое указывалось в предыдущих элементах.</span><span class="sxs-lookup"><span data-stu-id="425c9-181">You need to replace only the `Name` attribute with the name that you provided in previous entries.</span></span>  
  
    ```  
    <Extension Name="MyNETDataProvider" Type="Microsoft.ReportingServices.QueryDesigners.GenericQueryDesigner,Microsoft.ReportingServices.QueryDesigners"/>  
    ```  
  
#### <a name="to-set-the-code-group-policy-for-a-net-data-provider-on-the-report-designer-client"></a><span data-ttu-id="425c9-182">Настройка групповой политики кода для поставщика данных .NET на клиенте конструктора отчетов</span><span class="sxs-lookup"><span data-stu-id="425c9-182">To set the code group policy for a .NET data provider on the Report Designer client</span></span>  
  
1.  <span data-ttu-id="425c9-183">Создайте резервную копию файла RSPreviewPolicy.config в каталоге PrivateAssemblies.</span><span class="sxs-lookup"><span data-stu-id="425c9-183">Make a backup copy of the RSPreviewPolicy.config file in the PrivateAssemblies directory.</span></span>  
  
2.  <span data-ttu-id="425c9-184">Откройте файл RSPreviewPolicy.config с помощью среды [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] или простого текстового редактора (например Блокнота).</span><span class="sxs-lookup"><span data-stu-id="425c9-184">Open RSPreviewPolicy.config with [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] or a simple text editor, such as Notepad.</span></span>  
  
3.  <span data-ttu-id="425c9-185">Найдите в файле RSPreviewPolicy.config элемент `CodeGroup`.</span><span class="sxs-lookup"><span data-stu-id="425c9-185">Locate the `CodeGroup` element in the RSPreviewPolicy.config file.</span></span>  
  
4.  <span data-ttu-id="425c9-186">Добавьте группу кода для сборки поставщика данных [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], предоставляющую разрешение `FullTrust`,</span><span class="sxs-lookup"><span data-stu-id="425c9-186">Add a code group for the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] data provider assembly that grants `FullTrust` permission.</span></span> <span data-ttu-id="425c9-187">как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="425c9-187">Your code group might resemble the following:</span></span>  
  
    ```  
    <CodeGroup class="UnionCodeGroup"  
       version="1"  
       PermissionSetName="FullTrust"  
       Name="ThisDataProviderCodeGroup"  
       Description="Code group for the .NET data provider">  
          <IMembershipCondition class="UrlMembershipCondition"  
             version="1"  
             Url=  
    " C:\Program Files\Microsoft Visual Studio 9\Common7\IDE\PrivateAssemblies\DataProviderAssembly.dll"  
           />  
    </CodeGroup>  
    ```  
  
 <span data-ttu-id="425c9-188">Членство URL — это лишь одно из множества условий членства, которые должны быть заданы для поставщика данных.</span><span class="sxs-lookup"><span data-stu-id="425c9-188">URL membership is only one of many membership conditions you might select for the data provider.</span></span>  
  
### <a name="verifying-the-deployment-and-registration-on-the-report-designer-client"></a><span data-ttu-id="425c9-189">Проверка развертывания и регистрации на клиенте конструктора отчетов</span><span class="sxs-lookup"><span data-stu-id="425c9-189">Verifying the Deployment and Registration on the Report Designer Client</span></span>  
 <span data-ttu-id="425c9-190">Прежде чем выполнять проверку развертывания, необходимо закрыть все экземпляры среды [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="425c9-190">Before you can verify deployment, you must close all instances of [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] on your local computer.</span></span> <span data-ttu-id="425c9-191">После завершения всех текущих сеансов можно проверить успешность развертывания поставщика данных в конструкторе отчетов, создав с помощью среды [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]новый проект отчета.</span><span class="sxs-lookup"><span data-stu-id="425c9-191">After you have ended all current sessions, you can verify whether your data provider was deployed successfully to Report Designer by creating a new report project in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span></span> <span data-ttu-id="425c9-192">При создании набора данных для отчета поставщик данных должен появиться в списке доступных типов источников данных.</span><span class="sxs-lookup"><span data-stu-id="425c9-192">The data provider should be included in the list of available data source types when you create a new data set for your report.</span></span>  
  
## <a name="platform-considerations"></a><span data-ttu-id="425c9-193">Замечания о платформе</span><span class="sxs-lookup"><span data-stu-id="425c9-193">Platform Considerations</span></span>  
 <span data-ttu-id="425c9-194">На 64-разрядной (x64) платформе среда [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)] выполняется в 32-разрядном режиме WOW.</span><span class="sxs-lookup"><span data-stu-id="425c9-194">On a 64-bit (x64) platform, [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)] runs in 32-bit WOW mode.</span></span> <span data-ttu-id="425c9-195">При разработке отчетов на платформе x64, для обеспечения их просмотра на клиенте конструктора отчетов необходимо установить 32-разрядную версию поставщика данных.</span><span class="sxs-lookup"><span data-stu-id="425c9-195">When you author reports on an x64 platform, you need 32-bit data providers installed on the report authoring client in order to preview your reports.</span></span> <span data-ttu-id="425c9-196">Если отчет публикуется в той же системе, необходимо установить поставщики данных x64 для просмотра отчетов с помощью диспетчера отчетов.</span><span class="sxs-lookup"><span data-stu-id="425c9-196">If you publish the report on the same system, you need x64 data providers to view the report with Report Manager.</span></span>  
  
 [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)] <span data-ttu-id="425c9-197">не поддерживается платформами на базе [!INCLUDE[vcpritanium](../../includes/vcpritanium-md.md)].</span><span class="sxs-lookup"><span data-stu-id="425c9-197">is not supported for [!INCLUDE[vcpritanium](../../includes/vcpritanium-md.md)]-based platforms.</span></span>  
  
 <span data-ttu-id="425c9-198">Модули обработки данных, установленные в службах [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] , должны быть скомпилированы для каждой из платформ и установлены в соответствующие каталоги.</span><span class="sxs-lookup"><span data-stu-id="425c9-198">The data processing extensions that are installed with [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] must be compiled natively for each platform and installed in the correct locations.</span></span> <span data-ttu-id="425c9-199">Если регистрируется пользовательский или стандартный поставщик данных [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] , то он должен быть скомпилирован для целевой платформы и установлен в соответствующий каталог.</span><span class="sxs-lookup"><span data-stu-id="425c9-199">If you register a custom data provider or a standard [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] data provider, it needs to be compiled natively for the appropriate platform and installed the appropriate locations.</span></span> <span data-ttu-id="425c9-200">При работе на 32-разрядной платформе поставщик данных должен быть скомпилирован для 32-разрядной платформы,</span><span class="sxs-lookup"><span data-stu-id="425c9-200">If you are running on a 32-bit platform, the data provider must be compiled for a 32-bit platform.</span></span> <span data-ttu-id="425c9-201">а при работе на 64-разрядной платформе — для 64-разрядной платформы.</span><span class="sxs-lookup"><span data-stu-id="425c9-201">If you are running on a 64-bit platform, the data provider must be compiled for the 64-bit platform.</span></span> <span data-ttu-id="425c9-202">32-разрядный поставщик данных с 64-разрядными интерфейсами на 64-разрядной платформе использовать нельзя.</span><span class="sxs-lookup"><span data-stu-id="425c9-202">You cannot use a 32-bit data provider wrapped with 64-bit interfaces on a 64 bit platform.</span></span> <span data-ttu-id="425c9-203">Сведения о работоспособности на установленной платформе поставщика данных сторонней разработки см. в документации по этому программному обеспечению.</span><span class="sxs-lookup"><span data-stu-id="425c9-203">Check your third-party software for information about whether the data provider will work on the installed platform.</span></span> <span data-ttu-id="425c9-204">Дополнительные сведения о поставщиках данных и поддержке платформ см. в разделе [Источники данных, поддерживаемые службами Reporting Services (службы SSRS)](../create-deploy-and-manage-mobile-and-paginated-reports.md).</span><span class="sxs-lookup"><span data-stu-id="425c9-204">For more information about data providers and platform support, see [Data Sources Supported by Reporting Services &#40;SSRS&#41;](../create-deploy-and-manage-mobile-and-paginated-reports.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="425c9-205">См. также:</span><span class="sxs-lookup"><span data-stu-id="425c9-205">See Also</span></span>  
 <span data-ttu-id="425c9-206">[Настройка и администрирование сервера отчетов (службы Reporting Services в собственном режиме)](../report-server/configure-and-administer-a-report-server-ssrs-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="425c9-206">[Configure and Administer a Report Server &#40;SSRS Native Mode&#41;](../report-server/configure-and-administer-a-report-server-ssrs-native-mode.md) </span></span>  
 <span data-ttu-id="425c9-207">[Реализация модуля обработки данных](../extensions/data-processing/implementing-a-data-processing-extension.md) </span><span class="sxs-lookup"><span data-stu-id="425c9-207">[Implementing a Data Processing Extension](../extensions/data-processing/implementing-a-data-processing-extension.md) </span></span>  
 <span data-ttu-id="425c9-208">[Файлы конфигурации служб Reporting Services](../report-server/reporting-services-configuration-files.md) </span><span class="sxs-lookup"><span data-stu-id="425c9-208">[Reporting Services Configuration Files](../report-server/reporting-services-configuration-files.md) </span></span>  
 [<span data-ttu-id="425c9-209">Управление доступом для кода в службах Reporting Services</span><span class="sxs-lookup"><span data-stu-id="425c9-209">Code Access Security in Reporting Services</span></span>](../extensions/secure-development/code-access-security-in-reporting-services.md)  
  
  
