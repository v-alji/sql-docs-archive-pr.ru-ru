---
title: Тип подключения к Oracle (службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 9db86dd2-beda-42d8-8af7-2629d58a8e3d
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: e9bf19953c5d2dc2f818eddcacf445e641972d4e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663992"
---
# <a name="oracle-connection-type-ssrs"></a><span data-ttu-id="eed67-102">Тип соединения Oracle (службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="eed67-102">Oracle Connection Type (SSRS)</span></span>
  <span data-ttu-id="eed67-103">Чтобы использовать в отчете данные из базы данных Oracle, необходимо иметь набор данных, основанный на источнике данных Oracle.</span><span class="sxs-lookup"><span data-stu-id="eed67-103">To use data from an Oracle database in your report, you must you must have a dataset that is based on a report data source of type Oracle.</span></span> <span data-ttu-id="eed67-104">Этот встроенный тип источника данных основан на управляемом поставщике .NET Framework для Oracle и требует наличия клиентского программного обеспечения Oracle.</span><span class="sxs-lookup"><span data-stu-id="eed67-104">This built-in data source type is based on the .NET Framework Managed Provider for Oracle and requires an Oracle client software component.</span></span>  
  
 <span data-ttu-id="eed67-105">Используйте сведения в этом разделе для создания источника данных.</span><span class="sxs-lookup"><span data-stu-id="eed67-105">Use the information in this topic to build a data source.</span></span> <span data-ttu-id="eed67-106">Пошаговые инструкции см. в статьях [Добавление и проверка подключения к данным или источника данных &#40;построитель отчетов и служб SSRS&#41;](add-and-verify-a-data-connection-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="eed67-106">For step-by-step instructions, see [Add and Verify a Data Connection or Data Source &#40;Report Builder and SSRS&#41;](add-and-verify-a-data-connection-report-builder-and-ssrs.md).</span></span>  
  
##  <a name="connection-string"></a><a name="Connection"></a><span data-ttu-id="eed67-107">Строка подключения</span><span class="sxs-lookup"><span data-stu-id="eed67-107">Connection String</span></span>  
 <span data-ttu-id="eed67-108">Данные для строки соединения и учетные данные для подключения к источнику данных можно получить у администратора базы данных.</span><span class="sxs-lookup"><span data-stu-id="eed67-108">Contact your database administrator for connection information and for the credentials to use to connect to the data source.</span></span> <span data-ttu-id="eed67-109">В следующем примере строки соединения указывается база данных Oracle на сервере Oracle9 с использованием Юникода.</span><span class="sxs-lookup"><span data-stu-id="eed67-109">The following connection string example specifies an Oracle database on the server named "Oracle9" using Unicode.</span></span> <span data-ttu-id="eed67-110">Имя сервера должно соответствовать значению, определенному в файле конфигурации tnsnames.ora в качестве имени экземпляра сервера Oracle.</span><span class="sxs-lookup"><span data-stu-id="eed67-110">The server name must match what is defined in the Tnsnames.ora configuration file as the Oracle server instance name.</span></span>  
  
```  
Data Source="Oracle9"; Unicode="True"  
```  
  
 <span data-ttu-id="eed67-111">Дополнительные сведения о примерах строки подключения см. в разделе [Подключения к данным, источники данных и строки подключения в построителе отчетов](../data-connections-data-sources-and-connection-strings-in-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="eed67-111">For more information about connection string examples, see [Data Connections, Data Sources, and Connection Strings in Report Builder](../data-connections-data-sources-and-connection-strings-in-report-builder.md).</span></span>  
  
##  <a name="credentials"></a><a name="Credentials"></a><span data-ttu-id="eed67-112">Информации</span><span class="sxs-lookup"><span data-stu-id="eed67-112">Credentials</span></span>  
 <span data-ttu-id="eed67-113">Учетные данные необходимы для запуска запросов, локального предварительного просмотра отчетов, а также для предварительного просмотра отчетов на сервере отчетов.</span><span class="sxs-lookup"><span data-stu-id="eed67-113">Credentials are required to run queries, to preview the report locally, and to preview the report from the report server.</span></span>  
  
 <span data-ttu-id="eed67-114">После публикации отчета может понадобиться изменить учетные данные источника данных, чтобы разрешения, необходимые для получения данных при запуске отчета на сервере отчетов, были допустимыми.</span><span class="sxs-lookup"><span data-stu-id="eed67-114">After you publish your report, you may need to change the credentials for the data source so that when the report runs on the report server, the permissions to retrieve the data are valid.</span></span>  
  
 <span data-ttu-id="eed67-115">Дополнительные сведения см. в разделе [подключения к данным, источники данных и строки подключения в Reporting Services](../data-connections-data-sources-and-connection-strings-in-reporting-services.md) или [укажите учетные данные в построитель отчетов](../specify-credentials-in-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="eed67-115">For more information, see [Data Connections, Data Sources, and Connection Strings in Reporting Services](../data-connections-data-sources-and-connection-strings-in-reporting-services.md) or [Specify Credentials in Report Builder](../specify-credentials-in-report-builder.md).</span></span>  
  

  
##  <a name="queries"></a><a name="Query"></a><span data-ttu-id="eed67-116">Запроса</span><span class="sxs-lookup"><span data-stu-id="eed67-116">Queries</span></span>  
 <span data-ttu-id="eed67-117">Для создания набора данных можно выбрать хранимую процедуру из раскрывающегося списка или создать SQL-запрос.</span><span class="sxs-lookup"><span data-stu-id="eed67-117">To create a dataset, you can either select a stored procedure from a drop-down list or create an SQL query.</span></span> <span data-ttu-id="eed67-118">Чтобы построить запрос, воспользуйтесь текстовым конструктором запросов.</span><span class="sxs-lookup"><span data-stu-id="eed67-118">To build a query, you must use the text-based query designer.</span></span> <span data-ttu-id="eed67-119">Дополнительные сведения см. в разделе [Пользовательский интерфейс текстового конструктора запросов (построитель отчетов)](text-based-query-designer-user-interface-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="eed67-119">For more information, see [Text-based Query Designer User Interface &#40;Report Builder&#41;](text-based-query-designer-user-interface-report-builder.md).</span></span>  
  
 <span data-ttu-id="eed67-120">Можно указать хранимые процедуры, возвращающие только один результирующий набор.</span><span class="sxs-lookup"><span data-stu-id="eed67-120">You can specify stored procedures that return only one result set.</span></span> <span data-ttu-id="eed67-121">Использование курсорных запросов не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="eed67-121">Using cursor-based queries are not supported.</span></span>  
  
##  <a name="parameters"></a><a name="Parameters"></a> <span data-ttu-id="eed67-122">Параметры</span><span class="sxs-lookup"><span data-stu-id="eed67-122">Parameters</span></span>  
 <span data-ttu-id="eed67-123">Если запрос включает переменные запроса, то автоматически создаются соответствующие параметры отчета.</span><span class="sxs-lookup"><span data-stu-id="eed67-123">If the query includes query variables, corresponding report parameters are automatically generated.</span></span> <span data-ttu-id="eed67-124">Этот модуль поддерживает именованные параметры.</span><span class="sxs-lookup"><span data-stu-id="eed67-124">Named parameters are supported by this extension.</span></span> <span data-ttu-id="eed67-125">Oracle версии 9 или более поздней поддерживает параметры с несколькими значениями.</span><span class="sxs-lookup"><span data-stu-id="eed67-125">For Oracle version 9 or later, multivalue parameters are supported.</span></span>  
  
 <span data-ttu-id="eed67-126">Параметры отчета создаются со значениями свойств по умолчанию, которые, возможно, потребуется изменить.</span><span class="sxs-lookup"><span data-stu-id="eed67-126">Report parameters are created with default property values that you might need to modify.</span></span> <span data-ttu-id="eed67-127">Например, все параметры отчета имеют тип данных **Text**.</span><span class="sxs-lookup"><span data-stu-id="eed67-127">For example, each report parameter is data type **Text**.</span></span> <span data-ttu-id="eed67-128">После создания параметров отчета можно изменить значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="eed67-128">After the report parameters are created, you might have to change default values.</span></span> <span data-ttu-id="eed67-129">Дополнительные сведения см. в разделе [Параметры отчета (построитель отчетов и конструктор отчетов)](../report-design/report-parameters-report-builder-and-report-designer.md).</span><span class="sxs-lookup"><span data-stu-id="eed67-129">For more information, see [Report Parameters &#40;Report Builder and Report Designer&#41;](../report-design/report-parameters-report-builder-and-report-designer.md).</span></span>  
  

  
##  <a name="remarks"></a><a name="Remarks"></a> <span data-ttu-id="eed67-130">Замечания</span><span class="sxs-lookup"><span data-stu-id="eed67-130">Remarks</span></span>  
 <span data-ttu-id="eed67-131">Прежде чем подключиться к источнику данных Oracle, системный администратор должен установить версию поставщика данных .NET для Oracle, поддерживающую получение данных из базы данных Oracle.</span><span class="sxs-lookup"><span data-stu-id="eed67-131">Before you can connect an Oracle data source, the system administrator must have installed the version of the .NET Data Provider for Oracle that supports retrieving data from the Oracle database.</span></span> <span data-ttu-id="eed67-132">Этот поставщик данных должен быть установлен на компьютере, где работает построитель отчетов, а также на сервере отчетов.</span><span class="sxs-lookup"><span data-stu-id="eed67-132">This data provider must be installed on the same computer as Report Builder and also on the report server.</span></span>  
  
 <span data-ttu-id="eed67-133">Дополнительные сведения см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="eed67-133">For more information, see the following:</span></span>  
  
-   <span data-ttu-id="eed67-134">[Использование поставщика данных .NET Framework для Oracle](https://go.microsoft.com/fwlink/?LinkId=112314) на узле msdn.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="eed67-134">[Using the .NET Framework Data Provider for Oracle](https://go.microsoft.com/fwlink/?LinkId=112314) on msdn.microsoft.com</span></span>  
  
-   [<span data-ttu-id="eed67-135">Как использовать службы Reporting Services для настройки и доступа к источнику данных Oracle</span><span class="sxs-lookup"><span data-stu-id="eed67-135">How to use Reporting Services to configure and to access an Oracle data source</span></span>](https://support.microsoft.com/kb/834305)  
  
-   [<span data-ttu-id="eed67-136">Как добавить разрешения для субъекта безопасности NETWORK SERVICE</span><span class="sxs-lookup"><span data-stu-id="eed67-136">How to add permissions for the NETWORK SERVICE security principal</span></span>](https://support.microsoft.com/kb/870668)  
  
###### <a name="alternate-data-extensions"></a><span data-ttu-id="eed67-137">Альтернативные модули обработки данных</span><span class="sxs-lookup"><span data-stu-id="eed67-137">Alternate Data Extensions</span></span>  
 <span data-ttu-id="eed67-138">Также данные из базы данных Oracle можно получить с помощью источника данных OLE DB.</span><span class="sxs-lookup"><span data-stu-id="eed67-138">You can also retrieve data from an Oracle database by using an OLE DB data source type.</span></span> <span data-ttu-id="eed67-139">Дополнительные сведения см. в разделе [Тип соединения OLE DB (службы SSRS)](ole-db-connection-type-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="eed67-139">For more information, see [OLE DB Connection Type &#40;SSRS&#41;](ole-db-connection-type-ssrs.md).</span></span>  
  
###### <a name="report-models"></a><span data-ttu-id="eed67-140">Модели отчетов</span><span class="sxs-lookup"><span data-stu-id="eed67-140">Report Models</span></span>  
 <span data-ttu-id="eed67-141">Также можно создавать модели на основе базы данных Oracle.</span><span class="sxs-lookup"><span data-stu-id="eed67-141">You can also create models based on an Oracle database.</span></span>  
  
###### <a name="platform-and-version-information"></a><span data-ttu-id="eed67-142">Сведения о платформе и версии</span><span class="sxs-lookup"><span data-stu-id="eed67-142">Platform and Version Information</span></span>  
 <span data-ttu-id="eed67-143">Дополнительные сведения о поддержке платформ и версий см. в разделе [Источники данных, поддерживаемые службами Reporting Services (службы SSRS)](../create-deploy-and-manage-mobile-and-paginated-reports.md) документации к [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] в [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [электронной документации](https://go.microsoft.com/fwlink/?linkid=121312) по .</span><span class="sxs-lookup"><span data-stu-id="eed67-143">For more information about platform and version support, see [Data Sources Supported by Reporting Services &#40;SSRS&#41;](../create-deploy-and-manage-mobile-and-paginated-reports.md) in the [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] documentation in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [Books Online](https://go.microsoft.com/fwlink/?linkid=121312).</span></span>  
  

  
##  <a name="how-to-topics"></a><a name="HowTo"></a><span data-ttu-id="eed67-144">Разделы руководства</span><span class="sxs-lookup"><span data-stu-id="eed67-144">How-To Topics</span></span>  
 <span data-ttu-id="eed67-145">В этом разделе содержатся пошаговые инструкции по работе с подключениями к данным, источниками данных и наборами данных.</span><span class="sxs-lookup"><span data-stu-id="eed67-145">This section contains step-by-step instructions for working with data connections, data sources, and datasets.</span></span>  
  
 [<span data-ttu-id="eed67-146">Добавление и проверка подключения к данным или источника данных &#40;построитель отчетов и служб SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="eed67-146">Add and Verify a Data Connection or Data Source &#40;Report Builder and SSRS&#41;</span></span>](add-and-verify-a-data-connection-report-builder-and-ssrs.md)  
  
 [<span data-ttu-id="eed67-147">Создание общего или внедренного набора данных (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="eed67-147">Create a Shared Dataset or Embedded Dataset &#40;Report Builder and SSRS&#41;</span></span>](create-a-shared-dataset-or-embedded-dataset-report-builder-and-ssrs.md)  
  
 [<span data-ttu-id="eed67-148">Добавление фильтра к набору данных (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="eed67-148">Add a Filter to a Dataset &#40;Report Builder and SSRS&#41;</span></span>](add-a-filter-to-a-dataset-report-builder-and-ssrs.md)  
  
 
  
##  <a name="related-sections"></a><a name="Related"></a> <span data-ttu-id="eed67-149">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="eed67-149">Related Sections</span></span>  
 <span data-ttu-id="eed67-150">В этих разделах документации содержатся подробные сведения о данных отчетов, а также методические сведения об определении, настройке и использовании элементов отчетов, связанных с данными.</span><span class="sxs-lookup"><span data-stu-id="eed67-150">These sections of the documentation provide in-depth conceptual information about report data, as well as procedural information about how to define, customize, and use parts of a report that are related to data.</span></span>  
  
 [<span data-ttu-id="eed67-151">Добавление данных в построитель отчетов &#40;отчетов и SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="eed67-151">Add Data to a Report &#40;Report Builder and SSRS&#41;</span></span>](report-datasets-ssrs.md)  
 <span data-ttu-id="eed67-152">Предоставляет общие сведения о доступе к данным отчета.</span><span class="sxs-lookup"><span data-stu-id="eed67-152">Provides an overview of accessing data for your report.</span></span>  
  
 [<span data-ttu-id="eed67-153">Подключения к данным, источники данных и строки подключения в построителе отчетов</span><span class="sxs-lookup"><span data-stu-id="eed67-153">Data Connections, Data Sources, and Connection Strings in Report Builder</span></span>](../data-connections-data-sources-and-connection-strings-in-report-builder.md)  
 <span data-ttu-id="eed67-154">Предоставляет сведения о подключениях к данным и источникам данных.</span><span class="sxs-lookup"><span data-stu-id="eed67-154">Provides information about data connections and data sources.</span></span>  
  
 [<span data-ttu-id="eed67-155">Внедренные и общие наборы данных отчета (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="eed67-155">Report Embedded Datasets and Shared Datasets &#40;Report Builder and SSRS&#41;</span></span>](report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md)  
 <span data-ttu-id="eed67-156">Предоставляет сведения об общих и внедренных наборах данных.</span><span class="sxs-lookup"><span data-stu-id="eed67-156">Provides information about embedded and shared datasets.</span></span>  
  
 [<span data-ttu-id="eed67-157">Коллекция полей набора данных (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="eed67-157">Dataset Fields Collection &#40;Report Builder and SSRS&#41;</span></span>](dataset-fields-collection-report-builder-and-ssrs.md)  
 <span data-ttu-id="eed67-158">Предоставляет сведения о коллекции полей набора данных, создаваемой запросом.</span><span class="sxs-lookup"><span data-stu-id="eed67-158">Provides information about the dataset field collection generated by the query.</span></span>  
  
 <span data-ttu-id="eed67-159">[Источники данных, поддерживаемые службами Reporting Services &#40;SSRS&#41;](../create-deploy-and-manage-mobile-and-paginated-reports.md), см. в документации [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] в [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [электронной документации](https://go.microsoft.com/fwlink/?linkid=121312).</span><span class="sxs-lookup"><span data-stu-id="eed67-159">[Data Sources Supported by Reporting Services &#40;SSRS&#41;](../create-deploy-and-manage-mobile-and-paginated-reports.md) in the [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] documentation in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [Books Online](https://go.microsoft.com/fwlink/?linkid=121312).</span></span>  
 <span data-ttu-id="eed67-160">Предоставляет подробные сведения о поддержке платформ и версий для каждого модуля обработки данных.</span><span class="sxs-lookup"><span data-stu-id="eed67-160">Provides in-depth information about platform and version support for each data extension.</span></span>  
  

  
## <a name="see-also"></a><span data-ttu-id="eed67-161">См. также:</span><span class="sxs-lookup"><span data-stu-id="eed67-161">See Also</span></span>  
 <span data-ttu-id="eed67-162">[Параметры отчета &#40;построитель отчетов и конструктор отчетов&#41;](../report-design/report-parameters-report-builder-and-report-designer.md) </span><span class="sxs-lookup"><span data-stu-id="eed67-162">[Report Parameters &#40;Report Builder and Report Designer&#41;](../report-design/report-parameters-report-builder-and-report-designer.md) </span></span>  
 <span data-ttu-id="eed67-163">[Фильтрация, группировка и сортировка данных &#40;построитель отчетов и SSRS&#41;](../report-design/filter-group-and-sort-data-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="eed67-163">[Filter, Group, and Sort Data &#40;Report Builder and SSRS&#41;](../report-design/filter-group-and-sort-data-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="eed67-164">Выражения (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="eed67-164">Expressions &#40;Report Builder and SSRS&#41;</span></span>](../report-design/expressions-report-builder-and-ssrs.md)  
  
  
