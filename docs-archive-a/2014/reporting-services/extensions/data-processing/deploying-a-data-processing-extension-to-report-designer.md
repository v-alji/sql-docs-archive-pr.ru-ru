---
title: Практическое руководство. Развертывание модуля обработки данных в конструкторе отчетов | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- data processing extensions [Reporting Services], deploying
- assemblies [Reporting Services], data processing extension deployments
ms.assetid: 3614e601-004e-4a16-8388-836ffd67e9dd
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 56bd56e9d8eeeeff1781f22b42cf0eb1ce706fa4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750496"
---
# <a name="how-to-deploy-a-data-processing-extension-to-report-designer"></a><span data-ttu-id="f83d0-102">Руководство. Развертывание модуля обработки данных в конструкторе отчетов</span><span class="sxs-lookup"><span data-stu-id="f83d0-102">How to: Deploy a Data Processing Extension to Report Designer</span></span>
  <span data-ttu-id="f83d0-103">Модули обработки данных используются в конструкторе отчетов для получения и обработки данных в процессе разработки отчетов.</span><span class="sxs-lookup"><span data-stu-id="f83d0-103">Report Designer uses data processing extensions for retrieving and processing data while you are designing reports.</span></span> <span data-ttu-id="f83d0-104">Сборка модуля обработки данных должна быть развернута в конструкторе отчетов как закрытая сборка.</span><span class="sxs-lookup"><span data-stu-id="f83d0-104">You should deploy your data processing extension assembly to Report Designer as a private assembly.</span></span> <span data-ttu-id="f83d0-105">Необходимо также внести запись в файл конфигурации конструктора отчетов, RSReportDesigner.config.</span><span class="sxs-lookup"><span data-stu-id="f83d0-105">You also need to make an entry in the Report Designer configuration file, RSReportDesigner.config.</span></span>  
  
#### <a name="to-deploy-a-data-processing-extension-assembly"></a><span data-ttu-id="f83d0-106">Развертывание сборки модуля обработки данных</span><span class="sxs-lookup"><span data-stu-id="f83d0-106">To deploy a data processing extension assembly</span></span>  
  
1.  <span data-ttu-id="f83d0-107">Скопируйте конкретную сборку из промежуточной папки в каталог конструктора отчетов.</span><span class="sxs-lookup"><span data-stu-id="f83d0-107">Copy your assembly from your staging location to the Report Designer directory.</span></span> <span data-ttu-id="f83d0-108">По умолчанию каталог исполняемых файлов конструктора отчетов расположен в папке C:\Program Files\Microsoft Visual Studio 9.0\Common7\IDE\PrivateAssemblies.</span><span class="sxs-lookup"><span data-stu-id="f83d0-108">The default location of the Report Designer directory is C:\Program Files\Microsoft Visual Studio 9.0\Common7\IDE\PrivateAssemblies.</span></span>  
  
2.  <span data-ttu-id="f83d0-109">После того, как будет скопирован файл сборки, откройте файл RSReportDesigner.config.</span><span class="sxs-lookup"><span data-stu-id="f83d0-109">After the assembly file is copied, open the RSReportDesigner.config file.</span></span> <span data-ttu-id="f83d0-110">Файл RSReportDesigner.config также находится в каталоге конструктора отчетов.</span><span class="sxs-lookup"><span data-stu-id="f83d0-110">The RSReportDesigner.config file is also located in the Report Designer directory.</span></span> <span data-ttu-id="f83d0-111">Необходимо внести запись в этот файл конфигурации для файла сборки развертываемого модуля обработки данных.</span><span class="sxs-lookup"><span data-stu-id="f83d0-111">You need to make an entry in the configuration file for your data processing extension assembly file.</span></span> <span data-ttu-id="f83d0-112">Файл конфигурации можно открыть с помощью [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] или воспользоваться простым текстовым редактором (таким как Блокнот).</span><span class="sxs-lookup"><span data-stu-id="f83d0-112">You can open the configuration file with [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] or with a simple text editor, such as Notepad.</span></span>  
  
3.  <span data-ttu-id="f83d0-113">Найдите в файле RSReportDesigner.config элемент **Data** .</span><span class="sxs-lookup"><span data-stu-id="f83d0-113">Locate the **Data** element in the RSReportDesigner.config file.</span></span> <span data-ttu-id="f83d0-114">Запись для вновь созданного модуля обработки данных необходимо создать в месте, указанном ниже.</span><span class="sxs-lookup"><span data-stu-id="f83d0-114">An entry for your newly created data processing extension should be made in the following location:</span></span>  
  
    ```  
    <Extensions>  
       <Data>  
          <Your extension configuration information goes here>  
       </Data>  
    </Extensions>  
    ```  
  
