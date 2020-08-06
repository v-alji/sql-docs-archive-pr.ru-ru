---
title: Доступ к поставщику WMI для служб Reporting Services | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- Reporting Services WMI Provider
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- WMI provider [Reporting Services]
- programming [Reporting Services]
ms.assetid: 22cfbeb8-4ea3-4182-8f54-3341c771e87b
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: db0848ae8c988229a1804bbd4b19e6c38b68c35f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87737928"
---
# <a name="access-the-reporting-services-wmi-provider"></a><span data-ttu-id="76b2b-102">Доступ к поставщику WMI для служб Reporting Services</span><span class="sxs-lookup"><span data-stu-id="76b2b-102">Access the Reporting Services WMI Provider</span></span>
  <span data-ttu-id="76b2b-103">Поставщик WMI служб Reporting Services отображает два класса WMI для администрирования экземпляров серверов отчетов, работающих в собственном режиме, путем создания сценариев:</span><span class="sxs-lookup"><span data-stu-id="76b2b-103">The Reporting Services WMI provider exposes two WMI classes for administration of Native mode report server instances through scripting:</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="76b2b-104">Начиная с выпуска [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] , поставщик WMI поддерживается только для серверов отчетов, работающих в собственном режиме.</span><span class="sxs-lookup"><span data-stu-id="76b2b-104">Starting with the [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] release, the WMI provider is supported for only native mode report servers.</span></span> <span data-ttu-id="76b2b-105">Серверы отчетов служб в режиме интеграции с SharePoint могут управляться со страниц центра администрирования SharePoint и с помощью скриптов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="76b2b-105">SharePoint mode report servers can be managed with SharePoint Central Administration pages and PowerShell scripts.</span></span>  
  
