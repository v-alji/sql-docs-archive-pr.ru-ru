---
title: Запуск помощника по обновлению (Командная строка) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Upgrade Advisor [SQL Server], running
- command prompt [Upgrade Advisor]
- UpgradeAdvisorWizardCmd utility
- XML formats [Upgrade Advisor]
ms.assetid: 7c83049b-9227-4723-9b7f-66288bc6bd1d
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: a968f9d70788e1100af263f3ef9947493b4bd0c0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654740"
---
# <a name="running-upgrade-advisor-command-prompt"></a><span data-ttu-id="b622e-102">Запуск помощника по обновлению (командная строка)</span><span class="sxs-lookup"><span data-stu-id="b622e-102">Running Upgrade Advisor (Command Prompt)</span></span>
  <span data-ttu-id="b622e-103">Используйте служебную программу **UpgradeAdvisorWizardCmd** для запуска помощника по обновлению из командной строки.</span><span class="sxs-lookup"><span data-stu-id="b622e-103">Use the **UpgradeAdvisorWizardCmd** utility to run Upgrade Advisor from the command prompt.</span></span> <span data-ttu-id="b622e-104">Можно задать вывод результата в формате XML или в файле формата CSV (с разделителями-запятыми).</span><span class="sxs-lookup"><span data-stu-id="b622e-104">You can choose to receive results in XML format or in a file with comma-separated values.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b622e-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b622e-105">Syntax</span></span>  
  
```  
  
      UpgradeAdvisorWizardCmd [ -? ]  |   
    [ -ConfigFilefilename | <server_info> ]  
    [ -SqlUserlogin_id-SqlPasswordpassword ]  
    [ -CSV ]  
  
where <server_info> is any combination of the following:  
        -Serverserver_name-Instanceinstance_name-ASInstanceAS_instance_name-RSInstanceRS_instance_name  
```  
  