4.  <span data-ttu-id="f83d0-115">Добавьте запись для модуля обработки данных, включающего элемент **Extension** со значениями `Name` `Type` атрибутов, и `Visible` .</span><span class="sxs-lookup"><span data-stu-id="f83d0-115">Add an entry for your data processing extension which includes an **Extension** element with values for the `Name`, `Type`, and `Visible` attributes.</span></span> <span data-ttu-id="f83d0-116">Эта запись должна иметь следующий вид:</span><span class="sxs-lookup"><span data-stu-id="f83d0-116">Your entry might look like the following:</span></span>  
  
    ```  
    <Extension Name="ExtensionName" Type="CompanyName.ExtensionName.MyConnectionClass, AssemblyName" />  
    ```  
  
     <span data-ttu-id="f83d0-117">По умолчанию `Name` — уникальное имя модуля обработки данных.</span><span class="sxs-lookup"><span data-stu-id="f83d0-117">The value for `Name` is the unique name of the data processing extension.</span></span> <span data-ttu-id="f83d0-118">Значение параметра `Type` представляет собой список с разделителями-запятыми, включающий полное имя пространства имен для класса, реализующего интерфейсы <xref:Microsoft.ReportingServices.Interfaces.IExtension> и <xref:Microsoft.ReportingServices.DataProcessing.IDbConnection>, а затем имя сборки поставщика (без расширения DLL).</span><span class="sxs-lookup"><span data-stu-id="f83d0-118">The value for `Type` is a comma-separated list that includes an entry for the fully qualified namespace of your class that implements the <xref:Microsoft.ReportingServices.Interfaces.IExtension> and <xref:Microsoft.ReportingServices.DataProcessing.IDbConnection> interfaces, followed by the name of your assembly (not including the .dll file extension).</span></span> <span data-ttu-id="f83d0-119">По умолчанию модули обработки данных являются видимыми.</span><span class="sxs-lookup"><span data-stu-id="f83d0-119">By default, data processing extensions are visible.</span></span> <span data-ttu-id="f83d0-120">Чтобы скрыть расширение из пользовательских интерфейсов, например конструктор отчетов, добавьте `Visible` атрибут в элемент **Extension** и задайте для него значение `false` .</span><span class="sxs-lookup"><span data-stu-id="f83d0-120">To hide an extension from user interfaces, such as Report Designer, add a `Visible` attribute to the **Extension** element, and set it to `false`.</span></span>  
  
