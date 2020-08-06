---
title: Программное включение ведения журнала | Документы Майкрософт
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SQL Server Integration Services packages, logs
- SSIS packages, logs
- Integration Services packages, logs
- SSIS logging
- log providers [Integration Services]
- logs [Integration Services], enabling
- LoggingMode property
- LogProvider object
- packages [Integration Services], logs
ms.assetid: 3222a1ed-83eb-421c-b299-a53b67bba740
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ff7f81aca330960e4e94b0343080a37ded8c1273
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731977"
---
# <a name="enabling-logging-programmatically"></a><span data-ttu-id="1eb69-102">Программное включение ведения журнала</span><span class="sxs-lookup"><span data-stu-id="1eb69-102">Enabling Logging Programmatically</span></span>
  <span data-ttu-id="1eb69-103">Ядро выполнения предоставляет коллекцию объектов <xref:Microsoft.SqlServer.Dts.Runtime.LogProvider>, которые позволяют перехватывать во время проверки и выполнения пакета сведения, относящиеся к конкретному событию.</span><span class="sxs-lookup"><span data-stu-id="1eb69-103">The run-time engine provides a collection of <xref:Microsoft.SqlServer.Dts.Runtime.LogProvider> objects that enable event-specific information to be captured during package validation and execution.</span></span> <span data-ttu-id="1eb69-104">Объекты <xref:Microsoft.SqlServer.Dts.Runtime.LogProvider> доступны для объектов <xref:Microsoft.SqlServer.Dts.Runtime.DtsContainer>, включая объекты <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>, <xref:Microsoft.SqlServer.Dts.Runtime.Package>, <xref:Microsoft.SqlServer.Dts.Runtime.ForLoop> и <xref:Microsoft.SqlServer.Dts.Runtime.ForEachLoop>.</span><span class="sxs-lookup"><span data-stu-id="1eb69-104"><xref:Microsoft.SqlServer.Dts.Runtime.LogProvider> objects are available to <xref:Microsoft.SqlServer.Dts.Runtime.DtsContainer> objects, including the <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>, <xref:Microsoft.SqlServer.Dts.Runtime.Package>, <xref:Microsoft.SqlServer.Dts.Runtime.ForLoop>, and <xref:Microsoft.SqlServer.Dts.Runtime.ForEachLoop> objects.</span></span> <span data-ttu-id="1eb69-105">Ведение журналов включается для индивидуальных контейнеров или пакета в целом.</span><span class="sxs-lookup"><span data-stu-id="1eb69-105">Logging is enabled on individual containers, or on the whole package.</span></span>

 <span data-ttu-id="1eb69-106">Существует несколько типов регистраторов, которые может использовать контейнер.</span><span class="sxs-lookup"><span data-stu-id="1eb69-106">There are several types of log providers that are available for a container to use.</span></span> <span data-ttu-id="1eb69-107">Это повышает гибкость, позволяя создавать и сохранять сведения журнала во многих форматах.</span><span class="sxs-lookup"><span data-stu-id="1eb69-107">This provides the flexibility to create and store log information in many formats.</span></span> <span data-ttu-id="1eb69-108">Включение журналирования для объекта-контейнера выполняется в два этапа: сначала включается ведение журнала, а потом выбирается регистратор журнала.</span><span class="sxs-lookup"><span data-stu-id="1eb69-108">Enlisting a container object in logging is a two-step process: first logging is enabled, and then a log provider is selected.</span></span> <span data-ttu-id="1eb69-109">Свойства контейнера <xref:Microsoft.SqlServer.Dts.Runtime.DtsContainer.LoggingOptions%2A> и <xref:Microsoft.SqlServer.Dts.Runtime.DtsContainer.LoggingMode%2A> используются для указания записываемых в журнал событий и выбора регистратора.</span><span class="sxs-lookup"><span data-stu-id="1eb69-109">The <xref:Microsoft.SqlServer.Dts.Runtime.DtsContainer.LoggingOptions%2A> and <xref:Microsoft.SqlServer.Dts.Runtime.DtsContainer.LoggingMode%2A> properties of the container are used to specify the logged events and to select the log provider.</span></span>