## <a name="arguments"></a><span data-ttu-id="b622e-106">Аргументы</span><span class="sxs-lookup"><span data-stu-id="b622e-106">Arguments</span></span>  
 <span data-ttu-id="b622e-107">**-?**</span><span class="sxs-lookup"><span data-stu-id="b622e-107">**-?**</span></span>  
 <span data-ttu-id="b622e-108">Отображает синтаксис команды.</span><span class="sxs-lookup"><span data-stu-id="b622e-108">Displays the command syntax.</span></span>  
  
 <span data-ttu-id="b622e-109">**-ConfigFile** _имя файла_</span><span class="sxs-lookup"><span data-stu-id="b622e-109">**-ConfigFile** _filename_</span></span>  
 <span data-ttu-id="b622e-110">— Это путь и имя файла XML, содержащего параметры, используемые при запуске служебной программы **UpgradeAdvisorWizardCmd** .</span><span class="sxs-lookup"><span data-stu-id="b622e-110">Is the path name and file name of an XML file that contains settings to use when you run the **UpgradeAdvisorWizardCmd** utility.</span></span>  
  
 <span data-ttu-id="b622e-111">*<server_info>*</span><span class="sxs-lookup"><span data-stu-id="b622e-111">*<server_info>*</span></span>  
 <span data-ttu-id="b622e-112">Задает анализируемый компьютер и экземпляр.</span><span class="sxs-lookup"><span data-stu-id="b622e-112">Specifies which computer and instance to analyze.</span></span> <span data-ttu-id="b622e-113">Используйте эти параметры, если не применяется файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="b622e-113">Use these options if you are not using a configuration file.</span></span>  
  
 <span data-ttu-id="b622e-114">*<server_info>* может быть любым сочетанием следующих четырех аргументов:</span><span class="sxs-lookup"><span data-stu-id="b622e-114">*<server_info>* can be any combination of the following four arguments:</span></span>  
  
 <span data-ttu-id="b622e-115">**-Server** _server_name_</span><span class="sxs-lookup"><span data-stu-id="b622e-115">**-Server** _server_name_</span></span>  
 <span data-ttu-id="b622e-116">Задает имя компьютера для проведения анализа.</span><span class="sxs-lookup"><span data-stu-id="b622e-116">Specifies the name of the computer to analyze.</span></span> <span data-ttu-id="b622e-117">Это может быть локальный компьютер (значение по умолчанию) или удаленный компьютер.</span><span class="sxs-lookup"><span data-stu-id="b622e-117">This can be the local computer, which is the default value, or a remote computer.</span></span>  
  
 <span data-ttu-id="b622e-118">**-Instance** _instance_name_</span><span class="sxs-lookup"><span data-stu-id="b622e-118">**-Instance** _instance_name_</span></span>  
 <span data-ttu-id="b622e-119">Задает имя анализируемого экземпляра.</span><span class="sxs-lookup"><span data-stu-id="b622e-119">Specifies the name of the instance to analyze.</span></span> <span data-ttu-id="b622e-120">Значение по умолчанию отсутствует.</span><span class="sxs-lookup"><span data-stu-id="b622e-120">There is no default value.</span></span> <span data-ttu-id="b622e-121">Если этот параметр не указан, то компонент [!INCLUDE[ssDE](../../includes/ssde-md.md)] просматриваться не будет.</span><span class="sxs-lookup"><span data-stu-id="b622e-121">If you do not specify this parameter, the [!INCLUDE[ssDE](../../includes/ssde-md.md)] is not scanned.</span></span> <span data-ttu-id="b622e-122">Значением для экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] по умолчанию является MSSQLSERVER.</span><span class="sxs-lookup"><span data-stu-id="b622e-122">The value for a default instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is MSSQLSERVER.</span></span> <span data-ttu-id="b622e-123">Для именованного экземпляра укажите имя экземпляра.</span><span class="sxs-lookup"><span data-stu-id="b622e-123">For a named instance, use the instance name.</span></span>  
  
 <span data-ttu-id="b622e-124">**-Асинстанце**  _AS_instance_name_</span><span class="sxs-lookup"><span data-stu-id="b622e-124">**-ASInstance**  _AS_instance_name_</span></span>  
 <span data-ttu-id="b622e-125">Задает имя экземпляра служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] для анализа.</span><span class="sxs-lookup"><span data-stu-id="b622e-125">Specifies the name of the instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] to analyze.</span></span> <span data-ttu-id="b622e-126">Значение по умолчанию отсутствует.</span><span class="sxs-lookup"><span data-stu-id="b622e-126">There is no default value.</span></span> <span data-ttu-id="b622e-127">Если это значение не указано, то службы [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] просматриваться не будут.</span><span class="sxs-lookup"><span data-stu-id="b622e-127">If you do not specify this value, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] is not scanned.</span></span> <span data-ttu-id="b622e-128">Значением для экземпляра служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] по умолчанию является MSSQLServerOLAPService.</span><span class="sxs-lookup"><span data-stu-id="b622e-128">The value for a default instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] is MSSQLServerOLAPService.</span></span> <span data-ttu-id="b622e-129">Для именованного экземпляра укажите имя экземпляра.</span><span class="sxs-lookup"><span data-stu-id="b622e-129">For a named instance, use the instance name.</span></span>  
  
 <span data-ttu-id="b622e-130">**-Рсинстанце**  _RS_instance_name_</span><span class="sxs-lookup"><span data-stu-id="b622e-130">**-RSInstance**  _RS_instance_name_</span></span>  
 <span data-ttu-id="b622e-131">Задает имя экземпляра служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] для анализа.</span><span class="sxs-lookup"><span data-stu-id="b622e-131">Specifies the name of the instance of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] to analyze.</span></span> <span data-ttu-id="b622e-132">Значение по умолчанию отсутствует.</span><span class="sxs-lookup"><span data-stu-id="b622e-132">There is no default value.</span></span> <span data-ttu-id="b622e-133">Если это значение не указано, то службы [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] просматриваться не будут.</span><span class="sxs-lookup"><span data-stu-id="b622e-133">If you do not specify this value, [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] is not scanned.</span></span> <span data-ttu-id="b622e-134">Значением для экземпляра по умолчанию служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] является ReportServer.</span><span class="sxs-lookup"><span data-stu-id="b622e-134">The value for a default instance of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] is ReportServer.</span></span> <span data-ttu-id="b622e-135">Для именованного экземпляра укажите имя экземпляра.</span><span class="sxs-lookup"><span data-stu-id="b622e-135">For a named instance, use the instance name.</span></span>  
  
 <span data-ttu-id="b622e-136">**-SqlUser** _login_ID_</span><span class="sxs-lookup"><span data-stu-id="b622e-136">**-SqlUser** _login_id_</span></span>  
 <span data-ttu-id="b622e-137">При использовании проверки подлинности [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] это значение является именем входа [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], которое помощник по обновлению использует для соединения с экземпляром [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b622e-137">If you are using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication, this value is the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login that Upgrade Advisor will use to connect to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="b622e-138">Если имя входа не указано, для соединения с экземпляром [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] используется проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="b622e-138">If you do not specify a login, Windows Authentication is used to connect to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span>  
  
 <span data-ttu-id="b622e-139">**-SqlPassword** _пароль_</span><span class="sxs-lookup"><span data-stu-id="b622e-139">**-SqlPassword** _password_</span></span>  
 <span data-ttu-id="b622e-140">Если используется аргумент **-SqlUser** , используйте этот аргумент, чтобы указать пароль для [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] имени входа.</span><span class="sxs-lookup"><span data-stu-id="b622e-140">If you use the **-SqlUser** argument, use this argument to specify the password for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login.</span></span>  
  
 <span data-ttu-id="b622e-141">**-CSV**</span><span class="sxs-lookup"><span data-stu-id="b622e-141">**-CSV**</span></span>  
 <span data-ttu-id="b622e-142">Укажите этот аргумент, чтобы сформировать результат в виде CSV-файла с разделителями-запятыми дополнительно к стандартному представлению результатов в виде XML.</span><span class="sxs-lookup"><span data-stu-id="b622e-142">Specifies to provide results as comma-separated values to a .csv file in addition to the standard XML results.</span></span> <span data-ttu-id="b622e-143">Результаты записываются в папку "Мои документы" \\ [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Advisor\110\Reports Upgrade.</span><span class="sxs-lookup"><span data-stu-id="b622e-143">Results are written to the My Documents\\[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Upgrade Advisor\110\Reports folder.</span></span>  
  
## <a name="return-values"></a><span data-ttu-id="b622e-144">Возвращаемые значения</span><span class="sxs-lookup"><span data-stu-id="b622e-144">Return Values</span></span>  
 <span data-ttu-id="b622e-145">В следующей таблице показаны значения, возвращаемые **UpgradeAdvisorWizardCmd** .</span><span class="sxs-lookup"><span data-stu-id="b622e-145">The following table shows the values that **UpgradeAdvisorWizardCmd** returns.</span></span>  
  
|<span data-ttu-id="b622e-146">Значение</span><span class="sxs-lookup"><span data-stu-id="b622e-146">Value</span></span>|<span data-ttu-id="b622e-147">Описание</span><span class="sxs-lookup"><span data-stu-id="b622e-147">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b622e-148">0</span><span class="sxs-lookup"><span data-stu-id="b622e-148">0</span></span>|<span data-ttu-id="b622e-149">Анализ успешно завершен, проблем с обновлением не обнаружено.</span><span class="sxs-lookup"><span data-stu-id="b622e-149">Analysis succeeded, no upgrade issues found.</span></span>|  
|<span data-ttu-id="b622e-150">положительное целое число</span><span class="sxs-lookup"><span data-stu-id="b622e-150">positive integer</span></span>|<span data-ttu-id="b622e-151">Анализ успешно завершен, обнаружены проблемы с обновлением.</span><span class="sxs-lookup"><span data-stu-id="b622e-151">Analysis succeeded, upgrade issues found.</span></span>|  
|<span data-ttu-id="b622e-152">отрицательное целое число</span><span class="sxs-lookup"><span data-stu-id="b622e-152">negative integer</span></span>|<span data-ttu-id="b622e-153">Анализ не выполнен.</span><span class="sxs-lookup"><span data-stu-id="b622e-153">Analysis failed.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b622e-154">Remarks</span><span class="sxs-lookup"><span data-stu-id="b622e-154">Remarks</span></span>  
 <span data-ttu-id="b622e-155">За исключением имен пользователей и паролей для проверки подлинности [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], вся информация, необходимая для запуска анализа, может быть предоставлена в XML-файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="b622e-155">All information that is required to run the analysis, other than [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication user names and passwords, can be provided in an XML configuration file.</span></span> <span data-ttu-id="b622e-156">Этот XML-файл конфигурации документирован в шаблоне.</span><span class="sxs-lookup"><span data-stu-id="b622e-156">This XML configuration file is documented in the template.</span></span> <span data-ttu-id="b622e-157">Можно анализировать все установленные компоненты в экземпляре [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] без применения файла конфигурации со значениями по умолчанию, указав имена компьютеров и имена экземпляров.</span><span class="sxs-lookup"><span data-stu-id="b622e-157">If you do not use a configuration file, you can analyze all installed components in an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using default settings by specifying computer names and instance names.</span></span> <span data-ttu-id="b622e-158">Описания настроек файла конфигурации по умолчанию см. далее в этом разделе в таблице «Описание элементов».</span><span class="sxs-lookup"><span data-stu-id="b622e-158">See the "Element Descriptions" table later in this topic for a description of the default configuration file settings.</span></span>  
  
## <a name="configuration-file-template"></a><span data-ttu-id="b622e-159">Шаблон файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="b622e-159">Configuration File Template</span></span>  
 <span data-ttu-id="b622e-160">Следующий XML-файл можно использовать в качестве шаблона для создания собственных файлов конфигурации.</span><span class="sxs-lookup"><span data-stu-id="b622e-160">Use the following XML as a template for creating your own configuration files.</span></span> <span data-ttu-id="b622e-161">Шаблон можно изменить в соответствии с потребностями конкретной организации.</span><span class="sxs-lookup"><span data-stu-id="b622e-161">You can modify the template to meet the needs of your organization.</span></span>  
  
```xml  
<Configuration>  
    <Server> </Server>  
    <Instance></Instance>  
    <Components>  
        <SQLServer>  
            <Databases>  
                <Database></Database>  
            </Databases>  
            <TraceFiles>  
                <TraceFile></TraceFile>  
            </TraceFiles>  
            <BatchFiles>  
                <BatchFile></BatchFile>  
            </BatchFiles>  
            <BatchSeparator></BatchSeparator>  
        </SQLServer>  
        <AnalysisServices>  
            <ASInstance></ASInstance>  
            <Databases>  
                <Database></Database>  
            </Databases>  
        </AnalysisServices>  
        <ReportingServices>  
            <RSInstance></RSInstance>  
        </ReportingServices>  
        <IntegrationServices>  
            <PackagePath></PackagePath>  
        </IntegrationServices>  
    </Components>  
</Configuration>  
```  
  
## <a name="element-descriptions"></a><span data-ttu-id="b622e-162">Описание элементов</span><span class="sxs-lookup"><span data-stu-id="b622e-162">Element Descriptions</span></span>  
  
|<span data-ttu-id="b622e-163">Тег</span><span class="sxs-lookup"><span data-stu-id="b622e-163">Tag</span></span>|<span data-ttu-id="b622e-164">Определение</span><span class="sxs-lookup"><span data-stu-id="b622e-164">Definition</span></span>|<span data-ttu-id="b622e-165">Наличие</span><span class="sxs-lookup"><span data-stu-id="b622e-165">Occurrence</span></span>|  
|---------|----------------|----------------|  
|`Configuration`|<span data-ttu-id="b622e-166">Родительский элемент для файла конфигурации помощника по обновлению.</span><span class="sxs-lookup"><span data-stu-id="b622e-166">Parent element for Upgrade Advisor configuration file.</span></span>|<span data-ttu-id="b622e-167">Должен присутствовать один раз в каждом файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="b622e-167">Required once per configuration file.</span></span>|  
|`Server`|<span data-ttu-id="b622e-168">Имя анализируемого сервера.</span><span class="sxs-lookup"><span data-stu-id="b622e-168">Name of the server to analyze.</span></span>|<span data-ttu-id="b622e-169">Может присутствовать один раз в каждом файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="b622e-169">Optional once per configuration file.</span></span> <span data-ttu-id="b622e-170">Значением по умолчанию является локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="b622e-170">The default value is the local computer.</span></span>|  
|`Instance`|<span data-ttu-id="b622e-171">Имя экземпляра анализируемого компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b622e-171">Name of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] instance to analyze.</span></span>|<span data-ttu-id="b622e-172">Может присутствовать один раз в каждом файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="b622e-172">Optional once per configuration file.</span></span> <span data-ttu-id="b622e-173">Значением по умолчанию является экземпляр по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b622e-173">The default value is the default instance.</span></span><br /><br /> <span data-ttu-id="b622e-174">Требуется один раз для каждого файла конфигурации, если на сервере имеется элемент [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] или элемент `IntegrationServices`.</span><span class="sxs-lookup"><span data-stu-id="b622e-174">Required once per configuration file, if a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] element or an `IntegrationServices` element is present on the server.</span></span>|  
|`Components`|<span data-ttu-id="b622e-175">Содержит элементы, указывающие анализируемые компоненты.</span><span class="sxs-lookup"><span data-stu-id="b622e-175">Contains elements that specify which components to analyze.</span></span>|<span data-ttu-id="b622e-176">Должен присутствовать один раз в каждом файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="b622e-176">Required once per configuration file.</span></span>|  
|`SQLServer`|<span data-ttu-id="b622e-177">Содержит настройки анализа для экземпляра компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b622e-177">Contains analysis settings for an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>|<span data-ttu-id="b622e-178">Может присутствовать один раз в каждом файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="b622e-178">Optional once per configuration file.</span></span> <span data-ttu-id="b622e-179">Если не задан, базы данных компонента служб [!INCLUDE[ssDE](../../includes/ssde-md.md)] не анализируются.</span><span class="sxs-lookup"><span data-stu-id="b622e-179">If not specified, [!INCLUDE[ssDE](../../includes/ssde-md.md)] databases are not analyzed.</span></span>|  
|<span data-ttu-id="b622e-180">Значение `Databases` для элемента `SQLServer`</span><span class="sxs-lookup"><span data-stu-id="b622e-180">`Databases` for `SQLServer` element</span></span>|<span data-ttu-id="b622e-181">Содержит список анализируемых баз данных.</span><span class="sxs-lookup"><span data-stu-id="b622e-181">Contains a list of databases to analyze.</span></span>|<span data-ttu-id="b622e-182">Необязательный один раз для каждого `SQLServer` элемента.</span><span class="sxs-lookup"><span data-stu-id="b622e-182">Optional once per `SQLServer` element.</span></span> <span data-ttu-id="b622e-183">Если этот элемент отсутствует, выполняется анализ всех баз данных на экземпляре.</span><span class="sxs-lookup"><span data-stu-id="b622e-183">If this element is not present, all databases in the instance are analyzed.</span></span>|  
|<span data-ttu-id="b622e-184">Значение `Database` для элемента `SQLServer`</span><span class="sxs-lookup"><span data-stu-id="b622e-184">`Database` for `SQLServer` element</span></span>|<span data-ttu-id="b622e-185">Задает имя базы данных для анализа.</span><span class="sxs-lookup"><span data-stu-id="b622e-185">Specifies the name of a database to analyze.</span></span>|<span data-ttu-id="b622e-186">Должен присутствовать не менее одного раза, если присутствует элемент `Databases`.</span><span class="sxs-lookup"><span data-stu-id="b622e-186">Required once or more if the `Databases` element is present.</span></span> <span data-ttu-id="b622e-187">Если элемент `Database` содержит значение «\*», будут проанализированы все базы данных в экземпляре.</span><span class="sxs-lookup"><span data-stu-id="b622e-187">If a `Database` element contains the value "\*", all databases in the instance are analyzed.</span></span> <span data-ttu-id="b622e-188">Значение по умолчанию отсутствует.</span><span class="sxs-lookup"><span data-stu-id="b622e-188">There is no default value.</span></span>|  
|`TraceFiles`|<span data-ttu-id="b622e-189">Содержит список анализируемых файлов трассировки.</span><span class="sxs-lookup"><span data-stu-id="b622e-189">Contains a list of trace files to analyze.</span></span>|<span data-ttu-id="b622e-190">Необязательный один раз для каждого `SQLServer` элемента.</span><span class="sxs-lookup"><span data-stu-id="b622e-190">Optional once per `SQLServer` element.</span></span>|  
|`TraceFile`|<span data-ttu-id="b622e-191">Задает путь и имя анализируемого файла трассировки.</span><span class="sxs-lookup"><span data-stu-id="b622e-191">Specifies the path and name of a trace file to analyze.</span></span>|<span data-ttu-id="b622e-192">Должен присутствовать не менее одного раза, если присутствует элемент `TraceFiles`.</span><span class="sxs-lookup"><span data-stu-id="b622e-192">Required once or more if the `TraceFiles` element is present.</span></span> <span data-ttu-id="b622e-193">Значение по умолчанию отсутствует.</span><span class="sxs-lookup"><span data-stu-id="b622e-193">There is no default value.</span></span>|  
|`BatchFiles`|<span data-ttu-id="b622e-194">Содержит список анализируемых пакетных файлов.</span><span class="sxs-lookup"><span data-stu-id="b622e-194">Contains a list of batch files to analyze.</span></span>|<span data-ttu-id="b622e-195">Необязательный один раз для каждого `SQLServer` элемента.</span><span class="sxs-lookup"><span data-stu-id="b622e-195">Optional once per `SQLServer` element.</span></span>|  
|`BatchFile`|<span data-ttu-id="b622e-196">Задает анализируемый пакетный файл.</span><span class="sxs-lookup"><span data-stu-id="b622e-196">Specifies a batch file to analyze.</span></span> <span data-ttu-id="b622e-197">Может быть указан несколько раз.</span><span class="sxs-lookup"><span data-stu-id="b622e-197">Can be multiple.</span></span>|<span data-ttu-id="b622e-198">Должен присутствовать не менее одного раза, если присутствует элемент `BatchFiles`.</span><span class="sxs-lookup"><span data-stu-id="b622e-198">Required once or more if the `BatchFiles` element is present.</span></span> <span data-ttu-id="b622e-199">Значение по умолчанию отсутствует.</span><span class="sxs-lookup"><span data-stu-id="b622e-199">There is no default value.</span></span>|  
|`BatchSeparator`|<span data-ttu-id="b622e-200">Задает разделитель пакетов, используемый в пакетных файлах [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b622e-200">Specifies the batch separator used in your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] batch files.</span></span>|<span data-ttu-id="b622e-201">Необязательный один раз для каждого `SQLServer` элемента.</span><span class="sxs-lookup"><span data-stu-id="b622e-201">Optional once per `SQLServer` element.</span></span> <span data-ttu-id="b622e-202">Значение по умолчанию — GO.</span><span class="sxs-lookup"><span data-stu-id="b622e-202">The default value is GO.</span></span>|  
|`AnalysisServices`|<span data-ttu-id="b622e-203">Содержит параметры анализа для служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b622e-203">Contains analysis settings for [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>|<span data-ttu-id="b622e-204">Может присутствовать один раз в каждом файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="b622e-204">Optional once per configuration file.</span></span> <span data-ttu-id="b622e-205">Если не задан, базы данных компонента служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] не анализируются.</span><span class="sxs-lookup"><span data-stu-id="b622e-205">If not specified, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] databases are not analyzed.</span></span>|  
|`ASInstance`|<span data-ttu-id="b622e-206">Задает имя экземпляра служб [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b622e-206">Specifies the name of an instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>|<span data-ttu-id="b622e-207">Требуется один раз на каждый элемент `AnalysisServices`.</span><span class="sxs-lookup"><span data-stu-id="b622e-207">Required once per `AnalysisServices` element.</span></span> <span data-ttu-id="b622e-208">Значение по умолчанию отсутствует.</span><span class="sxs-lookup"><span data-stu-id="b622e-208">There is no default value.</span></span>|  
|<span data-ttu-id="b622e-209">Значение `Databases` для элемента `Analysis Services`</span><span class="sxs-lookup"><span data-stu-id="b622e-209">`Databases` for `Analysis Services` element</span></span>|<span data-ttu-id="b622e-210">Содержит список анализируемых баз данных.</span><span class="sxs-lookup"><span data-stu-id="b622e-210">Contains a list of databases to analyze.</span></span>|<span data-ttu-id="b622e-211">Необязательный один раз для каждого `AnalysisServices` элемента.</span><span class="sxs-lookup"><span data-stu-id="b622e-211">Optional once per `AnalysisServices` element.</span></span> <span data-ttu-id="b622e-212">Если этот элемент отсутствует, выполняется анализ всех баз данных на экземпляре.</span><span class="sxs-lookup"><span data-stu-id="b622e-212">If this element is not present, all databases in the instance are analyzed.</span></span>|  
|<span data-ttu-id="b622e-213">Значение `Database` для элемента `AnalysisServices`</span><span class="sxs-lookup"><span data-stu-id="b622e-213">`Database` for `AnalysisServices` element</span></span>|<span data-ttu-id="b622e-214">Задает имя базы данных для анализа.</span><span class="sxs-lookup"><span data-stu-id="b622e-214">Specifies the name of a database to analyze.</span></span>|<span data-ttu-id="b622e-215">Должен присутствовать не менее одного раза, если присутствует элемент `Databases`.</span><span class="sxs-lookup"><span data-stu-id="b622e-215">Required once or more if the `Databases` element is present.</span></span> <span data-ttu-id="b622e-216">Если элемент `Database` содержит значение «\*», будут проанализированы все базы данных в экземпляре.</span><span class="sxs-lookup"><span data-stu-id="b622e-216">If a `Database` element contains the value "\*", all databases in the instance are analyzed.</span></span> <span data-ttu-id="b622e-217">Значение по умолчанию отсутствует.</span><span class="sxs-lookup"><span data-stu-id="b622e-217">There is no default value.</span></span>|  
|`ReportingServices`|<span data-ttu-id="b622e-218">Указывает, что будет запущен анализ служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b622e-218">Specifies to run analysis against [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span>|<span data-ttu-id="b622e-219">Может присутствовать один раз в каждом файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="b622e-219">Optional once per configuration file.</span></span> <span data-ttu-id="b622e-220">Если не указан, анализ служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] не выполняется.</span><span class="sxs-lookup"><span data-stu-id="b622e-220">If not specified, [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] is not analyzed.</span></span>|  
|`RSInstance`|<span data-ttu-id="b622e-221">Задает имя экземпляра служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b622e-221">Specifies the name of an instance of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span>|<span data-ttu-id="b622e-222">Требуется один раз на каждый элемент `ReportingServices`.</span><span class="sxs-lookup"><span data-stu-id="b622e-222">Required once per `ReportingServices` element.</span></span> <span data-ttu-id="b622e-223">Значение по умолчанию отсутствует.</span><span class="sxs-lookup"><span data-stu-id="b622e-223">There is no default value.</span></span>|  
|`IntegrationServices`|<span data-ttu-id="b622e-224">Содержит параметры анализа для служб [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b622e-224">Contains analysis settings for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span></span>|<span data-ttu-id="b622e-225">Может присутствовать один раз в каждом файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="b622e-225">Optional once per configuration file.</span></span> <span data-ttu-id="b622e-226">Если не указан, анализ служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] не выполняется.</span><span class="sxs-lookup"><span data-stu-id="b622e-226">If not specified, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] is not analyzed.</span></span>|  
|`PackagePath`|<span data-ttu-id="b622e-227">Задает путь к набору пакетов служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b622e-227">Specifies the path of a set of [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages.</span></span>|<span data-ttu-id="b622e-228">Необязательный один раз для каждого `IntegrationServices` элемента.</span><span class="sxs-lookup"><span data-stu-id="b622e-228">Optional once per `IntegrationServices` element.</span></span> <span data-ttu-id="b622e-229">Если этот элемент отсутствует, будет выполнен анализ экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], а пакеты, хранящиеся вне экземпляра, анализироваться не будут.</span><span class="sxs-lookup"><span data-stu-id="b622e-229">If this element is not present, analysis occurs on the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance, and no externally stored packages are analyzed.</span></span> <span data-ttu-id="b622e-230">Значение по умолчанию отсутствует.</span><span class="sxs-lookup"><span data-stu-id="b622e-230">There is no default value.</span></span>|  
  
## <a name="examples"></a><span data-ttu-id="b622e-231">Примеры</span><span class="sxs-lookup"><span data-stu-id="b622e-231">Examples</span></span>  
  
### <a name="a-run-upgrade-advisor-using-a-configuration-file"></a><span data-ttu-id="b622e-232">A.</span><span class="sxs-lookup"><span data-stu-id="b622e-232">A.</span></span> <span data-ttu-id="b622e-233">Запуск помощника по обновлению с помощью файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="b622e-233">Run Upgrade Advisor Using a Configuration File</span></span>  
 <span data-ttu-id="b622e-234">В следующем примере показано, как запустить помощник по обновлению из командной строки с использованием файла конфигурации, в котором определена область анализа.</span><span class="sxs-lookup"><span data-stu-id="b622e-234">The following example shows how to run Upgrade Advisor from the command prompt by using a configuration file that specifies what to analyze.</span></span> <span data-ttu-id="b622e-235">Для соединения с [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] в данном примере используется проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="b622e-235">This example uses Windows Authentication to connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
```  
UpgradeAdvisorWizardCmd -ConfigFile "C:\My Documents\UpgradeConfig1.xml"  
```  
  
### <a name="b-run-upgrade-advisor-using-default-configuration-settings"></a><span data-ttu-id="b622e-236">Б.</span><span class="sxs-lookup"><span data-stu-id="b622e-236">B.</span></span> <span data-ttu-id="b622e-237">Запуск помощника по обновлению с помощью настроек конфигурации, установленных по умолчанию</span><span class="sxs-lookup"><span data-stu-id="b622e-237">Run Upgrade Advisor Using Default Configuration Settings</span></span>  
 <span data-ttu-id="b622e-238">В следующем примере показано, как запустить помощник по обновлению из командной строки, используя параметры конфигурации по умолчанию и проверку подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="b622e-238">The following example shows how to run Upgrade Advisor from the command prompt by using default configuration settings and Windows Authentication.</span></span>  
  
```  
UpgradeAdvisorWizardCmd -Server MyServer -Instance MyInst   
```  
  
### <a name="c-run-upgrade-advisor-using-ssnoversion-authentication"></a><span data-ttu-id="b622e-239">В.</span><span class="sxs-lookup"><span data-stu-id="b622e-239">C.</span></span> <span data-ttu-id="b622e-240">Запуск помощника по обновлению с помощью проверки подлинности [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b622e-240">Run Upgrade Advisor Using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication</span></span>  
 <span data-ttu-id="b622e-241">В следующем примере показано, как запустить помощник по обновлению из командной строки с использованием файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="b622e-241">The following example shows how to run Upgrade Advisor from the command prompt by using a configuration file.</span></span> <span data-ttu-id="b622e-242">В примере указывается имя пользователя и пароль [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] для подключения к экземпляру [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b622e-242">This example specifies a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] user name and password to connect to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
```  
UpgradeAdvisorWizardCmd -ConfigFile "C:\My Documents\UpgradeConfig1.xml"   
    -SqlUser "MyUserName" -SqlPassword "QweRTy-55"  
```  
  
## <a name="see-also"></a><span data-ttu-id="b622e-243">См. также:</span><span class="sxs-lookup"><span data-stu-id="b622e-243">See Also</span></span>  
 <span data-ttu-id="b622e-244">[Устранение проблем с обновлением](../../../2014/sql-server/install/resolving-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="b622e-244">[Resolving Upgrade Issues](../../../2014/sql-server/install/resolving-upgrade-issues.md) </span></span>  
 <span data-ttu-id="b622e-245">[Работа с советником по переходу](../../../2014/sql-server/install/working-with-upgrade-advisor.md) </span><span class="sxs-lookup"><span data-stu-id="b622e-245">[Working with Upgrade Advisor](../../../2014/sql-server/install/working-with-upgrade-advisor.md) </span></span>  
 [<span data-ttu-id="b622e-246">Запуск помощника по обновлению &#40;пользовательского интерфейса&#41;</span><span class="sxs-lookup"><span data-stu-id="b622e-246">Running Upgrade Advisor &#40;User Interface&#41;</span></span>](../../../2014/sql-server/install/running-upgrade-advisor-user-interface.md)  
  
  