5.  <span data-ttu-id="f83d0-121">Наконец, добавьте для пользовательской сборки группу кода, которая предоставляет разрешение **FullTrust** для конкретного модуля.</span><span class="sxs-lookup"><span data-stu-id="f83d0-121">Finally, add a code group for your custom assembly that grants **FullTrust** permission for your extension.</span></span> <span data-ttu-id="f83d0-122">С этой целью добавьте указанную группу кода в файл rspreviewpolicy.config, который по умолчанию находится в папке C:\Program Files\Microsoft Visual Studio 9.0\Common7\IDE\PrivateAssemblies.</span><span class="sxs-lookup"><span data-stu-id="f83d0-122">You do this by adding the code group to the rspreviewpolicy.config file located by default in C:\Program Files\Microsoft Visual Studio 9.0\Common7\IDE\PrivateAssemblies.</span></span> <span data-ttu-id="f83d0-123">Пример группы кода показан ниже.</span><span class="sxs-lookup"><span data-stu-id="f83d0-123">Your code group might look like the following:</span></span>  
  
    ```  
    <CodeGroup class="UnionCodeGroup"  
       version="1"  
       PermissionSetName="FullTrust"  
       Name="MyExtensionCodeGroup"  
       Description="Code group for my data processing extension">  
          <IMembershipCondition class="UrlMembershipCondition"  
             version="1"  
             Url="C:\Program Files\Microsoft Visual Studio 9.0\Common7\IDE\PrivateAssemblies\MyExtensionAssembly.dll"  
           />  
    </CodeGroup>  
    ```  
  
 <span data-ttu-id="f83d0-124">URL-членство — это лишь одно из множества условий членства, которые могут быть заданы для модуля обработки данных.</span><span class="sxs-lookup"><span data-stu-id="f83d0-124">URL membership is only one of many membership conditions you might choose for your data processing extension.</span></span> <span data-ttu-id="f83d0-125">Дополнительные сведения об управлении доступом для кода в [!INCLUDE[ssRSversion2005](../../../includes/ssrsversion2005-md.md)] см. в разделе [Безопасная разработка (службы Reporting Services)](../secure-development/secure-development-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="f83d0-125">For more information about code access security in [!INCLUDE[ssRSversion2005](../../../includes/ssrsversion2005-md.md)], see [Secure Development &#40;Reporting Services&#41;](../secure-development/secure-development-reporting-services.md)</span></span>  
  
## <a name="generic-query-designer"></a><span data-ttu-id="f83d0-126">Обычный конструктор запросов</span><span class="sxs-lookup"><span data-stu-id="f83d0-126">Generic Query Designer</span></span>  
 <span data-ttu-id="f83d0-127">В состав конструктора отчетов входит обычный конструктор запросов, который можно применять с пользовательскими модулями обработки данных.</span><span class="sxs-lookup"><span data-stu-id="f83d0-127">Report Designer provides a generic query designer that you can use with custom data processing extensions.</span></span> <span data-ttu-id="f83d0-128">Конструктор состоит из двух панелей: панели запросов и панели результатов.</span><span class="sxs-lookup"><span data-stu-id="f83d0-128">This designer consists of two panes: a query pane and a results pane.</span></span> <span data-ttu-id="f83d0-129">С помощью универсального конструктора можно создавать запросы, не поддерживаемые при использовании графического интерфейса.</span><span class="sxs-lookup"><span data-stu-id="f83d0-129">You can use the generic designer to write queries that are not supported by the graphical interface.</span></span> <span data-ttu-id="f83d0-130">В отличие от графического конструктора запросов, обычный конструктор запросов не проверяет синтаксис запроса и не изменяет структуру запроса.</span><span class="sxs-lookup"><span data-stu-id="f83d0-130">Unlike the graphical query designer, the generic query designer does not check query syntax or restructure the query.</span></span>  
  
#### <a name="to-enable-the-generic-query-designer-for-a-custom-extension"></a><span data-ttu-id="f83d0-131">Включение обычного конструктора запросов для пользовательского модуля</span><span class="sxs-lookup"><span data-stu-id="f83d0-131">To enable the generic query designer for a custom extension</span></span>  
  
-   <span data-ttu-id="f83d0-132">Добавьте следующую запись в файл RSReportDesigner.config в элементе **Designer** , заменив `Name` атрибут именем, указанным в предыдущих записях.</span><span class="sxs-lookup"><span data-stu-id="f83d0-132">Add the following entry to the RSReportDesigner.config file under the **Designer** element, replacing the `Name` attribute with the name that you provided in previous entries.</span></span>  
  
    ```  
    <Extension Name="ExtensionName" Type="Microsoft.ReportingServices.QueryDesigners.GenericQueryDesigner,Microsoft.ReportingServices.QueryDesigners"/>  
    ```  
  
## <a name="verifying-the-deployment"></a><span data-ttu-id="f83d0-133">Проверка развертывания</span><span class="sxs-lookup"><span data-stu-id="f83d0-133">Verifying the Deployment</span></span>  
 <span data-ttu-id="f83d0-134">Прежде чем выполнять проверку развертывания, необходимо закрыть все экземпляры среды [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="f83d0-134">Before you can verify deployment, you must close all instances of [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] on your local computer.</span></span> <span data-ttu-id="f83d0-135">После завершения всех текущих сеансов можно проверить, успешно ли развернут модуль обработки данных в конструкторе отчетов, создав с помощью среды [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] новый проект отчета.</span><span class="sxs-lookup"><span data-stu-id="f83d0-135">After you have ended all current sessions, you can verify whether your data processing extension was deployed successfully to Report Designer by creating a new report project in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span></span> <span data-ttu-id="f83d0-136">При создании набора данных для отчета модуль должен появиться в списке доступных типов источников данных.</span><span class="sxs-lookup"><span data-stu-id="f83d0-136">Your extension should be included in the list of available data source types when you create a new data set for your report.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f83d0-137">См. также:</span><span class="sxs-lookup"><span data-stu-id="f83d0-137">See Also</span></span>  
 <span data-ttu-id="f83d0-138">[Развертывание модуля обработки данных](deploying-a-data-processing-extension.md) </span><span class="sxs-lookup"><span data-stu-id="f83d0-138">[Deploying a Data Processing Extension](deploying-a-data-processing-extension.md) </span></span>  
 <span data-ttu-id="f83d0-139">[Модули служб Reporting Services](../reporting-services-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="f83d0-139">[Reporting Services Extensions](../reporting-services-extensions.md) </span></span>  
 <span data-ttu-id="f83d0-140">[Реализация модуля обработки данных](implementing-a-data-processing-extension.md) </span><span class="sxs-lookup"><span data-stu-id="f83d0-140">[Implementing a Data Processing Extension](implementing-a-data-processing-extension.md) </span></span>  
 [<span data-ttu-id="f83d0-141">Библиотека модулей Reporting Services</span><span class="sxs-lookup"><span data-stu-id="f83d0-141">Reporting Services Extension Library</span></span>](../reporting-services-extension-library.md)  
  
  