|<span data-ttu-id="76b2b-106">Class</span><span class="sxs-lookup"><span data-stu-id="76b2b-106">Class</span></span>|<span data-ttu-id="76b2b-107">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="76b2b-107">Namespace</span></span>|<span data-ttu-id="76b2b-108">Description</span><span class="sxs-lookup"><span data-stu-id="76b2b-108">Description</span></span>|  
|-----------|---------------|-----------------|  
|<span data-ttu-id="76b2b-109">MSReportServer_Instance</span><span class="sxs-lookup"><span data-stu-id="76b2b-109">MSReportServer_Instance</span></span>|<span data-ttu-id="76b2b-110">Рут\микрософт\склсервер\репортсервер\ RS_ *\<EncodedInstanceName>* \v11</span><span class="sxs-lookup"><span data-stu-id="76b2b-110">root\Microsoft\SqlServer\ReportServer\RS_*\<EncodedInstanceName>* \v11</span></span>|<span data-ttu-id="76b2b-111">Основные сведения, необходимые клиенту для подключения к установленному серверу отчетов.</span><span class="sxs-lookup"><span data-stu-id="76b2b-111">Provides basic information required for a client to connect to an installed report server.</span></span>|  
|<span data-ttu-id="76b2b-112">MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="76b2b-112">MSReportServer_ConfigurationSetting</span></span>|<span data-ttu-id="76b2b-113">Рут\микрософт\склсервер\репортсервер\ RS_ *\<EncodedInstanceName>* \v11\Admin</span><span class="sxs-lookup"><span data-stu-id="76b2b-113">root\Microsoft\SqlServer\ReportServer\RS_*\<EncodedInstanceName>* \v11\Admin</span></span>|<span data-ttu-id="76b2b-114">Представляет установочные параметры и параметры времени выполнения для экземпляра сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="76b2b-114">Represents the installation and run-time parameters of a report server instance.</span></span> <span data-ttu-id="76b2b-115">Эти параметры хранятся в файле конфигурации для сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="76b2b-115">These parameters are stored in the configuration file for the report server.</span></span><br /><br /> <span data-ttu-id="76b2b-116">**\*\* Важно. \*\*** Этот класс доступен только для пользователей с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="76b2b-116">**\*\* Important \*\*** This class is only accessible with administrative privileges.</span></span>|  
  
 <span data-ttu-id="76b2b-117">Экземпляр каждого из перечисленных выше классов создается для каждого экземпляра сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="76b2b-117">An instance of each of the above classes is created for each report server instance.</span></span> <span data-ttu-id="76b2b-118">Вы можете использовать любые средства Microsoft или сторонних производителей для получения доступа к объектам WMI, которые отображаются сервером отчетов, включая программные интерфейсы WMI, отображаемые самой платформой .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="76b2b-118">You can use any Microsoft or third party tools to access the WMI objects exposed by the report server, including WMI programming interfaces exposed by the .NET Framework itself.</span></span> <span data-ttu-id="76b2b-119">В этом разделе рассматривается процедура получения доступа и использования экземпляров классов WMI с помощью команды PowerShell [Get-WmiObject](https://technet.microsoft.com/library/dd315295.aspx).</span><span class="sxs-lookup"><span data-stu-id="76b2b-119">This topic describes how to access and use the WMI class instances with the PowerShell command [Get-WmiObject](https://technet.microsoft.com/library/dd315295.aspx).</span></span>  
  
## <a name="determine-the-instance-name-in-the-namespace-string"></a><span data-ttu-id="76b2b-120">Определение имени экземпляра в строке пространства имен</span><span class="sxs-lookup"><span data-stu-id="76b2b-120">Determine the Instance Name in the Namespace String</span></span>  
 <span data-ttu-id="76b2b-121">Имя экземпляра в пути к пространству имен для классов WMI служб Reporting Services представляет собой кодировку имен экземпляра, которая указывается вами при установке именованных экземпляров служб Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="76b2b-121">The instance name in the namespace path for the Reporting Services WMI classes is an encoding of the instance names that you specify when installing the named Reporting Services instances.</span></span> <span data-ttu-id="76b2b-122">Конкретно в именах экземплярах кодируются специальные символы.</span><span class="sxs-lookup"><span data-stu-id="76b2b-122">Namely, special characters in the instance names are encoded.</span></span> <span data-ttu-id="76b2b-123">Например, подчеркивающая линия (_) кодируется как _5f, поэтому имя экземпляра My_Instance в пути к пространству имен WMI будет закодировано как My_5fInstance.</span><span class="sxs-lookup"><span data-stu-id="76b2b-123">For example, an underline (_) is encoded as "_5f", so an instance name of "My_Instance" is encoded as "My_5fInstance" in the WMI namespace path.</span></span>  
  
 <span data-ttu-id="76b2b-124">Для просмотра списка закодированных имен экземпляров вашего сервера отчетов в пути к пространству имен WMI используйте следующую команду PowerShell:</span><span class="sxs-lookup"><span data-stu-id="76b2b-124">To list the encoded instance names of your report server instances in the WMI namespace path, use the following PowerShell command:</span></span>  
  
```powershell
Get-WmiObject -Namespace root\Microsoft\SqlServer\ReportServer -Class __Namespace -ComputerName hostname | Select Name  
```  
  
## <a name="access-the-wmi-classes-using-powershell"></a><span data-ttu-id="76b2b-125">Получение доступа к классам WMI Server с использованием PowerShell</span><span class="sxs-lookup"><span data-stu-id="76b2b-125">Access the WMI Classes Using PowerShell</span></span>  
 <span data-ttu-id="76b2b-126">Для получения доступа к классам WMI выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="76b2b-126">To access the WMI classes, run the following command:</span></span>  
  
```powershell
Get-WmiObject -Namespace <namespacename> -Class <classname> -ComputerName <hostname>  
```  
  
 <span data-ttu-id="76b2b-127">Например, для получения доступа к классу MSReportServer_ConfigurationSetting на экземпляре сервера отчетов по умолчанию узла myrshost, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="76b2b-127">For example, to access the MSReportServer_ConfigurationSetting class on the default report server instance of the host myrshost, run the following command.</span></span> <span data-ttu-id="76b2b-128">Для успешного выполнения данной команды необходимо, чтобы экземпляр сервера отчетов по умолчанию был установлен на узле myrshost.</span><span class="sxs-lookup"><span data-stu-id="76b2b-128">The default report server instance must be installed on myrshost for this command to succeed.</span></span>  
  
```powershell
Get-WmiObject -Namespace "root\Microsoft\SqlServer\ReportServer\RS_MSSQLSERER\v11\Admin" -Class MSReportServer_ConfigurationSetting -ComputerName myrshost  
```  
  
 <span data-ttu-id="76b2b-129">Синтаксис данной команды выводит все имена и значения свойств класса.</span><span class="sxs-lookup"><span data-stu-id="76b2b-129">This command syntax outputs all class property names and values.</span></span> <span data-ttu-id="76b2b-130">Обратите внимание, что несмотря на то, что вы получаете доступ к классу в пространстве имени экземпляра сервера отчетов по умолчанию (RS_MSSQLSERVER), возвращаются все экземпляры класса MSReportServer_ConfigurationSetting.</span><span class="sxs-lookup"><span data-stu-id="76b2b-130">Note that all instances of the class MSReportServer_ConfigurationSetting is returned, even though you are accessing the class in the namespace of the default report server instance (RS_MSSQLSERVER).</span></span> <span data-ttu-id="76b2b-131">Например, если узел myrshost установлен с экземпляром сервера отчетов по умолчанию, а именованный экземпляр сервера отчетов назван SHAREPOINT, то после выполнения данной команды будут возвращены два объекта WMI и выведены имена и значения свойств для обоих экземпляров серверов отчетов.</span><span class="sxs-lookup"><span data-stu-id="76b2b-131">For example, if myrshost is installed with the default report server instance and a named report server instance called SHAREPOINT, this command will return two WMI objects and output the property names and values for both report server instances.</span></span>  
  
 <span data-ttu-id="76b2b-132">Для возвращения определенного экземпляра класса при возвращении нескольких экземпляров, используйте параметр -Filter для фильтрации результатов на основании свойств с уникальными значениями, как, например, InstanceName.</span><span class="sxs-lookup"><span data-stu-id="76b2b-132">To return a specific class instance when multiple instances are returned, use the -Filter parameter to filter the results based on properties with unique values such as InstanceName.</span></span> <span data-ttu-id="76b2b-133">Например, чтобы вернуть только объект WMI для экземпляра сервера отчетов по умолчанию, используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="76b2b-133">For example, to return only the WMI object for the default report server instance, use the following command:</span></span>  
  
```powershell
Get-WmiObject -Namespace "root\Microsoft\SqlServer\ReportServer\RS_MSSQLServer\v11\Admin" -Class MSReportServer_ConfigurationSetting -ComputerName myrshost -Filter "InstanceName='MSSQLSERVER'"  
```  
  
## <a name="query-the-available-methods-and-properties"></a><span data-ttu-id="76b2b-134">Запрос доступных методов и свойств</span><span class="sxs-lookup"><span data-stu-id="76b2b-134">Query the Available Methods and Properties</span></span>  
 <span data-ttu-id="76b2b-135">Для просмотра доступных методов и свойств в одном из классов WMI служб Reporting Services примените результаты из команды Get-WmiObject в команду Get-Member.</span><span class="sxs-lookup"><span data-stu-id="76b2b-135">To see what methods and properties are available in one of the Reporting Services WMI classes, pipe the results from Get-WmiObject to the Get-Member command.</span></span> <span data-ttu-id="76b2b-136">Пример:</span><span class="sxs-lookup"><span data-stu-id="76b2b-136">For example:</span></span>  
  
```powershell
Get-WmiObject -Namespace "root\Microsoft\SqlServer\ReportServer\RS_MSSQLServer\v11\Admin" -Class MSReportServer_ConfigurationSetting -ComputerName myrshost | Get-Member  
```  
  
 <span data-ttu-id="76b2b-137">Документацию по свойствам и методам классов WMI Reporting Services см. в разделе...</span><span class="sxs-lookup"><span data-stu-id="76b2b-137">For documentation on the properties and methods of the Reporting Services WMI classes, see ....</span></span>  
  
## <a name="use-a-wmi-method-or-property"></a><span data-ttu-id="76b2b-138">Использование метода или свойства WMI</span><span class="sxs-lookup"><span data-stu-id="76b2b-138">Use a WMI Method or Property</span></span>  
 <span data-ttu-id="76b2b-139">Вы можете использовать доступные методы и свойства при наличии объектов WMI для классов служб Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="76b2b-139">Once you have the WMI objects to the Reporting Services classes and know the available methods and properties, you can use these methods and properties.</span></span> <span data-ttu-id="76b2b-140">Например, при наличии именованного экземпляра сервера отчетов в режиме интеграции с SharePoint с названием SHAREPOINT можно использовать следующую последовательность команд для получения URL-адреса для сайта центра администрирования SharePoint:</span><span class="sxs-lookup"><span data-stu-id="76b2b-140">For example, if you have a named report server instance in SharePoint integrated mode called SHAREPOINT, use the following command sequence to retrieve the URL for the SharePoint Central Administration site:</span></span>  
  
```powershell
$rsconfig = Get-WmiObject -Namespace "root\Microsoft\SqlServer\ReportServer\RS_MSSQLServer\v11\Admin" -Class MSReportServer_ConfigurationSetting -ComputerName myrshost -Filter "InstanceName='SHAREPOINT'"  
$rsconfig.GetAdminSiteUrl()  
```  
  
## <a name="see-also"></a><span data-ttu-id="76b2b-141">См. также:</span><span class="sxs-lookup"><span data-stu-id="76b2b-141">See Also</span></span>
 <span data-ttu-id="76b2b-142">[Справочник по библиотеке поставщика WMI Reporting Services &#40;SSRS&#41;](../wmi-provider-library-reference/reporting-services-wmi-provider-library-reference-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="76b2b-142">[Reporting Services WMI Provider Library Reference &#40;SSRS&#41;](../wmi-provider-library-reference/reporting-services-wmi-provider-library-reference-ssrs.md) </span></span>  
 [<span data-ttu-id="76b2b-143">RSReportServer Configuration File</span><span class="sxs-lookup"><span data-stu-id="76b2b-143">RSReportServer Configuration File</span></span>](../report-server/rsreportserver-config-configuration-file.md)  
