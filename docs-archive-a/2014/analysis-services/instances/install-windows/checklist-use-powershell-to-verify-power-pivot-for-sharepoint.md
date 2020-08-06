---
title: 'Контрольный список: использование PowerShell для проверки PowerPivot для SharePoint | Документация Майкрософт'
ms.custom: ''
ms.date: 07/20/2020
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 73a13f05-3450-411f-95f9-4b6167cc7607
author: minewiskan
ms.author: owend
ms.openlocfilehash: 001b3fae82851b9ec08b0383bb3db9e6d011ae32
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87729958"
---
# <a name="checklist-use-powershell-to-verify-powerpivot-for-sharepoint"></a><span data-ttu-id="2cca0-102">Контрольный список: использование PowerShell для проверки PowerPivot для SharePoint</span><span class="sxs-lookup"><span data-stu-id="2cca0-102">CheckList: Use PowerShell to Verify PowerPivot for SharePoint</span></span>
  <span data-ttu-id="2cca0-103">Ни одна из операций установки или восстановления [!INCLUDE[ssGeminiShort](../../../includes/ssgeminishort-md.md)] не завершена без прохождения проверочного теста, который подтверждает работоспособность служб и данных.</span><span class="sxs-lookup"><span data-stu-id="2cca0-103">No [!INCLUDE[ssGeminiShort](../../../includes/ssgeminishort-md.md)] installation or recovery operation is complete without a solid verification test pass that confirms your services and data are operational.</span></span> <span data-ttu-id="2cca0-104">В этой статье рассказывается о том, как выполнить эти шаги с помощью Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2cca0-104">In this article, we show you how to perform these steps using Windows PowerShell.</span></span> <span data-ttu-id="2cca0-105">Каждому шагу посвящен отдельный подраздел с тем, чтобы можно было перейти непосредственно к конкретным задачам.</span><span class="sxs-lookup"><span data-stu-id="2cca0-105">We put each step into its own section so that you can go straight to specific tasks.</span></span> <span data-ttu-id="2cca0-106">Например, выполните скрипт, приведенный в подразделе [Базы данных](#bkmk_databases) этого раздела для проверки имени приложения службы и баз данных содержимого, если необходимо запланировать их для обслуживания или резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="2cca0-106">For example, run the script in the [Databases](#bkmk_databases) section of this topic to verify the name of the service application and content databases if you want to schedule them for maintenance or backup.</span></span>