## <a name="enabling-logging"></a><span data-ttu-id="1eb69-110">Включение журнала</span><span class="sxs-lookup"><span data-stu-id="1eb69-110">Enabling Logging</span></span>
 <span data-ttu-id="1eb69-111">Свойство <xref:Microsoft.SqlServer.Dts.Runtime.DtsContainer.LoggingMode%2A>, имеющееся у каждого контейнера, который может осуществлять ведение журнала, определяет, записывается ли информация о событиях контейнера в журнал событий.</span><span class="sxs-lookup"><span data-stu-id="1eb69-111">The <xref:Microsoft.SqlServer.Dts.Runtime.DtsContainer.LoggingMode%2A> property, found in each container that can perform logging, determines whether the container's event information is recorded to the event log.</span></span> <span data-ttu-id="1eb69-112">Этому свойству назначается значение из структуры <xref:Microsoft.SqlServer.Dts.Runtime.DTSLoggingMode>. По умолчанию оно наследуется от родительского контейнера.</span><span class="sxs-lookup"><span data-stu-id="1eb69-112">This property is assigned a value from the <xref:Microsoft.SqlServer.Dts.Runtime.DTSLoggingMode> structure, and is inherited from the container's parent by default.</span></span> <span data-ttu-id="1eb69-113">Если контейнер является пакетом и, следовательно, не имеет родителя, свойство использует значение <xref:Microsoft.SqlServer.Dts.Runtime.DTSLoggingMode.UseParentSetting>, которое по умолчанию равно `Disabled`.</span><span class="sxs-lookup"><span data-stu-id="1eb69-113">If the container is a package, and therefore has no parent, the property uses the <xref:Microsoft.SqlServer.Dts.Runtime.DTSLoggingMode.UseParentSetting>, which defaults to `Disabled`.</span></span>

### <a name="selecting-a-log-provider"></a><span data-ttu-id="1eb69-114">Выбор регистратора</span><span class="sxs-lookup"><span data-stu-id="1eb69-114">Selecting a Log Provider</span></span>
 <span data-ttu-id="1eb69-115">После того как свойству <xref:Microsoft.SqlServer.Dts.Runtime.DtsContainer.LoggingMode%2A> присвоено значение `Enabled`, регистратор добавляется в коллекцию контейнера <xref:Microsoft.SqlServer.Dts.Runtime.SelectedLogProviders> для завершения процесса.</span><span class="sxs-lookup"><span data-stu-id="1eb69-115">After the <xref:Microsoft.SqlServer.Dts.Runtime.DtsContainer.LoggingMode%2A> property is set to `Enabled`, a log provider is added to the <xref:Microsoft.SqlServer.Dts.Runtime.SelectedLogProviders> collection of the container to complete the process.</span></span> <span data-ttu-id="1eb69-116">Коллекция <xref:Microsoft.SqlServer.Dts.Runtime.SelectedLogProviders> доступна через объект <xref:Microsoft.SqlServer.Dts.Runtime.LoggingOptions> и содержит регистраторы, выбранные для данного контейнера.</span><span class="sxs-lookup"><span data-stu-id="1eb69-116">The <xref:Microsoft.SqlServer.Dts.Runtime.SelectedLogProviders> collection is available on the <xref:Microsoft.SqlServer.Dts.Runtime.LoggingOptions> object, and contains the log providers selected for the container.</span></span> <span data-ttu-id="1eb69-117">Метод <xref:Microsoft.SqlServer.Dts.Runtime.SelectedLogProviders.Add%2A> вызывается для создания регистратора и добавления его в коллекцию.</span><span class="sxs-lookup"><span data-stu-id="1eb69-117">The <xref:Microsoft.SqlServer.Dts.Runtime.SelectedLogProviders.Add%2A> method is called to create a provider and add it to the collection.</span></span> <span data-ttu-id="1eb69-118">После этого метод возвращает регистратор, добавленный в коллекцию.</span><span class="sxs-lookup"><span data-stu-id="1eb69-118">The method then returns the log provider that was added to the collection.</span></span> <span data-ttu-id="1eb69-119">Каждый регистратор имеет уникальные параметры настройки, которые устанавливаются с помощью свойства <xref:Microsoft.SqlServer.Dts.Runtime.LogProvider.ConfigString%2A>.</span><span class="sxs-lookup"><span data-stu-id="1eb69-119">Each provider has configuration settings that are unique to that provider, and these properties are set using the <xref:Microsoft.SqlServer.Dts.Runtime.LogProvider.ConfigString%2A> property.</span></span>

 <span data-ttu-id="1eb69-120">В следующей таблице перечислены доступные регистраторы и приведено их описание и значения их свойства <xref:Microsoft.SqlServer.Dts.Runtime.LogProvider.ConfigString%2A>.</span><span class="sxs-lookup"><span data-stu-id="1eb69-120">The following table lists the available log providers, their description, and their <xref:Microsoft.SqlServer.Dts.Runtime.LogProvider.ConfigString%2A> information.</span></span>

