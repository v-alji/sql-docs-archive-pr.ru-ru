---
title: Файл конфигурации ReportingServicesService | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- traces [Reporting Services]
- Report Server Windows service, ReportingServicesService configuration file
- ReportingServicesService configuration file
ms.assetid: 40f4a401-cb61-4c42-b1ec-01acdacdacd1
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 5124631db9635211827dd3b1abbff7116101a61d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664706"
---
# <a name="reportingservicesservice-configuration-file"></a><span data-ttu-id="5f082-102">ReportingServicesService, файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="5f082-102">ReportingServicesService Configuration File</span></span>
  <span data-ttu-id="5f082-103">Файл ReportingServicesService.exe.config содержит параметры, позволяющие настраивать трассировку.</span><span class="sxs-lookup"><span data-stu-id="5f082-103">The ReportingServicesService.exe.config file includes settings that configure tracing.</span></span>  
  
## <a name="file-location"></a><span data-ttu-id="5f082-104">Расположение файла</span><span class="sxs-lookup"><span data-stu-id="5f082-104">File Location</span></span>  
 <span data-ttu-id="5f082-105">Этот файл находится в папке \Reporting Services\Report Server\Bin.</span><span class="sxs-lookup"><span data-stu-id="5f082-105">This file is located in the \Reporting Services\Report Server\Bin folder.</span></span>  
  