|||
|-|-|
|<span data-ttu-id="2cca0-107">![Содержимое, связанное с PowerShell](../../../reporting-services/media/rs-powershellicon.jpg "Содержимое, связанное с PowerShell")</span><span class="sxs-lookup"><span data-stu-id="2cca0-107">![PowerShell related content](../../../reporting-services/media/rs-powershellicon.jpg "PowerShell related content")</span></span>|<span data-ttu-id="2cca0-108">Полный скрипт PowerShell приведен в конце раздела.</span><span class="sxs-lookup"><span data-stu-id="2cca0-108">A full PowerShell script is included at the bottom of the topic.</span></span> <span data-ttu-id="2cca0-109">Используйте полный скрипт в качестве отправной точки создания пользовательского скрипта для аудита полного развертывания [!INCLUDE[ssGeminiShort](../../../includes/ssgeminishort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2cca0-109">Use the full script as a starting point to build a custom script for auditing your full [!INCLUDE[ssGeminiShort](../../../includes/ssgeminishort-md.md)] deployment.</span></span>|

||
|-|
|<span data-ttu-id="2cca0-110">**[!INCLUDE[applies](../../../includes/applies-md.md)]** SharePoint 2013 &#124; SharePoint 2010</span><span class="sxs-lookup"><span data-stu-id="2cca0-110">**[!INCLUDE[applies](../../../includes/applies-md.md)]**  SharePoint 2013 &#124; SharePoint 2010</span></span>|

 <span data-ttu-id="2cca0-111">**В этой статье**. Обозначенные буквами элементы в содержании соответствуют областям на схеме.</span><span class="sxs-lookup"><span data-stu-id="2cca0-111">**In this topic**: The lettered items in the following the TOC correspond to areas of the diagram.</span></span> <span data-ttu-id="2cca0-112">На диаграмме показано:</span><span class="sxs-lookup"><span data-stu-id="2cca0-112">The diagram illustrates the</span></span>

|||
|-|-|
|[<span data-ttu-id="2cca0-113">Подготовка среды PowerShell</span><span class="sxs-lookup"><span data-stu-id="2cca0-113">Prepare your PowerShell environment</span></span>](#bkmk_prerequisites)<br /><br /> [<span data-ttu-id="2cca0-114">Симптомы и рекомендуемые действия</span><span class="sxs-lookup"><span data-stu-id="2cca0-114">Symptoms and Recommended Actions</span></span>](#bkmk_symptoms)<br /><br /> <span data-ttu-id="2cca0-115">**(A)** [Службы Analysis Services для Windows](#bkmk_windows_service)</span><span class="sxs-lookup"><span data-stu-id="2cca0-115">**(A)** [Analysis Services Windows Service](#bkmk_windows_service)</span></span><br /><br /> <span data-ttu-id="2cca0-116">**(Б)** [PowerPivotSystemService и PowerPivotEngineService](#bkmk_engine_and_system_service)</span><span class="sxs-lookup"><span data-stu-id="2cca0-116">**(B)** [PowerPivotSystemService and PowerPivotEngineService](#bkmk_engine_and_system_service)</span></span><br /><br /> <span data-ttu-id="2cca0-117">**(В)** [Приложения службы PowerPivot и прокси-серверы](#bkmk_powerpivot_service_application)</span><span class="sxs-lookup"><span data-stu-id="2cca0-117">**(C)** [PowerPivot Service Application(s) and proxies](#bkmk_powerpivot_service_application)</span></span><br /><br /> <span data-ttu-id="2cca0-118">**(D)** [Базы данных](#bkmk_databases)</span><span class="sxs-lookup"><span data-stu-id="2cca0-118">**(D)** [Databases](#bkmk_databases)</span></span><br /><br /> [<span data-ttu-id="2cca0-119">Компоненты SharePoint</span><span class="sxs-lookup"><span data-stu-id="2cca0-119">SharePoint Features</span></span>](#bkmk_features)<br /><br /> [<span data-ttu-id="2cca0-120">Задания таймера</span><span class="sxs-lookup"><span data-stu-id="2cca0-120">Timer Jobs</span></span>](#bkmk_timer_jobs)<br /><br /> [<span data-ttu-id="2cca0-121">Правила определения исправности</span><span class="sxs-lookup"><span data-stu-id="2cca0-121">Health Rules</span></span>](#bkmk_health_rules)<br /><br /> <span data-ttu-id="2cca0-122">**(E)** [Журналы Windows и ULS](#bkmk_logs)</span><span class="sxs-lookup"><span data-stu-id="2cca0-122">**(E)** [Windows and ULS Logs](#bkmk_logs)</span></span><br /><br /> [<span data-ttu-id="2cca0-123">Поставщик MSOLAP</span><span class="sxs-lookup"><span data-stu-id="2cca0-123">MSOLAP Provider</span></span>](#bkmk_msolap)<br /><br /> [<span data-ttu-id="2cca0-124">Клиентская библиотека ADOMD.Net</span><span class="sxs-lookup"><span data-stu-id="2cca0-124">ADOMD.Net client Library</span></span>](#bkmk_adomd)<br /><br /> [<span data-ttu-id="2cca0-125">Правила сбора данных об исправности</span><span class="sxs-lookup"><span data-stu-id="2cca0-125">Health Data Collection Rules</span></span>](#bkmk_health_collection)<br /><br /> [<span data-ttu-id="2cca0-126">Решения</span><span class="sxs-lookup"><span data-stu-id="2cca0-126">Solutions</span></span>](#bkmk_solutions)<br /><br /> [<span data-ttu-id="2cca0-127">Действия по проверке вручную</span><span class="sxs-lookup"><span data-stu-id="2cca0-127">Manual Verification Steps</span></span>](#bkmk_manual)<br /><br /> [<span data-ttu-id="2cca0-128">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="2cca0-128">More Resources</span></span>](#bkmk_more_resources)<br /><br /> [<span data-ttu-id="2cca0-129">Полный скрипт PowerShell</span><span class="sxs-lookup"><span data-stu-id="2cca0-129">Full PowerShell Script</span></span>](#bkmk_full_script)|<span data-ttu-id="2cca0-130">![проверка powerpivot с помощью powershell](../../../sql-server/install/media/ssas-powershell-component-verification.png "проверка powerpivot с помощью powershell")</span><span class="sxs-lookup"><span data-stu-id="2cca0-130">![powershell verification of powerpivot](../../../sql-server/install/media/ssas-powershell-component-verification.png "powershell verification of powerpivot")</span></span>|

##  <a name="prepare-your-powershell-environment"></a><a name="bkmk_prerequisites"></a> <span data-ttu-id="2cca0-131">Подготовка среды PowerShell</span><span class="sxs-lookup"><span data-stu-id="2cca0-131">Prepare your PowerShell environment</span></span>
 <span data-ttu-id="2cca0-132">В этом разделе описаны действия по подготовке среды PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2cca0-132">The steps in this section prepare your PowerShell environment.</span></span> <span data-ttu-id="2cca0-133">В зависимости от текущей конфигурации среды создания скриптов некоторые действия могут не потребоваться.</span><span class="sxs-lookup"><span data-stu-id="2cca0-133">The steps may not be required, depending on how your scripting environment is currently configured.</span></span>

 <span data-ttu-id="2cca0-134">**Разрешения PowerShell**</span><span class="sxs-lookup"><span data-stu-id="2cca0-134">**PowerShell Permissions**</span></span>

 <span data-ttu-id="2cca0-135">Откройте окно Powershell или PowerShell ISE (интегрированная среда скриптов) с **правами администратора**.</span><span class="sxs-lookup"><span data-stu-id="2cca0-135">Open a Powershell window or the PowerShell ISE (Integrated Scripting Environment) with **administrative privileges**.</span></span> <span data-ttu-id="2cca0-136">Если во время выполнения команд у вас не будет прав администратора, то появится сообщение об ошибке следующего вида:</span><span class="sxs-lookup"><span data-stu-id="2cca0-136">If you do not have administrative privileges when you run commands, you will see an error message similar to the following:</span></span>

 <span data-ttu-id="2cca0-137">Get-SPLogEvent: для выполнения этого командлета необходимо иметь **права администратора** на компьютере.</span><span class="sxs-lookup"><span data-stu-id="2cca0-137">Get-SPLogEvent : You need to have Machine **administrator privileges** to run this cmdlet.</span></span>

 <span data-ttu-id="2cca0-138">**SharePoint и модуль [!INCLUDE[ssGeminiShort](../../../includes/ssgeminishort-md.md)]**</span><span class="sxs-lookup"><span data-stu-id="2cca0-138">**SharePoint and [!INCLUDE[ssGeminiShort](../../../includes/ssgeminishort-md.md)]** Module</span></span>

 <span data-ttu-id="2cca0-139">Если при запуске связанных с SharePoint командлетов отображается сообщение об ошибке, похожее на следующее, выполните команду Add-PSSnapin:</span><span class="sxs-lookup"><span data-stu-id="2cca0-139">If you see an error message similar to the following when you run SharePoint related cmdlets, run the Add-PSSnapin command:</span></span>

 <span data-ttu-id="2cca0-140">Термин "Get-PowerPivotSystemService" **не распознан как имя командлета**, функции, файла скрипта или действующей программы.</span><span class="sxs-lookup"><span data-stu-id="2cca0-140">The term 'Get-PowerPivotSystemService' **is not recognized as the name of a cmdlet**, function, script file, or operable program.</span></span> <span data-ttu-id="2cca0-141">Проверьте правильность написания имени, а если включен путь, то проверьте правильность пути и повторите попытку.</span><span class="sxs-lookup"><span data-stu-id="2cca0-141">Check the spelling of the name, or if a path was included, verify that the path is correct and try again.</span></span>

```
Add-PSSnapin Microsoft.Sharepoint.Powershell -EA 0
```

 <span data-ttu-id="2cca0-142">**Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="2cca0-142">**Windows PowerShell**</span></span>

 <span data-ttu-id="2cca0-143">Дополнительные сведения о PowerShell ISE см. в разделе [Общие сведения о Windows PowerShell ISE](https://technet.microsoft.com/library/dd315244.aspx) и [Использование Windows PowerShell для администрирования SharePoint 2013](https://technet.microsoft.com/library/ee806878\(v=office.15\).aspx).</span><span class="sxs-lookup"><span data-stu-id="2cca0-143">For more information on the PowerShell ISE, see [Introducing the Windows PowerShell ISE](https://technet.microsoft.com/library/dd315244.aspx) and [Use Windows PowerShell to administer SharePoint 2013](https://technet.microsoft.com/library/ee806878\(v=office.15\).aspx).</span></span>

|||
|-|-|
|<span data-ttu-id="2cca0-144">![набор приложений общего характера powerpivot в sharepoint](../../../sql-server/install/media/ssas-powerpivot-logo.png "набор приложений общего характера powerpivot в sharepoint")</span><span class="sxs-lookup"><span data-stu-id="2cca0-144">![powerpivot in sharepoint general application set](../../../sql-server/install/media/ssas-powerpivot-logo.png "powerpivot in sharepoint general application set")</span></span>|<span data-ttu-id="2cca0-145">При желании можно проверить большинство компонентов в центре администрирования с помощью панели управления [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2cca0-145">You can optionally verify a majority of the components in Central Administration, using the [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] management dashboard.</span></span> <span data-ttu-id="2cca0-146">Чтобы открыть панель мониторинга в центре администрирования, выберите **Общие параметры приложения**, а затем щелкните **Панель мониторинга управления** в **PowerPivot**.</span><span class="sxs-lookup"><span data-stu-id="2cca0-146">To open the dashboard in Central Administration, click **General Application Settings**, and then click **Management Dashboard** in the **PowerPivot**.</span></span> <span data-ttu-id="2cca0-147">Дополнительные сведения о панели мониторинга см. в разделе [PowerPivot Management Dashboard and Usage Data](../../power-pivot-sharepoint/power-pivot-management-dashboard-and-usage-data.md).</span><span class="sxs-lookup"><span data-stu-id="2cca0-147">For more information on the dashboard, see [PowerPivot Management Dashboard and Usage Data](../../power-pivot-sharepoint/power-pivot-management-dashboard-and-usage-data.md).</span></span>|

##  <a name="symptoms-and-recommended-actions"></a><a name="bkmk_symptoms"></a><span data-ttu-id="2cca0-148">Симптомы и рекомендуемые действия</span><span class="sxs-lookup"><span data-stu-id="2cca0-148">Symptoms and Recommended Actions</span></span>
 <span data-ttu-id="2cca0-149">В следующей таблице приведен список симптомов или проблем и предложенный подраздел, в котором приведены сведения о том, как устранить данную проблему.</span><span class="sxs-lookup"><span data-stu-id="2cca0-149">The following table is a list of symptoms or issues and the suggested section of this topic to consult to help you resolve the issue.</span></span>

|<span data-ttu-id="2cca0-150">Симптом</span><span class="sxs-lookup"><span data-stu-id="2cca0-150">Symptom</span></span>|<span data-ttu-id="2cca0-151">См. в разделе</span><span class="sxs-lookup"><span data-stu-id="2cca0-151">See section</span></span>|
|-------------|-----------------|
|<span data-ttu-id="2cca0-152">Обновление данных не выполняется</span><span class="sxs-lookup"><span data-stu-id="2cca0-152">Data refresh is not running</span></span>|<span data-ttu-id="2cca0-153">См. раздел [Timer Jobs](#bkmk_timer_jobs) и проверьте, что **Оперативное задание таймера обновления данных PowerPivot** находится в сети.</span><span class="sxs-lookup"><span data-stu-id="2cca0-153">See the section [Timer Jobs](#bkmk_timer_jobs) and verify the **Online PowerPivot Data Refresh Timer Job** is online.</span></span>|
|<span data-ttu-id="2cca0-154">На панели мониторинга управления отображаются старые данные</span><span class="sxs-lookup"><span data-stu-id="2cca0-154">Management dashboard data is old</span></span>|<span data-ttu-id="2cca0-155">См. раздел [Задания таймера](#bkmk_timer_jobs) и проверьте, что **панель управления заданием таймера обработки** включена.</span><span class="sxs-lookup"><span data-stu-id="2cca0-155">See the section [Timer Jobs](#bkmk_timer_jobs) and verify the **Management Dashboard Processing Timer Job** is online.</span></span>|
|<span data-ttu-id="2cca0-156">Некоторые части панели мониторинга управления</span><span class="sxs-lookup"><span data-stu-id="2cca0-156">Some portions of the Management Dashboard</span></span>|<span data-ttu-id="2cca0-157">При установке PowerPivot для SharePoint в ферму с такой топологией (центр администрирования без службы Excel Services или PowerPivot для SharePoint) необходимо загрузить и установить клиентскую библиотеку Microsoft ADOMD.NET, если требуется иметь полный доступ к встроенным на панели управления PowerPivot отчетам.</span><span class="sxs-lookup"><span data-stu-id="2cca0-157">If you install PowerPivot for SharePoint into a farm that has the topology of Central Administration, without Excel Services or PowerPivot for SharePoint, you must download and install the Microsoft ADOMD.NET client library if you want full access to the built-in reports in the PowerPivot management dashboard.</span></span> <span data-ttu-id="2cca0-158">Некоторые отчеты с панели мониторинга используют ADOMD.NET для доступа к внутренним данным, предоставляющим сведения об обработке запросов PowerPivot и исправности сервера в ферме.</span><span class="sxs-lookup"><span data-stu-id="2cca0-158">Some reports in the dashboard use ADOMD.NET to access internal data that provides reporting data on PowerPivot query processing and server health in the farm.</span></span> <span data-ttu-id="2cca0-159">Дополнительные сведения см. в разделе [ADOMD.Net client Library](#bkmk_adomd) и в статье [Установка ADOMD.NET на веб-серверах, обслуживающих клиентские запросы, под управлением центра администрирования](../../../sql-server/install/install-adomd-net-on-web-front-end-servers-running-central-administration.md).</span><span class="sxs-lookup"><span data-stu-id="2cca0-159">See the section [ADOMD.Net client Library](#bkmk_adomd) and the topic [Install ADOMD.NET on Web Front-End Servers Running Central Administration](../../../sql-server/install/install-adomd-net-on-web-front-end-servers-running-central-administration.md).</span></span>|
|\<future content>||

##  <a name="analysis-services-windows-service"></a><a name="bkmk_windows_service"></a> <span data-ttu-id="2cca0-160">Службы Analysis Services для Windows</span><span class="sxs-lookup"><span data-stu-id="2cca0-160">Analysis Services Windows Service</span></span>
 <span data-ttu-id="2cca0-161">Приведенный в этом разделе скрипт проверяет экземпляр служб [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] в режиме интеграции с SharePoint.</span><span class="sxs-lookup"><span data-stu-id="2cca0-161">The script in this section verifies the instance of [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] in SharePoint mode.</span></span> <span data-ttu-id="2cca0-162">Убедитесь, что служба **запущена**.</span><span class="sxs-lookup"><span data-stu-id="2cca0-162">Verify the service is **running**.</span></span>

```powershell
Get-Service | Select name, displayname, status | Where {$_.Name -eq "msolap`$powerpivot"} | Format-Table -Property * -AutoSize | Out-Default
```

```Output
Name              DisplayName                                Status
----              -----------                                ------
MSOLAP$POWERPIVOT SQL Server Analysis Services (POWERPIVOT) Running
```

##  <a name="powerpivotsystemservice-and-powerpivotengineservice"></a><a name="bkmk_engine_and_system_service"></a><span data-ttu-id="2cca0-163">PowerPivotSystemService и PowerPivotEngineService</span><span class="sxs-lookup"><span data-stu-id="2cca0-163">PowerPivotSystemService and PowerPivotEngineService</span></span>
 <span data-ttu-id="2cca0-164">Приведенные в этом разделе скрипты проверяют системные службы [!INCLUDE[ssGeminiShort](../../../includes/ssgeminishort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2cca0-164">The scripts in this section verify the [!INCLUDE[ssGeminiShort](../../../includes/ssgeminishort-md.md)] system services.</span></span> <span data-ttu-id="2cca0-165">Имеется одна системная служба для развертывания SharePoint 2013 и две для развертывания SharePoint 2010.</span><span class="sxs-lookup"><span data-stu-id="2cca0-165">There is one system service for a SharePoint 2013 deployment and two services for a SharePoint 2010 deployment.</span></span>

 <span data-ttu-id="2cca0-166">**PowerPivotSystemService**</span><span class="sxs-lookup"><span data-stu-id="2cca0-166">**PowerPivotSystemService**</span></span>

 <span data-ttu-id="2cca0-167">Проверьте состояние "в **сети**".</span><span class="sxs-lookup"><span data-stu-id="2cca0-167">Verify the Status is **Online**.</span></span>

```powershell
Get-PowerPivotSystemService | Select typename, status, applications, farm | Format-Table -Property * -AutoSize | Out-Default
```

```Output
TypeName                                  Status Applications                             Farm
--------                                  ------ ------------                             ----
SQL Server PowerPivot Service Application Online {Default PowerPivot Service Application} SPFarm Name=SharePoint_Config_77d8ab0744a34e8aa27c806a2b8c760c
```

 <span data-ttu-id="2cca0-168">**PowerPivotEngineService**</span><span class="sxs-lookup"><span data-stu-id="2cca0-168">**PowerPivotEngineService**</span></span>

> [!NOTE]
>  <span data-ttu-id="2cca0-169">**Пропустите этот скрипт, если** используется SharePoint 2013.</span><span class="sxs-lookup"><span data-stu-id="2cca0-169">**Skip this script if** you are using SharePoint 2013.</span></span> <span data-ttu-id="2cca0-170">PowerPivotEngineService не входит в развертывание SharePoint 2013.</span><span class="sxs-lookup"><span data-stu-id="2cca0-170">The PowerPivotEngineService is not part of a SharePoint 2013 deployment.</span></span> <span data-ttu-id="2cca0-171">При выполнении командлета Get-PowerPivot службы**Engine**Service в SharePoint 2013 откроется сообщение об ошибке примерно следующего содержания.</span><span class="sxs-lookup"><span data-stu-id="2cca0-171">If you run the Get-PowerPivot**Engine**Service cmdlet on SharePoint 2013, you will see an error message similar to the following.</span></span> <span data-ttu-id="2cca0-172">Это сообщение об ошибке возвращается, даже если запущена команда PSSnapin, описанная в разделе предварительных требований этого раздела.</span><span class="sxs-lookup"><span data-stu-id="2cca0-172">This error message is returned even if you have run the Add-PSSnapin command described in the prerequisites section of this topic.</span></span>
> 
>  <span data-ttu-id="2cca0-173">Термин «Get-PowerPivotEngineService» не распознан в качестве имени командлета</span><span class="sxs-lookup"><span data-stu-id="2cca0-173">The term 'Get-PowerPivotEngineService' is not recognized as the name of a cmdlet</span></span>

 <span data-ttu-id="2cca0-174">В развертывании SharePoint 2010 состояние должно быть **В сети**.</span><span class="sxs-lookup"><span data-stu-id="2cca0-174">In a SharePoint 2010 deployment, verify the status is **Online**.</span></span>

```powershell
Get-PowerPivotEngineService | Select typename, status, name, instances, farm | Format-Table -Property * -AutoSize | Out-Default
```

```Output
TypeName  : SQL Server Analysis Services
Status    : Online
Name      : MSOLAP$POWERPIVOT
Instances : {POWERPIVOT}
Farm      : SPFarm Name=SharePoint_Config
```

##  <a name="powerpivot-service-applications-and-proxies"></a><a name="bkmk_powerpivot_service_application"></a><span data-ttu-id="2cca0-175">Приложения службы PowerPivot и прокси-серверы</span><span class="sxs-lookup"><span data-stu-id="2cca0-175">PowerPivot Service Application(s) and proxies</span></span>
 <span data-ttu-id="2cca0-176">Состояние должно быть **В сети**.</span><span class="sxs-lookup"><span data-stu-id="2cca0-176">Verify the status is **Online**.</span></span> <span data-ttu-id="2cca0-177">Приложение служб Excel не использует базы данных приложения службы, поэтому командлет не возвращает имя базы данных.</span><span class="sxs-lookup"><span data-stu-id="2cca0-177">The Excel Services Application does not use a service application database and therefore the cmdlet does not return a database name.</span></span> <span data-ttu-id="2cca0-178">Запишите базу данных, которая используется приложением службы [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] , чтобы можно было удостовериться в том, что она находится в сети в подразделе базы данных далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="2cca0-178">Note the database used by the [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] service application so you can verify the database is online in the database section later in this topic.</span></span>

 <span data-ttu-id="2cca0-179">**Приложение службы PowerPivot и Excel**</span><span class="sxs-lookup"><span data-stu-id="2cca0-179">**PowerPivot and Excel Service Application(s)**</span></span>

 <span data-ttu-id="2cca0-180">В развертывании SharePoint 2010 состояние должно быть **В сети**.</span><span class="sxs-lookup"><span data-stu-id="2cca0-180">For a SharePoint 2010 deployment, verify the status is **Online**.</span></span>

```powershell
Get-PowerPivotServiceApplication | Select typename,name, status, unattendedaccount, applicationpool, farm, database
Get-SPExcelServiceApplication | Select typename, DisplayName, status
```

```Output
TypeName          : PowerPivot Service Application
Name              : PowerPivotServiceApplication1
Status            : Online
UnattendedAccount : PowerPivotUnattendedAccount
ApplicationPool   : SPIisWebServiceApplicationPool Name=sqlbi_serviceapp
Farm              : SPFarm Name=SharePoint_Config
Database          : GeminiServiceDatabase Name=PowerPivotServiceApplication1_19648f3f2c944e27acdc6c20aab8487a

TypeName    : Excel Services Application Web Service Application
DisplayName : Excel Services Application
Status      : Online
```

 <span data-ttu-id="2cca0-181">**Пул приложений службы**</span><span class="sxs-lookup"><span data-stu-id="2cca0-181">**Service Application Pool**</span></span>

> [!NOTE]
>  <span data-ttu-id="2cca0-182">Следующий образец кода сначала возвращает свойство applicationpool приложения службы [!INCLUDE[ssGeminiShort](../../../includes/ssgeminishort-md.md)] по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="2cca0-182">The following code sample first returns the applicationpool property of the default [!INCLUDE[ssGeminiShort](../../../includes/ssgeminishort-md.md)] service application.</span></span> <span data-ttu-id="2cca0-183">Имя анализируется из строки и используется для получения сведений о состоянии объекта пула приложений.</span><span class="sxs-lookup"><span data-stu-id="2cca0-183">The name is parsed from the string and used to get the status of the application pool object.</span></span>
> 
>  <span data-ttu-id="2cca0-184">Проверьте состояние "в **сети**".</span><span class="sxs-lookup"><span data-stu-id="2cca0-184">Verify the Status is **Online**.</span></span> <span data-ttu-id="2cca0-185">Если состояние находится не в сети или отображается сообщение "ошибка HTTP" при просмотре [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] сайта, убедитесь, что учетные данные удостоверения в пулах приложений IIS все еще верны.</span><span class="sxs-lookup"><span data-stu-id="2cca0-185">If the status is not Online or you see "http error" when you browse the [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] site, verify the identity credentials in the IIS application pools are still correct.</span></span> <span data-ttu-id="2cca0-186">Имя пула приложений IIS — это значение свойства идентификатора, возвращаемого командой Get-SPServiceApplicationPool.</span><span class="sxs-lookup"><span data-stu-id="2cca0-186">The IIS pool name will is the value of the ID property returned by the Get-SPServiceApplicationPool command.</span></span>

```powershell
$poolname = [string](Get-PowerPivotServiceApplication | Select -Property applicationpool)
$position = $poolname.lastindexof("=")
$poolname = $poolname.substring($position+1)
$poolname = $poolname.substring(0,$poolname.length-1)

Get-SPServiceApplicationPool | Select name, status, processaccountname, id | Where {$_.Name -eq $poolname} | Format-Table -Property * -AutoSize | Out-Default
```

```Output
Name                           Status ProcessAccountName Id
----                           ------ ------------------ ------- 
SharePoint Web Services System Online DOMAIN\account     89b50ec3-49e3-4de7-881a-2cec4b8b73ea
```

 ![Примечание](../../../reporting-services/media/rs-fyinote.png "Примечание.") . Пул приложений также можно проверить на странице центра администрирования **Управление приложениями служб**. <span data-ttu-id="2cca0-188">Щелкните имя приложения службы, затем нажмите кнопку **Свойства** на ленте.</span><span class="sxs-lookup"><span data-stu-id="2cca0-188">Click the name of the service application and then click **properties** in the ribbon.</span></span>

 <span data-ttu-id="2cca0-189">**Прокси-серверы приложения службы PowerPivot и Excel**</span><span class="sxs-lookup"><span data-stu-id="2cca0-189">**PowerPivot and Excel Service Application proxies**</span></span>

 <span data-ttu-id="2cca0-190">Проверьте состояние "в **сети**".</span><span class="sxs-lookup"><span data-stu-id="2cca0-190">Verify the Status is **Online**.</span></span>

```powershell
Get-SPServiceApplicationProxy | Select typename, status, unattendedaccount, displayname | Where {$_.TypeName -Like "*powerpivot*" -Or $_.TypeName -Like "*excel services*"} | Format-Table -Property * -AutoSize | Out-Default
```

```Output
TypeName                                                 Status UnattendedAccount           DisplayName
--------                                                 ------ -----------------           -----------
PowerPivot Service Application Proxy                     Online PowerPivotUnattendedAccount PowerPivotServiceApplication1
Excel Services Application Web Service Application Proxy Online                             Excel Services Application
```

##  <a name="databases"></a><a name="bkmk_databases"></a> <span data-ttu-id="2cca0-191">Базы данных</span><span class="sxs-lookup"><span data-stu-id="2cca0-191">Databases</span></span>
 <span data-ttu-id="2cca0-192">Следующий скрипт возвращает состояние баз данных приложений служб и все базы данных содержимого.</span><span class="sxs-lookup"><span data-stu-id="2cca0-192">The following script returns the status of the service application databases and all content databases.</span></span> <span data-ttu-id="2cca0-193">Состояние должно быть **В сети**.</span><span class="sxs-lookup"><span data-stu-id="2cca0-193">Verify the status is **Online**.</span></span>

```powershell
Get-SPDatabase | Select name, status, server, typename | Where {$_.TypeName -eq "content database" -Or $_.TypeName -Like "*Gemini*"} | Format-Table -Property * -AutoSize | Out-Default
```

```Output
Name                                                                       Status Server                  TypeName 
----                                                                       ------ ------                  -------- 
DefaultPowerPivotServiceApplicationDB-38422181-2b68-4ab2-b2bb-9c00c39e5a5e Online SPServer Name=TESTSERVER Microsoft.AnalysisServices.SPAddin.GeminiServiceDatabase
DefaultWebApplicationDB-f0db1a8e-4c22-408c-b9b9-153bd74b0312               Online TESTSERVER\POWERPIVOT    Content Database 
SharePoint_Admin_3cadf0b098bf49e0bb15abd487f5c684                          Online TESTSERVER\POWERPIVOT    Content Database
```

##  <a name="sharepoint-features"></a><a name="bkmk_features"></a><span data-ttu-id="2cca0-194">Функции SharePoint</span><span class="sxs-lookup"><span data-stu-id="2cca0-194">SharePoint Features</span></span>
 <span data-ttu-id="2cca0-195">Убедитесь в том, что компоненты сайта, сети и фермы находятся в сети.</span><span class="sxs-lookup"><span data-stu-id="2cca0-195">Verify the site, web, and farm features are online.</span></span>

```powershell
Get-SPFeature | Select displayname, status, scope, farm | Where {$_.displayName -Like "*powerpivot*"} | Format-Table -Property * -AutoSize | Out-Default
```

```Output
DisplayName     Status Scope Farm                         
-----------     ------ ----- ----                         
PowerPivotSite  Online  Site SPFarm Name=SharePoint_Config
PowerPivotAdmin Online   Web SPFarm Name=SharePoint_Config
PowerPivot      Online  Farm SPFarm Name=SharePoint_Config
```

##  <a name="timer-jobs"></a><a name="bkmk_timer_jobs"></a><span data-ttu-id="2cca0-196">Задания таймера</span><span class="sxs-lookup"><span data-stu-id="2cca0-196">Timer Jobs</span></span>
 <span data-ttu-id="2cca0-197">Убедитесь в том, что задания таймера находятся **В сети**.</span><span class="sxs-lookup"><span data-stu-id="2cca0-197">Verify the Time Jobs are **Online**.</span></span> <span data-ttu-id="2cca0-198">Служба [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] EngineService не установлена на сервере SharePoint 2013, поэтому скрипт не сформирует список заданий таймера EngineService в развертывании SharePoint 2013.</span><span class="sxs-lookup"><span data-stu-id="2cca0-198">The [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] EngineService is not installed on SharePoint 2013, therefore the script will not list EngineService timer jobs in a SharePoint 2013 deployment.</span></span>

```powershell
Get-SPTimerJob | Where {$_.service -Like "*power*" -Or $_.service -Like "*mid*"} | Select status, displayname, LastRunTime, service | Format-Table -Property * -AutoSize | Out-Default
```

```Output
      Status DisplayName                                                                          LastRunTime          Service                             
------ -----------                                                                          -----------          -------                             
Online Health Analysis Job (Daily, SQL Server Analysis Services, All Servers)               4/9/2014 12:00:01 AM EngineService Name=MSOLAP$POWERPIVOT
Online Health Analysis Job (Hourly, SQL Server Analysis Services, All Servers)              4/9/2014 1:00:01 PM  EngineService Name=MSOLAP$POWERPIVOT
Online Health Analysis Job (Weekly, SQL Server Analysis Services, All Servers)              4/6/2014 12:00:10 AM EngineService Name=MSOLAP$POWERPIVOT
Online PowerPivot Management Dashboard Processing Timer Job                                 4/8/2014 3:45:38 AM  MidTierService
Online PowerPivot Health Statistics Collector Timer Job                                     4/9/2014 1:00:12 PM  MidTierService
Online PowerPivot Data Refresh Timer Job                                                    4/9/2014 1:09:36 PM  MidTierService
Online Health Analysis Job (Daily, SQL Server PowerPivot Service Application, All Servers)  4/9/2014 12:00:00 AM MidTierService
Online Health Analysis Job (Daily, SQL Server PowerPivot Service Application, Any Server)   4/9/2014 12:00:00 AM MidTierService
Online Health Analysis Job (Weekly, SQL Server PowerPivot Service Application, All Servers) 4/6/2014 12:00:03 AM MidTierService
Online Health Analysis Job (Weekly, SQL Server PowerPivot Service Application, Any Server)  4/6/2014 12:00:03 AM MidTierService
Online PowerPivot Setup Extension Timer Job                                                 4/1/2014 1:40:31 AM  MidTierService
```

##  <a name="health-rules"></a><a name="bkmk_health_rules"></a><span data-ttu-id="2cca0-199">Правила определения исправности</span><span class="sxs-lookup"><span data-stu-id="2cca0-199">Health Rules</span></span>
 <span data-ttu-id="2cca0-200">В развертывании SharePoint 2013 меньше правил.</span><span class="sxs-lookup"><span data-stu-id="2cca0-200">There are fewer rules in a SharePoint 2013 deployment.</span></span> <span data-ttu-id="2cca0-201">Полный список правил для каждой среды SharePoint и объяснение использования правил см. в разделе [PowerPivot Health Rules-configure](../../power-pivot-sharepoint/configure-power-pivot-health-rules.md).</span><span class="sxs-lookup"><span data-stu-id="2cca0-201">For a full list of rules for each SharePoint environment and an explanation of how to use the rules, see [PowerPivot Health Rules - Configure](../../power-pivot-sharepoint/configure-power-pivot-health-rules.md).</span></span>

```powershell
Get-SPHealthAnalysisRule | Select name, enabled, summary | Where {$_.summary -Like "*power*"}  | Format-Table -Property * -AutoSize | Out-Default
```

```Output
Name                          Enabled Summary
----                          ------- -------         
SecondaryLogonHealthRule         True PowerPivot:  Secondary Logon service (seclogon) is disabled
DataRefreshTimerJobHealthRule    True PowerPivot: The PowerPivot Data Refresh timer job is disabled.
ASUsageLoadHealthRule            True PowerPivot: The ratio of load events to connections is too high.
ASMiniDumpHealthRule             True PowerPivot: One or more minidump files were found in the Logs directory, indicating a program crash
ASUsageCubeRule                  True PowerPivot: Usage data is not getting updated at the expected frequency.
ASADOMDNETHealthRule             True PowerPivot: ADOMD.NET is not installed on a standalone WFE that is configured for central admin
MidTierAcctReadPermissionRule    True PowerPivot: MidTier process account should have 'Full Read' permission on all associated SPWebApplications.
```

##  <a name="windows-and-uls-logs"></a><a name="bkmk_logs"></a><span data-ttu-id="2cca0-202">Журналы Windows и ULS</span><span class="sxs-lookup"><span data-stu-id="2cca0-202">Windows and ULS Logs</span></span>
 <span data-ttu-id="2cca0-203">**Журнал событий Windows**</span><span class="sxs-lookup"><span data-stu-id="2cca0-203">**Windows event log**</span></span>

 <span data-ttu-id="2cca0-204">Следующая команда выполняет поиск в журнале событий Windows событий, связанных с экземпляром [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] в режиме SharePoint.</span><span class="sxs-lookup"><span data-stu-id="2cca0-204">The following command will search the windows event log for events related to the instance of [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] in SharePoint mode.</span></span> <span data-ttu-id="2cca0-205">Сведения об отключении событий или изменении уровня событий см. в разделе [Настройка и просмотр файлов журнала SharePoint и журнала диагностики &#40;PowerPivot для SharePoint&#41;](../../power-pivot-sharepoint/configure-and-view-sharepoint-and-diagnostic-logging.md).</span><span class="sxs-lookup"><span data-stu-id="2cca0-205">For information on disabling events or changing the event level, see [Configure and View SharePoint Log Files  and Diagnostic Logging &#40;PowerPivot for SharePoint&#41;](../../power-pivot-sharepoint/configure-and-view-sharepoint-and-diagnostic-logging.md).</span></span>

 <span data-ttu-id="2cca0-206">**Имя службы:** MSOLAP$POWERPIVOT.</span><span class="sxs-lookup"><span data-stu-id="2cca0-206">**Service Name:** MSOLAP$POWERPIVOT</span></span>

 <span data-ttu-id="2cca0-207">**Отображаемое имя в службах Windows:** SQL Server Analysis Services (POWERPIVOT).</span><span class="sxs-lookup"><span data-stu-id="2cca0-207">**Display name in Windows Services:** SQL Server Analysis Services (POWERPIVOT)</span></span>

```powershell
Get-EventLog "application" | Where-Object {$_.source -Like "msolap`$powerpivot*"}  | Select timegenerated, entrytype , source, message | Format-Table -property * -AutoSize | Out-Default
```

```Output
TimeGenerated           EntryType Source            Message
-------------           --------- ------            -------
4/16/2014 1:45:19 PM  Information MSOLAP$POWERPIVOT Software usage metrics are disabled.
4/16/2014 1:45:19 PM  Information MSOLAP$POWERPIVOT Service started. Microsoft SQL Server Analysis Services 64 Bit Evaluation (x64) RTM 12.0.1997.5.
4/16/2014 1:45:18 PM  Information MSOLAP$POWERPIVOT The flight recorder was started.
4/14/2014 6:45:37 PM  Information MSOLAP$POWERPIVOT Software usage metrics are disabled.
```

 <span data-ttu-id="2cca0-208">**Журнал ULS SharePoint, последние 48 часов**</span><span class="sxs-lookup"><span data-stu-id="2cca0-208">**SharePoint ULS Log, last 48 hours**</span></span>

 <span data-ttu-id="2cca0-209">Следующая команда возвращает сообщения [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] из журнала ULS, созданные за последние 48 часов.</span><span class="sxs-lookup"><span data-stu-id="2cca0-209">The following command will return [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] messages from the ULS log that were created in the last 48 hours.</span></span> <span data-ttu-id="2cca0-210">Настройте параметр addhours в соответствии со своими требованиями.</span><span class="sxs-lookup"><span data-stu-id="2cca0-210">Adjust the addhours parameter for your need.</span></span>

```powershell
Get-SPLogEvent -StartTime(Get-Date).AddHours(-48) | Where-Object {$_.Area -eq "powerpivot service" -and $_.level -eq "high"} | Select timestamp, area, category, eventid,level, message | Format-Table -Property * -AutoSize | Out-Default
```

 <span data-ttu-id="2cca0-211">Следующий вариант команды возвращает из журнала только события категории **обновление данных** .</span><span class="sxs-lookup"><span data-stu-id="2cca0-211">The following variation of the command only returns log events for the **data refresh** category.</span></span>

```powershell
Get-SPLogEvent -starttime(Get-Date).addhours(-48) | Where-Object {$_.category -eq "data refresh" -and $_.level -eq "high"} | Select timestamp, area, category, eventid, level, correlation, message
```

```Output
Timestamp   : 4/14/2014 7:15:01 PM
Area        : PowerPivot Service
Category    : Data Refresh
EventID     : 43
Level       : High
Correlation : 5755879c-7cab-e097-8f80-f27895d44a77
Message     : The following error occurred when working with the service application, Default PowerPivot Service Application. Skipping the service application..

Timestamp   : 4/14/2014 7:15:02 PM
Area        : PowerPivot Service
Category    : Data Refresh
EventID     : 99
Level       : High
Correlation : 5755879c-7cab-e097-8f80-f27895d44a77
Message     : EXCEPTION: System.TimeoutException: The request channel timed out while waiting for a reply after 00:00:47.0625313. Increase the timeout value passed to 
              the call to Request or increase the SendTimeout value on the Binding. The time allotted to this operation may have been a portion of a longer timeout. 
              ---> System.TimeoutException: The HTTP request to 'http://localhost:32843/SecurityTokenServiceApplication/securitytoken.svc/actas' has exceeded the 
              allotted timeout of 00:00:54.5930000. The time allotted to this operation may have been a portion of a longer timeout. ---> System.Net.WebException: The 
              operation has timed out     at System.Net.HttpWebRequest.GetResponse()     at 
              System.ServiceModel.Channels.HttpChannelFactory`1.HttpRequestChannel.HttpChannelRequest.WaitForReply(TimeSpan timeout...
```

##  <a name="msolap-provider"></a><a name="bkmk_msolap"></a><span data-ttu-id="2cca0-212">Поставщик MSOLAP</span><span class="sxs-lookup"><span data-stu-id="2cca0-212">MSOLAP Provider</span></span>
 <span data-ttu-id="2cca0-213">Проверьте поставщик MSOLAP.</span><span class="sxs-lookup"><span data-stu-id="2cca0-213">Verify the provider MSOLAP provider.</span></span> [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)]<span data-ttu-id="2cca0-214">и [!INCLUDE[ssSQL14](../../../includes/sssql14-md.md)] [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] требует MSOLAP. 5.</span><span class="sxs-lookup"><span data-stu-id="2cca0-214">and [!INCLUDE[ssSQL14](../../../includes/sssql14-md.md)] [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] require MSOLAP.5.</span></span>

```powershell
$excelApp = Get-SPExcelServiceApplication
Get-SPExcelDataProvider -ExcelServiceApplication $excelApp | Select providerid, providertype, description | Where {$_.providerid -like "msolap*" } | Format-Table -Property * -AutoSize | Out-Default
```

```Output
ProviderId ProviderType Description
---------- ------------ -----------
MSOLAP     Oledb        Microsoft OLE DB Provider for OLAP Services     
MSOLAP.3   Oledb        Microsoft OLE DB Provider for OLAP Services 9.0 
MSOLAP.4   Oledb        Microsoft OLE DB Provider for OLAP Services 10.0
MSOLAP.5   Oledb        Microsoft OLE DB Provider for OLAP Services 11.0
```

 <span data-ttu-id="2cca0-215">Дополнительные сведения см. в статьях [Установка поставщика OLE DB служб Analysis Services на серверах SharePoint](../../../sql-server/install/install-the-analysis-services-ole-db-provider-on-sharepoint-servers.md) и [Добавление MSOLAP.5 в качестве надежного поставщика данных в службах Excel Services](https://technet.microsoft.com/library/hh758436.aspx).</span><span class="sxs-lookup"><span data-stu-id="2cca0-215">For more information, see [Install the Analysis Services OLE DB Provider on SharePoint Servers](../../../sql-server/install/install-the-analysis-services-ole-db-provider-on-sharepoint-servers.md) and [Add MSOLAP.5 as a Trusted Data Provider in Excel Services](https://technet.microsoft.com/library/hh758436.aspx).</span></span>

##  <a name="adomdnet-client-library"></a><a name="bkmk_adomd"></a><span data-ttu-id="2cca0-216">Клиентская библиотека ADOMD.Net</span><span class="sxs-lookup"><span data-stu-id="2cca0-216">ADOMD.Net client Library</span></span>

```powershell
Get-WMIObject -Class win32_product | Where-Object {$_.name -Like "*ado*"} | Select name, version, vendor | Format-Table -Property * -AutoSize | out-default
```

```Output
name                                                  version      vendor
----                                                  -------      ------
Microsoft SQL Server 2008 Analysis Services ADOMD.NET 10.1.2531.0  Microsoft Corporation
Microsoft SQL Server 2005 Analysis Services ADOMD.NET 9.00.1399.06 Microsoft Corporation
```

 <span data-ttu-id="2cca0-217">Дополнительные сведения можно найти в статье [Установка ADOMD.NET на веб-серверах, обслуживающих клиентские запросы, под управлением центра администрирования](../../../sql-server/install/install-adomd-net-on-web-front-end-servers-running-central-administration.md).</span><span class="sxs-lookup"><span data-stu-id="2cca0-217">For more information, see [Install ADOMD.NET on Web Front-End Servers Running Central Administration](../../../sql-server/install/install-adomd-net-on-web-front-end-servers-running-central-administration.md).</span></span>

##  <a name="health-data-collection-rules"></a><a name="bkmk_health_collection"></a><span data-ttu-id="2cca0-218">Правила сбора данных о работоспособности</span><span class="sxs-lookup"><span data-stu-id="2cca0-218">Health Data Collection Rules</span></span>
 <span data-ttu-id="2cca0-219">Убедитесь в том, что в поле **Состояние** указано значение «В сети», а в поле **Включен** — значение True.</span><span class="sxs-lookup"><span data-stu-id="2cca0-219">Verify the **Status** is Online and **Enabled** is True.</span></span>

```powershell
Get-SPUsageDefinition | Select name, status, enabled, tablename, DaysToKeepDetailedData | Where {$_.name -Like "powerpivot*"} | Format-Table -Property * -AutoSize | Out-Default
```

```Output
Name                         Status Enabled TableName                   DaysToKeepDetailedData
----                         ------ ------- ---------                   ----------------------
PowerPivot Connections       OnlineTrue AnalysisServicesConnections  14
PowerPivot Load Data Usage   Online    True AnalysisServicesLoads                           14
PowerPivot Query Usage       Online    True AnalysisServicesRequests                        14
PowerPivot Unload Data Usage Online    True AnalysisServicesUnloads                         14
```

 <span data-ttu-id="2cca0-220">Дополнительные сведения см. в статье [PowerPivot Usage Data Collection](../../power-pivot-sharepoint/power-pivot-usage-data-collection.md).</span><span class="sxs-lookup"><span data-stu-id="2cca0-220">For more information, see [PowerPivot Usage Data Collection](../../power-pivot-sharepoint/power-pivot-usage-data-collection.md).</span></span>

##  <a name="solutions"></a><a name="bkmk_solutions"></a><span data-ttu-id="2cca0-221">Решения</span><span class="sxs-lookup"><span data-stu-id="2cca0-221">Solutions</span></span>
 <span data-ttu-id="2cca0-222">Если другие компоненты находятся в сети, то проверку решений можно пропустить.</span><span class="sxs-lookup"><span data-stu-id="2cca0-222">If the other components are online then you can skip verifying the solutions.</span></span> <span data-ttu-id="2cca0-223">Однако, если правила определения исправности отсутствуют, убедитесь в том, что существует два решения PowerPivot и при этом они имеют состояние **В сети** и **Развернуто**.</span><span class="sxs-lookup"><span data-stu-id="2cca0-223">If however the Health rules are missing, verify the two solutions exist and showed Verify the two PowerPivot solutions are **Online** and **Deployed**.</span></span>

```powershell
Get-SPSolution | Select name, status, deployed, DeploymentState, DeployedServers | Where {$_.Name -Like "*powerpivot*"} | Format-Table -Property * -AutoSize | Out-Default
```

<span data-ttu-id="2cca0-224">SharePoint 2013.</span><span class="sxs-lookup"><span data-stu-id="2cca0-224">SharePoint 2013:</span></span>

```Output
Name                                 Status Deployed        DeploymentState DeployedServers
----                                 ------ --------        --------------- ---------------
powerpivotfarm14solution.wsp         Online     True         GlobalDeployed {UETESTA00}
powerpivotfarmsolution.wsp           Online     True         GlobalDeployed {UETESTA00}
powerpivotwebapplicationsolution.wsp Online     True WebApplicationDeployed {UETESTA00}
```

<span data-ttu-id="2cca0-225">SharePoint 2010.</span><span class="sxs-lookup"><span data-stu-id="2cca0-225">SharePoint 2010:</span></span>

```Output
Name                 Status Deployed        DeploymentState DeployedServers 
----                 ------ --------        --------------- --------------- 
powerpivotfarm.wsp   Online     True         GlobalDeployed {uesql11spoint2}
powerpivotwebapp.wsp Online     True WebApplicationDeployed {uesql11spoint2}
```

 <span data-ttu-id="2cca0-226">Дополнительные сведения о развертывании решений SharePoint см. в разделе [Развертывание пакетов решений (SharePoint Server 2010)](https://technet.microsoft.com/library/cc262995\(v=office.14\).aspx).</span><span class="sxs-lookup"><span data-stu-id="2cca0-226">For more information on how to deploy SharePoint solutions, see [Deploy solution packages (SharePoint Server 2010)](https://technet.microsoft.com/library/cc262995\(v=office.14\).aspx).</span></span>

##  <a name="manual-verification-steps"></a><a name="bkmk_manual"></a> <span data-ttu-id="2cca0-227">Действия по выполнению проверки вручную</span><span class="sxs-lookup"><span data-stu-id="2cca0-227">Manual Verification Steps</span></span>
 <span data-ttu-id="2cca0-228">В этом разделе описаны шаги по проверке, которые нельзя выполнить с помощью командлетов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2cca0-228">This section describes verification steps that cannot be completed with PowerShell cmdlets.</span></span>

 <span data-ttu-id="2cca0-229">**Плановое обновление данных.** Для расписания обновления книги задайте **Кроме того, как можно скорее обновите данные**.</span><span class="sxs-lookup"><span data-stu-id="2cca0-229">**Scheduled Data Refresh:** Configure the refresh schedule a workbook to **Also refresh as soon as possible**.</span></span>  <span data-ttu-id="2cca0-230">Дополнительные сведения см. в разделе "Проверка обновления данных" раздела [Обновление данных и источники данных, не поддерживающие проверку подлинности Windows &#40;PowerPivot для SharePoint&#41;](../../power-pivot-sharepoint/schedule-data-refresh-and-data-sources-no-windows-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="2cca0-230">For more information, see the "Verify Data Refresh" section of [Schedule Data Refresh and Data Sources That Do Not Support Windows Authentication &#40;PowerPivot for SharePoint&#41;](../../power-pivot-sharepoint/schedule-data-refresh-and-data-sources-no-windows-authentication.md).</span></span>

##  <a name="more-resources"></a><a name="bkmk_more_resources"></a><span data-ttu-id="2cca0-231">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="2cca0-231">More Resources</span></span>
 <span data-ttu-id="2cca0-232">[Командлеты для администрирования веб-сервера (IIS) в Windows PowerShell](https://technet.microsoft.com/library/ee790599.aspx).</span><span class="sxs-lookup"><span data-stu-id="2cca0-232">[Web Server (IIS) Administration Cmdlets in Windows PowerShell](https://technet.microsoft.com/library/ee790599.aspx).</span></span>

 <span data-ttu-id="2cca0-233">[PowerShell для проверки служб, состояние веб-сайтов IIS и пула приложений в SharePoint](https://gallery.technet.microsoft.com/office/PowerShell-to-check-a6ed72a0).</span><span class="sxs-lookup"><span data-stu-id="2cca0-233">[PowerShell to check services, IIS sites and Application Pool status in SharePoint](https://gallery.technet.microsoft.com/office/PowerShell-to-check-a6ed72a0).</span></span>

 <span data-ttu-id="2cca0-234">[Ссылка на Windows PowerShell для SharePoint 2013](https://technet.microsoft.com/library/ee890108\(v=office.15\).aspx)</span><span class="sxs-lookup"><span data-stu-id="2cca0-234">[Windows PowerShell for SharePoint 2013 reference](https://technet.microsoft.com/library/ee890108\(v=office.15\).aspx)</span></span>

 <span data-ttu-id="2cca0-235">[Ссылка на Windows PowerShell для SharePoint Foundation 2010](https://technet.microsoft.com/library/ee890105\(v=office.14\).aspx)</span><span class="sxs-lookup"><span data-stu-id="2cca0-235">[Windows PowerShell for SharePoint Foundation 2010 reference](https://technet.microsoft.com/library/ee890105\(v=office.14\).aspx)</span></span>

 <span data-ttu-id="2cca0-236">[Управление службами Excel с помощью Windows PowerShell (SharePoint Server 2010)](https://technet.microsoft.com/library/ff191201\(v=office.14\).aspx)</span><span class="sxs-lookup"><span data-stu-id="2cca0-236">[Manage Excel Services with Windows PowerShell (SharePoint Server 2010)](https://technet.microsoft.com/library/ff191201\(v=office.14\).aspx)</span></span>

 [<span data-ttu-id="2cca0-237">Просмотр и чтение файлов журналов программы установки SQL Server</span><span class="sxs-lookup"><span data-stu-id="2cca0-237">View and Read SQL Server Setup Log Files</span></span>](../../../database-engine/install-windows/view-and-read-sql-server-setup-log-files.md)

 [<span data-ttu-id="2cca0-238">Использование командлета Get-EvenLog</span><span class="sxs-lookup"><span data-stu-id="2cca0-238">Use the Get-EvenLog cmdlet</span></span>](https://technet.microsoft.com/library/ee176846.aspx)

##  <a name="full-powershell-script"></a><a name="bkmk_full_script"></a><span data-ttu-id="2cca0-239">Полный сценарий PowerShell</span><span class="sxs-lookup"><span data-stu-id="2cca0-239">Full PowerShell Script</span></span>
 <span data-ttu-id="2cca0-240">Следующий скрипт содержит все команды, приведенные в предыдущих разделах.</span><span class="sxs-lookup"><span data-stu-id="2cca0-240">The Following script contains all of the commands from the previous sections.</span></span> <span data-ttu-id="2cca0-241">Скрипт выполняет команды в том же порядке, в котором они перечислены в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="2cca0-241">The script runs the commands in the same order as they are presented in this topic.</span></span> <span data-ttu-id="2cca0-242">Скрипт содержит некоторые дополнительные изменения команд, приведенных в этом разделе, на тот случай, если необходима дополнительная фильтрация.</span><span class="sxs-lookup"><span data-stu-id="2cca0-242">The script contains some optional variations of the commands noted in this topic in case you need additional filtering.</span></span> <span data-ttu-id="2cca0-243">Изменения отключаются с помощью символа комментария (#).</span><span class="sxs-lookup"><span data-stu-id="2cca0-243">The variations are disabled with a comment character (#).</span></span> <span data-ttu-id="2cca0-244">Скрипт также содержит некоторые инструкции для проверки служб [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] в режиме интеграции с SharePoint.</span><span class="sxs-lookup"><span data-stu-id="2cca0-244">The script also includes some statements for verifying [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] SharePoint mode.</span></span> <span data-ttu-id="2cca0-245">Инструкции [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] отключаются с помощью символа комментария (#).</span><span class="sxs-lookup"><span data-stu-id="2cca0-245">The [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] statements are disabled with a comment character (#).</span></span>

```powershell
# This script audits services related to PowerPivot for SharePoint
$starttime = Get-Date
write-host -foregroundcolor DarkGray StartTime $starttime

Write-Host  "Import the SharePoint PowerShell snappin"
Add-PSSnapin Microsoft.Sharepoint.Powershell -EA 0

Write-Host -ForegroundColor Green "Analysis Services Windows Service"
Write-Host -ForegroundColor Green ">>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>"
Get-Service | Select name, displayname, status | Where {$_.Name -eq "msolap`$powerpivot"} | Format-Table -Property * -AutoSize | Out-Default

Write-Host -ForegroundColor Green "PowerPivotEngineService and PowerPivotSystemService"
Write-Host -ForegroundColor Green ">>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>"

Get-PowerPivotSystemService | Select typename, status, applications, farm | Format-Table -property * -AutoSize | Out-Default
# If needed, you can run the following to compare job definitions specific to the service against the results of the timer job definition section
#Get-PowerPivotSystemService | select -ExpandProperty jobdefinitions | select displayname, schedule, service | format-table -property * -autosize | out-default

Get-PowerPivotEngineService | Select typename, status, name, instances, farm | Format-Table -property * -AutoSize | Out-Default
# If needed, you can run the following to compare job definitions specific to the service against the results of the timer job definition section
#Get-PowerPivotEngineService | select -ExpandProperty jobdefinitions | select displayname, schedule, service | format-table -property * -autosize | out-default

#Write-Host -ForegroundColor Green "Service Instances - optional if you want to associate services with the server"
#Write-Host -ForegroundColor Green ">>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>"
#Get-SPServiceInstance | select typename, status, server, service, instance | where {$_.TypeName -like "*powerpivot*" -or $_.TypeName -like "*excel*" -or $_.TypeName -like "*Analysis Services*"} | format-table -property * -autosize | out-default
#Get-PowerPivotEngineServiceInstance  | select typename, ASServername, status, server, service, instance
#Get-PowerPivotSystemServiceInstance  | select typename, ASSServerName, status, server, service, instance

Write-Host -ForegroundColor Green "PowerPivot And Excel Service Applications"
Write-Host -ForegroundColor Green ">>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>"
Get-PowerPivotServiceApplication | Select typename,name, status, unattendedaccount, applicationpool, farm, database
Get-SPExcelServiceApplication | Select typename,  DisplayName, status

#Write-Host ""
Write-Host -ForegroundColor Green "PowerPivot Service Application pool"
Write-Host -ForegroundColor Green ">>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>"
# the following assumes there is only 1 PowerPivot Service Application, and returns that application's pool name.  if you have more than one, use the 2nd version
$poolname = [string](Get-PowerPivotServiceApplication | Select -Property applicationpool)
$position = $poolname.lastindexof("=")
$poolname = $poolname.substring($position+1)
$poolname = $poolname.substring(0,$poolname.length-1)
Get-SPServiceApplicationPool | Select name, status, processaccountname, id | Where {$_.Name -eq $poolname} | Format-Table -Property * -AutoSize | Out-Default

#Write-Host ""
Write-Host -ForegroundColor Green "PowerPivot and Excel Service Application Proxy"
Write-Host -ForegroundColor Green ">>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>"
Get-SPServiceApplicationProxy |  Select typename, status, unattendedaccount, displayname | Where {$_.TypeName -like "*powerpivot*" -or $_.TypeName -like "*excel services*"} | Format-Table -Property * -AutoSize | Out-Default
#Get-SPServiceApplicationProxy |  select typename, status, unattendedaccount, displayname | where {$_.TypeName -like "*powerpivot*" -or $_.TypeName -like "*Reporting Services*" -or $_.TypeName -like "*excel services*"} | format-table -property * -autosize | out-default

Write-Host -ForegroundColor Green "DATABASES"
Write-Host -ForegroundColor Green ">>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>"
Get-SPDatabase | Select name, status, server, typename | Where {$_.TypeName -eq "content database" -or $_.TypeName -like "*Gemini*"} | Format-Table -Property * -AutoSize | Out-Default
#Get-SPDatabase | select name, status, server, typename | where {$_.TypeName -eq "content database" -or $_.TypeName -like "*Gemini*" -or $_.TypeName -like "*ReportingServices*"}

Write-Host -ForegroundColor Green "features"
Write-Host -ForegroundColor Green ">>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>"
Get-SPFeature | Select displayname, status, scope, farm | Where {$_.displayName -like "*powerpivot*"} | Format-Table -Property * -AutoSize | Out-Default
#Get-SPFeature | select displayname, status, scope, farm | where {$_.displayName -like "*powerpivot*" -or $_.displayName -like "*ReportServer*"}  | format-table -property * -autosize | out-default

Write-Host -ForegroundColor Green "Timer Jobs (Job Definitions) -- list is the same as seen in the 'Review timer job definitions' section of the management dashboard"
Write-Host -ForegroundColor Green ">>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>"
Get-SPTimerJob | Where {$_.service -like "*power*" -or $_.service -like "*mid*"} | Select status, displayname, LastRunTime, service | Format-Table -Property * -AutoSize | Out-Default

Write-Host -ForegroundColor Green "health rules"
Write-Host -ForegroundColor Green ">>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>"
Get-SPHealthAnalysisRule | Select name, enabled, summary | Where {$_.summary -Like "*power*"}  | Format-Table -Property * -AutoSize | Out-Default

$time = Get-Date
Write-Host -ForegroundColor DarkGray StartTime $starttime
Write-Host -ForegroundColor DarkGray EndTime $time

Write-Host -ForegroundColor Green "Windows Event Log data MSSQL$POWERPIVOT and "
Write-Host -ForegroundColor Green ">>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>"
Get-EventLog "application" | Where-Object {$_.source -like "msolap`$powerpivot*"}  | Select timegenerated, entrytype , source, message | Format-Table -Property * -autosize | Out-Default
#The following is the same command but with the Inforamtion events filtered out.
#Get-EventLog "application" | Where-Object {$_.source -like "msolap`$powerpivot*" -and ($_.entrytype -match "error" -or $_.entrytype -match "critical" -or $_.entrytype -match "warning")}  |select timegenerated, entrytype , source, message | format-table -property * -autosize | out-default

#Write-Host ""
Write-Host -ForegroundColor Green "ULS Log data"
Write-Host -ForegroundColor Green ">>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>"
Get-SPLogEvent -StartTime(Get-Date).AddHours(-48) | Where-Object {$_.Area -eq "powerpivot service" -and $_.level -eq "high"} | Select timestamp, area, category, eventid, level, correlation, message | Format-Table -Property * -AutoSize | Out-Default
#the following example filters for the category 'data refresh'
#Get-SPLogEvent -starttime(get-date).addhours(-48) | Where-Object {$_.category -eq "data refresh" -and $_.level -eq "high"} | select timestamp, area, category, eventid, level, correlation, message

$time = Get-Date
Write-Host -ForegroundColor DarkGray StartTime $starttime
Write-Host -ForegroundColor DarkGray EndTime $time

Write-Host -ForegroundColor Green "MSOLAP data provider for Excel Servivces, service application"
Write-Host -ForegroundColor Green ">>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>"
$excelApp = Get-SPExcelServiceApplication
Get-SPExcelDataProvider -ExcelServiceApplication $excelApp | Select providerid, providertype, description | Where {$_.providerid -like "msolap*" } | Format-Table -Property * -AutoSize | Out-Default

Write-Host -ForegroundColor Green "ADOMD.net client library"
Write-Host -ForegroundColor Green ">>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>"
Get-WMIObject -Class win32_product | Where-Object {$_.name -like "*ado*"} | Select name, version, vendor | Format-Table -Property * -AutoSize | Out-Default

Write-Host -ForegroundColor Green "Usage Data Rules"
Write-Host -ForegroundColor Green ">>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>"
Get-SPUsageDefinition | Select name, status, enabled, tablename, DaysToKeepDetailedData | Where {$_.name -like "powerpivot*"} | Format-Table -Property * -AutoSize | Out-Default

Write-Host -ForegroundColor Green "Solutions"
Write-Host -ForegroundColor Green ">>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>"
Get-SPSolution | Select name, status, deployed, DeploymentState, DeployedServers | Where {$_.Name -like "*powerpivot*"} | Format-Table -Property * -AutoSize | Out-Default

$time = Get-Date
Write-Host -ForegroundColor DarkGray StartTime $starttime
Write-Host -ForegroundColor DarkGray EndTime $time
```