|<span data-ttu-id="1eb69-121">Поставщик</span><span class="sxs-lookup"><span data-stu-id="1eb69-121">Provider</span></span>|<span data-ttu-id="1eb69-122">Description</span><span class="sxs-lookup"><span data-stu-id="1eb69-122">Description</span></span>|<span data-ttu-id="1eb69-123">Свойство ConfigString</span><span class="sxs-lookup"><span data-stu-id="1eb69-123">ConfigString property</span></span>|
|--------------|-----------------|---------------------------|
|<span data-ttu-id="1eb69-124">Приложение SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="1eb69-124">SQL Server Profiler</span></span>|<span data-ttu-id="1eb69-125">Создает трассировки SQL, которые могут перехватываться и просматриваться в приложении [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Profiler.</span><span class="sxs-lookup"><span data-stu-id="1eb69-125">Generates SQL traces that may be captured and viewed in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Profiler.</span></span> <span data-ttu-id="1eb69-126">По умолчанию для имени файла данного регистратора используется расширение TRC.</span><span class="sxs-lookup"><span data-stu-id="1eb69-126">The default file name extension for this provider is .trc.</span></span>|<span data-ttu-id="1eb69-127">Настройка не требуется.</span><span class="sxs-lookup"><span data-stu-id="1eb69-127">No configuration is required.</span></span>|
|<span data-ttu-id="1eb69-128">SQL Server</span><span class="sxs-lookup"><span data-stu-id="1eb69-128">SQL Server</span></span>|<span data-ttu-id="1eb69-129">Записывает записи журнала событий в таблицу **sysssislog** любой базы данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1eb69-129">Writes event log entries to the **sysssislog** table in any [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database.</span></span>|<span data-ttu-id="1eb69-130">Регистратор [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] требует указания соединения с базой данных, а также имени базы данных-получателя.</span><span class="sxs-lookup"><span data-stu-id="1eb69-130">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider requires that the connection to the database be specified, and also the target database name.</span></span>|
|<span data-ttu-id="1eb69-131">Текстовый файл</span><span class="sxs-lookup"><span data-stu-id="1eb69-131">Text File</span></span>|<span data-ttu-id="1eb69-132">Записывает записи журнала событий в текстовые файлы в ASCII-кодировке в формате CSV (с разделителями-запятыми).</span><span class="sxs-lookup"><span data-stu-id="1eb69-132">Writes event log entries to ASCII text files in a comma-separated value (CSV) format.</span></span> <span data-ttu-id="1eb69-133">По умолчанию для имени файла для данного регистратора используется расширение LOG.</span><span class="sxs-lookup"><span data-stu-id="1eb69-133">The default file name extension for this provider is .log.</span></span>|<span data-ttu-id="1eb69-134">Имя диспетчера соединения файлов.</span><span class="sxs-lookup"><span data-stu-id="1eb69-134">The name of a file connection manager.</span></span>|
|<span data-ttu-id="1eb69-135">Журнал событий Windows</span><span class="sxs-lookup"><span data-stu-id="1eb69-135">Windows Event Log</span></span>|<span data-ttu-id="1eb69-136">Сохраняет журнальные записи в стандартном журнале событий Windows.</span><span class="sxs-lookup"><span data-stu-id="1eb69-136">Logs to standard Windows Event Log on the local computer in the Application log.</span></span>|<span data-ttu-id="1eb69-137">Настройка не требуется.</span><span class="sxs-lookup"><span data-stu-id="1eb69-137">No configuration is required.</span></span>|
|<span data-ttu-id="1eb69-138">XML-файл</span><span class="sxs-lookup"><span data-stu-id="1eb69-138">XML File</span></span>|<span data-ttu-id="1eb69-139">Записывает записи журнала событий в файл в формате XML.</span><span class="sxs-lookup"><span data-stu-id="1eb69-139">Writes event log entries to XML formatted file.</span></span> <span data-ttu-id="1eb69-140">По умолчанию для имени файла данного регистратора используется расширение XML.</span><span class="sxs-lookup"><span data-stu-id="1eb69-140">The default file name extension for this provider is .xml</span></span>|<span data-ttu-id="1eb69-141">Имя диспетчера соединения файлов.</span><span class="sxs-lookup"><span data-stu-id="1eb69-141">The name of a file connection manager.</span></span>|

 <span data-ttu-id="1eb69-142">События включаются в журнал событий или исключаются из него путем задания свойств контейнера `EventFilterKind` и `EventFilter`.</span><span class="sxs-lookup"><span data-stu-id="1eb69-142">Events are included in or excluded from the event log by setting the `EventFilterKind` and the `EventFilter` properties of the container.</span></span> <span data-ttu-id="1eb69-143">Структура `EventFilterKind` содержит два значения, `ExclusionFilter` и `InclusionFilter`, которые указывают, включаются ли в журнал событий события, добавленные в фильтр `EventFilter`.</span><span class="sxs-lookup"><span data-stu-id="1eb69-143">The `EventFilterKind` structure contains two values, `ExclusionFilter` and `InclusionFilter`, that indicate whether the events that are added to the `EventFilter` are included in the event log.</span></span> <span data-ttu-id="1eb69-144">После этого свойству `EventFilter` назначается строковый массив, содержащий имена событий, подлежащих фильтрации.</span><span class="sxs-lookup"><span data-stu-id="1eb69-144">The `EventFilter` property is then assigned a string array that contains the names of the events that are the subject of the filtering.</span></span>

 <span data-ttu-id="1eb69-145">Следующий код включает ведение журнала для пакета, добавляет регистратор для текстовых файлов в коллекцию <xref:Microsoft.SqlServer.Dts.Runtime.SelectedLogProviders> и указывает список событий, которые должны включаться в выход журнала.</span><span class="sxs-lookup"><span data-stu-id="1eb69-145">The following code enables logging on a package, adds the log provider for Text files to the <xref:Microsoft.SqlServer.Dts.Runtime.SelectedLogProviders> collection, and specifies a list of events to include in the logging output.</span></span>

## <a name="sample"></a><span data-ttu-id="1eb69-146">Образец</span><span class="sxs-lookup"><span data-stu-id="1eb69-146">Sample</span></span>

```csharp
using System;
using Microsoft.SqlServer.Dts.Runtime;

namespace Microsoft.SqlServer.Dts.Samples
{
  class Program
  {
    static void Main(string[] args)
    {
      Package p = new Package();

      ConnectionManager loggingConnection = p.Connections.Add("FILE");
      loggingConnection.ConnectionString = @"C:\SSISPackageLog.txt";

      LogProvider provider = p.LogProviders.Add("DTS.LogProviderTextFile.2");
      provider.ConfigString = loggingConnection.Name;
      p.LoggingOptions.SelectedLogProviders.Add(provider);
      p.LoggingOptions.EventFilterKind = DTSEventFilterKind.Inclusion;
      p.LoggingOptions.EventFilter = new String[] { "OnPreExecute", 
         "OnPostExecute", "OnError", "OnWarning", "OnInformation" };
      p.LoggingMode = DTSLoggingMode.Enabled;

      // Add tasks and other objects to the package.

    }
  }
}
```

```vb
Imports Microsoft.SqlServer.Dts.Runtime

Module Module1

  Sub Main()

    Dim p As Package = New Package()

    Dim loggingConnection As ConnectionManager = p.Connections.Add("FILE")
    loggingConnection.ConnectionString = "C:\SSISPackageLog.txt"

    Dim provider As LogProvider = p.LogProviders.Add("DTS.LogProviderTextFile.2")
    provider.ConfigString = loggingConnection.Name
    p.LoggingOptions.SelectedLogProviders.Add(provider)
    p.LoggingOptions.EventFilterKind = DTSEventFilterKind.Inclusion
    p.LoggingOptions.EventFilter = New String() {"OnPreExecute", _
       "OnPostExecute", "OnError", "OnWarning", "OnInformation"}
    p.LoggingMode = DTSLoggingMode.Enabled

    ' Add tasks and other objects to the package.

  End Sub

End Module
```

<span data-ttu-id="1eb69-147">![Значок Integration Services (маленький)](../media/dts-16.gif "Значок служб Integration Services (маленький)")  **следит за обновлениями Integration Services**</span><span class="sxs-lookup"><span data-stu-id="1eb69-147">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="1eb69-148">Чтобы загрузить новейшую документацию, статьи, образцы и видеоматериалы корпорации Майкрософт, а также лучшие решения участников сообщества, посетите страницу служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] на сайте MSDN:</span><span class="sxs-lookup"><span data-stu-id="1eb69-148">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="1eb69-149">Посетить страницу «Службы Integration Services» на сайте MSDN</span><span class="sxs-lookup"><span data-stu-id="1eb69-149">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="1eb69-150">Чтобы получать автоматические уведомления об этих обновлениях, подпишитесь на RSS-каналы, предлагаемые на этой странице.</span><span class="sxs-lookup"><span data-stu-id="1eb69-150">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="1eb69-151">См. также:</span><span class="sxs-lookup"><span data-stu-id="1eb69-151">See Also</span></span>
 [<span data-ttu-id="1eb69-152">Ведение журналов в службах Integration Services (SSIS)</span><span class="sxs-lookup"><span data-stu-id="1eb69-152">Integration Services &#40;SSIS&#41; Logging</span></span>](../performance/integration-services-ssis-logging.md)