## <a name="editing-guidelines"></a><span data-ttu-id="5f082-106">Рекомендации по изменению</span><span class="sxs-lookup"><span data-stu-id="5f082-106">Editing Guidelines</span></span>  
 <span data-ttu-id="5f082-107">В этом файле можно переименовать файл журнала, а также увеличить (или уменьшить) уровень трассировки.</span><span class="sxs-lookup"><span data-stu-id="5f082-107">You can modify this file to rename the log file or to increase or decrease trace levels.</span></span> <span data-ttu-id="5f082-108">Другие параметры изменять не следует.</span><span class="sxs-lookup"><span data-stu-id="5f082-108">Do not modify any of the other settings.</span></span> <span data-ttu-id="5f082-109">Инструкции см. в разделе [Изменение файла конфигурации служб Reporting Services (RSreportserver.config)](modify-a-reporting-services-configuration-file-rsreportserver-config.md).</span><span class="sxs-lookup"><span data-stu-id="5f082-109">For instructions, see [Modify a Reporting Services Configuration File &#40;RSreportserver.config&#41;](modify-a-reporting-services-configuration-file-rsreportserver-config.md).</span></span> <span data-ttu-id="5f082-110">Дополнительные сведения о журналах трассировки см. в разделе [Журнал трассировки службы сервера отчетов](report-server-service-trace-log.md).</span><span class="sxs-lookup"><span data-stu-id="5f082-110">For more information about trace logs, see [Report Server Service Trace Log](report-server-service-trace-log.md).</span></span>  
  
## <a name="example-configuration"></a><span data-ttu-id="5f082-111">Пример конфигурации</span><span class="sxs-lookup"><span data-stu-id="5f082-111">Example Configuration</span></span>  
 <span data-ttu-id="5f082-112">В следующем примере показаны параметры и значения по умолчанию из файла ReportingServicesService.exe.config.</span><span class="sxs-lookup"><span data-stu-id="5f082-112">The following example shows the settings and default values found in the ReportingServicesService.exe.config file.</span></span>  
  
```  
<configSections>  
      <section name="RStrace" type="Microsoft.ReportingServices.Diagnostics.RSTraceSectionHandler,Microsoft.ReportingServices.Diagnostics" />  
</configSections>  
<system.diagnostics>  
      <switches>  
          <add name="DefaultTraceSwitch" value="3" />  
      </switches>  
</system.diagnostics>  
<RStrace>  
      <add name="FileName" value="ReportServerService_" />  
      <add name="FileSizeLimitMb" value="32" />  
      <add name="KeepFilesForDays" value="14" />  
      <add name="Prefix" value="tid, time" />  
      <add name="TraceListeners" value="debugwindow, file" />  
      <add name="TraceFileMode" value="unique" />  
      <add name="Components" value="all" />  
</RStrace>  
<runtime>  
      <alwaysFlowImpersonationPolicy enabled="true"/>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
             <dependentAssembly>  
                    <assemblyIdentity name="Microsoft.ReportingServices.Interfaces"  
                        publicKeyToken="89845dcd8080cc91"  
                        culture="neutral" />  
                    <bindingRedirect oldVersion="8.0.242.0"  
                                     newVersion="10.0.0.0"/>  
                    <bindingRedirect oldVersion="9.0.242.0"  
                                     newVersion="10.0.0.0"/>  
             </dependentAssembly>  
      </assemblyBinding>  
      <gcServer enabled="true" />  
</runtime>  
```  
  
## <a name="configuration-settings"></a><span data-ttu-id="5f082-113">Параметры конфигурации</span><span class="sxs-lookup"><span data-stu-id="5f082-113">Configuration Settings</span></span>  
 <span data-ttu-id="5f082-114">Сведения об отдельных параметрах приведены в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="5f082-114">The following table provides information about specific settings.</span></span> <span data-ttu-id="5f082-115">Параметры представлены в том порядке, в котором они следуют в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="5f082-115">Settings are presented in the order in which they appear in the configuration file.</span></span>  
  
|<span data-ttu-id="5f082-116">Параметр</span><span class="sxs-lookup"><span data-stu-id="5f082-116">Setting</span></span>|<span data-ttu-id="5f082-117">Описание</span><span class="sxs-lookup"><span data-stu-id="5f082-117">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5f082-118">**RStrace**</span><span class="sxs-lookup"><span data-stu-id="5f082-118">**RStrace**</span></span>|<span data-ttu-id="5f082-119">Задает пространства имен для ошибок и трассировки.</span><span class="sxs-lookup"><span data-stu-id="5f082-119">Specifies namespaces used for errors and tracing.</span></span>|  
|<span data-ttu-id="5f082-120">**DefaultTraceSwitch**</span><span class="sxs-lookup"><span data-stu-id="5f082-120">**DefaultTraceSwitch**</span></span>|<span data-ttu-id="5f082-121">Задает уровень данных, записываемых в журнал трассировки ReportServerService.</span><span class="sxs-lookup"><span data-stu-id="5f082-121">Specifies the level of information that is reported to the ReportServerService trace log.</span></span> <span data-ttu-id="5f082-122">Каждый уровень содержит данные, передаваемые более низкими уровнями.</span><span class="sxs-lookup"><span data-stu-id="5f082-122">Each level includes the information reported by all lower-numbered levels.</span></span> <span data-ttu-id="5f082-123">Отключать трассировку не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="5f082-123">Disabling tracing is not recommended.</span></span> <span data-ttu-id="5f082-124">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="5f082-124">Valid values include:</span></span><br /><br /> <span data-ttu-id="5f082-125">0 = Отключить трассировку</span><span class="sxs-lookup"><span data-stu-id="5f082-125">0= Disables tracing</span></span><br /><br /> <span data-ttu-id="5f082-126">1 = Исключения и перезапуски</span><span class="sxs-lookup"><span data-stu-id="5f082-126">1= Exceptions and restarts</span></span><br /><br /> <span data-ttu-id="5f082-127">2 = Исключения, перезапуски, предупреждения</span><span class="sxs-lookup"><span data-stu-id="5f082-127">2= Exceptions, restarts, warnings</span></span><br /><br /> <span data-ttu-id="5f082-128">3 = Исключения, перезапуски, предупреждения, сообщения о состоянии (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="5f082-128">3= Exceptions, restarts, warnings, status messages (default)</span></span><br /><br /> <span data-ttu-id="5f082-129">4 = Подробный режим</span><span class="sxs-lookup"><span data-stu-id="5f082-129">4= Verbose mode</span></span>|  
|<span data-ttu-id="5f082-130">**FileName**</span><span class="sxs-lookup"><span data-stu-id="5f082-130">**FileName**</span></span>|<span data-ttu-id="5f082-131">Задает первую часть названия файла журнала.</span><span class="sxs-lookup"><span data-stu-id="5f082-131">Specifies the first portion of the log file name.</span></span> <span data-ttu-id="5f082-132">Вторую часть имени определяет значение, заданное в аргументе `Prefix`.</span><span class="sxs-lookup"><span data-stu-id="5f082-132">The value specified by `Prefix` completes the rest of the name.</span></span> <span data-ttu-id="5f082-133">По умолчанию это имя ReportServerService_.</span><span class="sxs-lookup"><span data-stu-id="5f082-133">By default, the name is ReportServerService_.</span></span>|  
|<span data-ttu-id="5f082-134">**FileSizeLimitMb**</span><span class="sxs-lookup"><span data-stu-id="5f082-134">**FileSizeLimitMb**</span></span>|<span data-ttu-id="5f082-135">Задает максимальный размер журнала трассировки.</span><span class="sxs-lookup"><span data-stu-id="5f082-135">Specifies an upper limit on trace log size.</span></span> <span data-ttu-id="5f082-136">Размер измеряется в мегабайтах.</span><span class="sxs-lookup"><span data-stu-id="5f082-136">The file is measured in megabytes.</span></span> <span data-ttu-id="5f082-137">Допустимые значения: от 0 до максимально допустимого целого числа.</span><span class="sxs-lookup"><span data-stu-id="5f082-137">Valid values are 0 to a maximum integer.</span></span> <span data-ttu-id="5f082-138">Значение по умолчанию: 32.</span><span class="sxs-lookup"><span data-stu-id="5f082-138">The default value is 32.</span></span>|  
|<span data-ttu-id="5f082-139">**KeepFilesForDays**</span><span class="sxs-lookup"><span data-stu-id="5f082-139">**KeepFilesForDays**</span></span>|<span data-ttu-id="5f082-140">Определяет, через сколько дней журнал трассировки будет удален.</span><span class="sxs-lookup"><span data-stu-id="5f082-140">Specifies the number of days after which a trace log file will be deleted.</span></span> <span data-ttu-id="5f082-141">Допустимые значения: от 0 до максимально допустимого целого числа.</span><span class="sxs-lookup"><span data-stu-id="5f082-141">Valid values are 0 to a maximum integer.</span></span> <span data-ttu-id="5f082-142">Значение по умолчанию: 14.</span><span class="sxs-lookup"><span data-stu-id="5f082-142">The default value is 14.</span></span>|  
|`Prefix`|<span data-ttu-id="5f082-143">Задает формируемое значение, позволяющее отличить один экземпляр журнала от другого.</span><span class="sxs-lookup"><span data-stu-id="5f082-143">Specifies a generated value that distinguishes one log instance from another.</span></span> <span data-ttu-id="5f082-144">По умолчанию к именам файлов журнала трассировки добавляются значения отметок времени.</span><span class="sxs-lookup"><span data-stu-id="5f082-144">By default, timestamp values are appended to trace log file names.</span></span> <span data-ttu-id="5f082-145">Значение этой величины — «tid, time».</span><span class="sxs-lookup"><span data-stu-id="5f082-145">This value is set to " tid, time ".</span></span> <span data-ttu-id="5f082-146">Не изменяйте этот параметр.</span><span class="sxs-lookup"><span data-stu-id="5f082-146">Do not modify this setting.</span></span>|  
|<span data-ttu-id="5f082-147">**TraceListeners**</span><span class="sxs-lookup"><span data-stu-id="5f082-147">**TraceListeners**</span></span>|<span data-ttu-id="5f082-148">Задает, куда будет выводиться содержимое журнала трассировки.</span><span class="sxs-lookup"><span data-stu-id="5f082-148">Specifies a target for outputting trace log content.</span></span> <span data-ttu-id="5f082-149">Можно через запятую задать несколько расположений.</span><span class="sxs-lookup"><span data-stu-id="5f082-149">You can specify multiple targets using a comma to separate each one.</span></span> <span data-ttu-id="5f082-150">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="5f082-150">Valid values include:</span></span><br /><br /> <span data-ttu-id="5f082-151">DebugWindow (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="5f082-151">DebugWindow (default)</span></span><br /><br /> <span data-ttu-id="5f082-152">File (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="5f082-152">File (default)</span></span><br /><br /> <span data-ttu-id="5f082-153">StdOut</span><span class="sxs-lookup"><span data-stu-id="5f082-153">StdOut</span></span>|  
|<span data-ttu-id="5f082-154">**TraceFileMode**</span><span class="sxs-lookup"><span data-stu-id="5f082-154">**TraceFileMode**</span></span>|<span data-ttu-id="5f082-155">Определяет, содержат ли журналы трассировки данные за 24-часовой период.</span><span class="sxs-lookup"><span data-stu-id="5f082-155">Specifies whether trace logs contain data for a 24-hour period.</span></span> <span data-ttu-id="5f082-156">Необходимо, чтобы каждому компоненту за каждый день соответствовал один уникальный журнал трассировки.</span><span class="sxs-lookup"><span data-stu-id="5f082-156">You should have one unique trace log for each component on each day.</span></span> <span data-ttu-id="5f082-157">Значение этой величины — Unique (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="5f082-157">This value is set to "Unique (default)".</span></span> <span data-ttu-id="5f082-158">Не изменяйте это значение.</span><span class="sxs-lookup"><span data-stu-id="5f082-158">Do not modify this value.</span></span>|  
|<span data-ttu-id="5f082-159">**Components**</span><span class="sxs-lookup"><span data-stu-id="5f082-159">**Components**</span></span>|<span data-ttu-id="5f082-160">Задает компоненты, для которых создаются журналы трассировки.</span><span class="sxs-lookup"><span data-stu-id="5f082-160">Specifies the components for which trace logs are created.</span></span> <span data-ttu-id="5f082-161">Значение по умолчанию — `all`.</span><span class="sxs-lookup"><span data-stu-id="5f082-161">The default value is `all`.</span></span> <span data-ttu-id="5f082-162">Другими допустимыми значениями этого параметра являются названия внутренних компонентов.</span><span class="sxs-lookup"><span data-stu-id="5f082-162">Other valid values for this setting include the names of internal components.</span></span> <span data-ttu-id="5f082-163">Не изменяйте это значение.</span><span class="sxs-lookup"><span data-stu-id="5f082-163">Do not modify this value.</span></span>|  
|<span data-ttu-id="5f082-164">**Этапе**</span><span class="sxs-lookup"><span data-stu-id="5f082-164">**Runtime**</span></span>|<span data-ttu-id="5f082-165">Задает параметры конфигурации, обеспечивающие обратную совместимость с предыдущей версией.</span><span class="sxs-lookup"><span data-stu-id="5f082-165">Specifies configuration settings that support backward compatibility with the previous version.</span></span> <span data-ttu-id="5f082-166">Параметры среды выполнения используются для перенаправления запросов, обращающихся к предыдущей версии пространства имен Microsoft.ReportingServices.Interfaces, в пространство имен новой версии.</span><span class="sxs-lookup"><span data-stu-id="5f082-166">Runtime settings are used to redirect requests that target the previous version of Microsoft.ReportingServices.Interfaces to the new version.</span></span><br /><br /> <span data-ttu-id="5f082-167">Все параметры конфигурации этого раздела описаны в документации по платформе [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5f082-167">All of the configuration settings in this section are described in the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] product documentation.</span></span> <span data-ttu-id="5f082-168">Дополнительные сведения можно получить, выполнив поиск по строке «Runtime Schema Settings» на веб-сайте MSDN или в документации по платформе [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5f082-168">For more information, search for "Runtime Schema Settings" on the MSDN Web site or in the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] documentation.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5f082-169">См. также:</span><span class="sxs-lookup"><span data-stu-id="5f082-169">See Also</span></span>  
 <span data-ttu-id="5f082-170">[Файлы конфигурации служб Reporting Services](reporting-services-configuration-files.md) </span><span class="sxs-lookup"><span data-stu-id="5f082-170">[Reporting Services Configuration Files](reporting-services-configuration-files.md) </span></span>  
 [<span data-ttu-id="5f082-171">Журнал трассировки службы сервера отчетов</span><span class="sxs-lookup"><span data-stu-id="5f082-171">Report Server Service Trace Log</span></span>](report-server-service-trace-log.md)  
  
  
