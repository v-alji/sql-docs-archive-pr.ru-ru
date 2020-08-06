---
title: Справочник по пользовательскому интерфейсу мастера настройки пакета | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.configwizard.selectobjects.f1
- sql12.dts.configwizard.selecconfigtype.f1
- sql12.dts.configwizard.finishdtsconfiguration.f1
- sql12.dts.configwizard.welcome.f1
ms.assetid: adca6938-6d5a-40ec-950e-dceb79d044fe
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 222c5f58ca4e942dd23909b433ab346c500fceed
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667803"
---
# <a name="package-configuration-wizard-ui-reference"></a><span data-ttu-id="2e894-102">Мастер конфигурации пакетов справочника по пользовательскому интерфейсу</span><span class="sxs-lookup"><span data-stu-id="2e894-102">Package Configuration Wizard UI Reference</span></span>
  <span data-ttu-id="2e894-103">**Мастер настройки пакета** используется для создания конфигураций, обновляющих свойства пакета служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] и его объекты во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="2e894-103">Use the **Package Configuration Wizard** to create configurations that update the properties of an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package and its objects at run time.</span></span> <span data-ttu-id="2e894-104">Мастер запускается при добавлении новой конфигурации или изменении существующей в диалоговом окне **Организатор конфигураций пакетов** .</span><span class="sxs-lookup"><span data-stu-id="2e894-104">This wizard runs when you add a new configuration or modify an existing one in the **Package Configurations Organizer** dialog box.</span></span> <span data-ttu-id="2e894-105">Для открытия диалогового окна **Организатор конфигураций пакетов** выберите пункт **Конфигурации пакета** в меню **службы SSIS** в среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2e894-105">To open the **Package Configurations Organizer** dialog box, select **Package Configurations** on the **SSIS** menu in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="2e894-106">Дополнительные сведения см. в разделе [Создание конфигурации пакетов](../../2014/integration-services/create-package-configurations.md).</span><span class="sxs-lookup"><span data-stu-id="2e894-106">For more information, see [Create Package Configurations](../../2014/integration-services/create-package-configurations.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2e894-107">Доступны конфигурации для модели развертывания пакетов.</span><span class="sxs-lookup"><span data-stu-id="2e894-107">Configurations are available for the package deployment model.</span></span> <span data-ttu-id="2e894-108">Для моделей развертывания проектов вместо конфигураций используются параметры.</span><span class="sxs-lookup"><span data-stu-id="2e894-108">Parameters are used in place of configurations for the project deployment model.</span></span> <span data-ttu-id="2e894-109">Модель развертывания проектов позволяет развертывать проекты служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] на сервере служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2e894-109">The project deployment model enables you to deploy [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] projects to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] server.</span></span> <span data-ttu-id="2e894-110">Дополнительные сведения о моделях развертывания см. в разделе [Deployment of Projects and Packages](packages/deploy-integration-services-ssis-projects-and-packages.md).</span><span class="sxs-lookup"><span data-stu-id="2e894-110">For more information about the deployment models, see [Deployment of Projects and Packages](packages/deploy-integration-services-ssis-projects-and-packages.md).</span></span>  
  
 <span data-ttu-id="2e894-111">В следующих разделах описаны страницы мастера.</span><span class="sxs-lookup"><span data-stu-id="2e894-111">The following sections describe pages of the Wizard.</span></span>  
  
## <a name="welcome-to-the-package-configuration-wizard-page"></a><span data-ttu-id="2e894-112">Страница приветствия мастера настройки пакета</span><span class="sxs-lookup"><span data-stu-id="2e894-112">Welcome to the Package Configuration Wizard Page</span></span>  
 <span data-ttu-id="2e894-113">**Мастер настройки служб SSIS** используется для создания конфигураций, обновляющих свойства пакета и его объекты во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="2e894-113">Use the **SSIS Configuration Wizard** to create configurations that update the properties of a package and its objects at run time.</span></span>  
  
### <a name="options"></a><span data-ttu-id="2e894-114">Параметры</span><span class="sxs-lookup"><span data-stu-id="2e894-114">Options</span></span>  
 <span data-ttu-id="2e894-115">**Больше не показывать это окно**</span><span class="sxs-lookup"><span data-stu-id="2e894-115">**Don't show this page again**</span></span>  
 <span data-ttu-id="2e894-116">Пропустить страницу приветствия при следующем запуске мастера.</span><span class="sxs-lookup"><span data-stu-id="2e894-116">Skip the welcome page the next time you open the wizard.</span></span>  
  
 <span data-ttu-id="2e894-117">**Дальше**</span><span class="sxs-lookup"><span data-stu-id="2e894-117">**Next**</span></span>  
 <span data-ttu-id="2e894-118">Перейти на следующую страницу мастера.</span><span class="sxs-lookup"><span data-stu-id="2e894-118">Go the next page in the wizard.</span></span>  
  
## <a name="select-configuration-type-page"></a><span data-ttu-id="2e894-119">Страница «Выбор типа конфигурации»</span><span class="sxs-lookup"><span data-stu-id="2e894-119">Select Configuration Type Page</span></span>  
 <span data-ttu-id="2e894-120">Страница **Выбор типа конфигурации** позволяет указать тип создаваемой конфигурации.</span><span class="sxs-lookup"><span data-stu-id="2e894-120">Use the **Select Configuration Type** page to specify the type of configuration to create.</span></span>  
  
 <span data-ttu-id="2e894-121">Если требуются дополнительные сведения для определения того, какой тип конфигурации должен использоваться, см. раздел [Package Configurations](../../2014/integration-services/package-configurations.md).</span><span class="sxs-lookup"><span data-stu-id="2e894-121">If you need additional information to determine which type of configuration to use, see [Package Configurations](../../2014/integration-services/package-configurations.md).</span></span>  
  
### <a name="static-options"></a><span data-ttu-id="2e894-122">Статические параметры</span><span class="sxs-lookup"><span data-stu-id="2e894-122">Static Options</span></span>  
 <span data-ttu-id="2e894-123">**Тип конфигурации**</span><span class="sxs-lookup"><span data-stu-id="2e894-123">**Configuration type**</span></span>  
 <span data-ttu-id="2e894-124">С помощью следующих параметров выберите тип источника, в котором будет храниться конфигурация:</span><span class="sxs-lookup"><span data-stu-id="2e894-124">Select the type of source in which to store the configuration, using the following options:</span></span>  
  
|<span data-ttu-id="2e894-125">Значение</span><span class="sxs-lookup"><span data-stu-id="2e894-125">Value</span></span>|<span data-ttu-id="2e894-126">Описание</span><span class="sxs-lookup"><span data-stu-id="2e894-126">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2e894-127">**XML-файл конфигурации**</span><span class="sxs-lookup"><span data-stu-id="2e894-127">**XML configuration file**</span></span>|<span data-ttu-id="2e894-128">Конфигурация хранится в виде XML-файла.</span><span class="sxs-lookup"><span data-stu-id="2e894-128">Store the configuration as an XML file.</span></span> <span data-ttu-id="2e894-129">При выборе этого значения отображаются динамические параметры в данном разделе, **Тип конфигурации**.</span><span class="sxs-lookup"><span data-stu-id="2e894-129">Selecting this value displays the dynamic options in the section, **Configuration Type**.</span></span>|  
|<span data-ttu-id="2e894-130">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="2e894-130">**Environment variable**</span></span>|<span data-ttu-id="2e894-131">Конфигурация хранится в одной из переменных среды.</span><span class="sxs-lookup"><span data-stu-id="2e894-131">Store the configuration in one of the environment variables.</span></span> <span data-ttu-id="2e894-132">При выборе этого значения отображаются динамические параметры в данном разделе, **Тип конфигурации**.</span><span class="sxs-lookup"><span data-stu-id="2e894-132">Selecting this value displays the dynamic options in the section, **Configuration Type**.</span></span>|  
|<span data-ttu-id="2e894-133">**Параметр реестра**</span><span class="sxs-lookup"><span data-stu-id="2e894-133">**Registry entry**</span></span>|<span data-ttu-id="2e894-134">Храните конфигурацию в реестре.</span><span class="sxs-lookup"><span data-stu-id="2e894-134">Store the configuration in the Registry.</span></span> <span data-ttu-id="2e894-135">При выборе этого значения отображаются динамические параметры в данном разделе, **Тип конфигурации**.</span><span class="sxs-lookup"><span data-stu-id="2e894-135">Selecting this value displays the dynamic options in the section, **Configuration Type**.</span></span>|  
|<span data-ttu-id="2e894-136">**Переменная родительского пакета**</span><span class="sxs-lookup"><span data-stu-id="2e894-136">**Parent package variable**</span></span>|<span data-ttu-id="2e894-137">Конфигурация хранится в переменной пакета, который содержит задачу.</span><span class="sxs-lookup"><span data-stu-id="2e894-137">Store the configuration as a variable in the package that contains the task.</span></span>  <span data-ttu-id="2e894-138">При выборе этого значения отображаются динамические параметры в данном разделе, **Тип конфигурации**.</span><span class="sxs-lookup"><span data-stu-id="2e894-138">Selecting this value displays the dynamic options in the section, **Configuration Type**.</span></span>|  
|<span data-ttu-id="2e894-139">**SQL Server**</span><span class="sxs-lookup"><span data-stu-id="2e894-139">**SQL Server**</span></span>|<span data-ttu-id="2e894-140">Конфигурация хранится в таблице [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2e894-140">Store the configuration in a table in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="2e894-141">При выборе этого значения отображаются динамические параметры в данном разделе, **Тип конфигурации**.</span><span class="sxs-lookup"><span data-stu-id="2e894-141">Selecting this value displays the dynamic options in the section, **Configuration Type**.</span></span>|  
  
 <span data-ttu-id="2e894-142">**Дальше**</span><span class="sxs-lookup"><span data-stu-id="2e894-142">**Next**</span></span>  
 <span data-ttu-id="2e894-143">Позволяет перейти к следующей странице мастера.</span><span class="sxs-lookup"><span data-stu-id="2e894-143">View the next page in the wizard sequence.</span></span>  
  
### <a name="dynamic-options"></a><span data-ttu-id="2e894-144">Динамические параметры</span><span class="sxs-lookup"><span data-stu-id="2e894-144">Dynamic Options</span></span>  
  
#### <a name="configuration-type-option--xml-configuration-file"></a><span data-ttu-id="2e894-145">Тип конфигурации — XML-файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="2e894-145">Configuration Type Option = XML Configuration File</span></span>  
 <span data-ttu-id="2e894-146">**Указать параметры конфигурации непосредственно**</span><span class="sxs-lookup"><span data-stu-id="2e894-146">**Specify configuration settings directly**</span></span>  
 <span data-ttu-id="2e894-147">Позволяет непосредственно указать параметры конфигурации.</span><span class="sxs-lookup"><span data-stu-id="2e894-147">Use to specify settings directly.</span></span>  
  
|<span data-ttu-id="2e894-148">Значение</span><span class="sxs-lookup"><span data-stu-id="2e894-148">Value</span></span>|<span data-ttu-id="2e894-149">Описание</span><span class="sxs-lookup"><span data-stu-id="2e894-149">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2e894-150">**Имя файла конфигурации**</span><span class="sxs-lookup"><span data-stu-id="2e894-150">**Configuration file name**</span></span>|<span data-ttu-id="2e894-151">Введите путь к файлу конфигурации, сформированному мастером.</span><span class="sxs-lookup"><span data-stu-id="2e894-151">Type the path of the configuration file that the wizard generates.</span></span>|  
|<span data-ttu-id="2e894-152">**Обзор**</span><span class="sxs-lookup"><span data-stu-id="2e894-152">**Browse**</span></span>|<span data-ttu-id="2e894-153">Диалоговое окно **Выбор расположения файла конфигурации** позволяет указать путь к файлу конфигурации, сформированному мастером.</span><span class="sxs-lookup"><span data-stu-id="2e894-153">Use the **Select Configuration File Location** dialog box to specify the path of the configuration file that the wizard generates.</span></span> <span data-ttu-id="2e894-154">Если файл отсутствует, мастер создает его.</span><span class="sxs-lookup"><span data-stu-id="2e894-154">If the file does not exist, it is created by the wizard.</span></span>|  
  
 <span data-ttu-id="2e894-155">**Сведения о расположении файла конфигурации хранятся в переменной среды**</span><span class="sxs-lookup"><span data-stu-id="2e894-155">**Configuration location is stored in an environment variable**</span></span>  
 <span data-ttu-id="2e894-156">Позволяет указать переменную среды, в которую записывается конфигурация.</span><span class="sxs-lookup"><span data-stu-id="2e894-156">Use to specify the environment variable in which to store the configuration.</span></span>  
  
|<span data-ttu-id="2e894-157">Значение</span><span class="sxs-lookup"><span data-stu-id="2e894-157">Value</span></span>|<span data-ttu-id="2e894-158">Описание</span><span class="sxs-lookup"><span data-stu-id="2e894-158">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2e894-159">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="2e894-159">**Environment variable**</span></span>|<span data-ttu-id="2e894-160">Выберите переменную среды из списка.</span><span class="sxs-lookup"><span data-stu-id="2e894-160">Select an environment variable from the list.</span></span>|  
  
#### <a name="configuration-type-option--environment-variable"></a><span data-ttu-id="2e894-161">Тип конфигурации — переменная среды</span><span class="sxs-lookup"><span data-stu-id="2e894-161">Configuration Type Option = Environment Variable</span></span>  
 <span data-ttu-id="2e894-162">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="2e894-162">**Environment variable**</span></span>  
 <span data-ttu-id="2e894-163">Выберите переменную среды, которая содержит сведения о конфигурации.</span><span class="sxs-lookup"><span data-stu-id="2e894-163">Select the environment variable that contains the configuration information.</span></span>  
  
#### <a name="configuration-type-option--registry-entry"></a><span data-ttu-id="2e894-164">Тип конфигурации — запись реестра</span><span class="sxs-lookup"><span data-stu-id="2e894-164">Configuration Type Option = Registry Entry</span></span>  
 <span data-ttu-id="2e894-165">**Указать параметры конфигурации непосредственно**</span><span class="sxs-lookup"><span data-stu-id="2e894-165">**Specify configuration settings directly**</span></span>  
 <span data-ttu-id="2e894-166">Позволяет непосредственно указать параметры конфигурации.</span><span class="sxs-lookup"><span data-stu-id="2e894-166">Use to specify settings directly.</span></span>  
  
|<span data-ttu-id="2e894-167">Значение</span><span class="sxs-lookup"><span data-stu-id="2e894-167">Value</span></span>|<span data-ttu-id="2e894-168">Описание</span><span class="sxs-lookup"><span data-stu-id="2e894-168">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2e894-169">**Параметр реестра**</span><span class="sxs-lookup"><span data-stu-id="2e894-169">**Registry entry**</span></span>|<span data-ttu-id="2e894-170">Введите раздел реестра, который содержит сведения о конфигурации.</span><span class="sxs-lookup"><span data-stu-id="2e894-170">Type the Registry key that contains the configuration information.</span></span> <span data-ttu-id="2e894-171">Формат — \<registry key>.</span><span class="sxs-lookup"><span data-stu-id="2e894-171">The format is \<registry key>.</span></span><br /><br /> <span data-ttu-id="2e894-172">Этот раздел реестра должен уже существовать в кусте HKEY_CURRENT_USER и иметь значение с именем Value.</span><span class="sxs-lookup"><span data-stu-id="2e894-172">The Registry key must already exist in HKEY_CURRENT_USER and have a value named Value.</span></span> <span data-ttu-id="2e894-173">Значение может иметь строковый тип или тип DWORD.</span><span class="sxs-lookup"><span data-stu-id="2e894-173">The value can be a DWORD or a string.</span></span><br /><br /> <span data-ttu-id="2e894-174">Если есть необходимость применить раздел реестра, не находящийся в корне куста HKEY_CURRENT_USER, используйте для указания этого раздела формат \<Registry key\registry key\\...>.</span><span class="sxs-lookup"><span data-stu-id="2e894-174">If you want to use a Registry key is not at the root of HKEY_CURRENT_USER, use the format \<Registry key\registry key\\...> to identify the key.</span></span>|  
  
 <span data-ttu-id="2e894-175">**Сведения о расположении файла конфигурации хранятся в переменной среды**</span><span class="sxs-lookup"><span data-stu-id="2e894-175">**Configuration location is stored in an environment variable**</span></span>  
 <span data-ttu-id="2e894-176">Позволяет указать переменную среды, в которую записывается конфигурация.</span><span class="sxs-lookup"><span data-stu-id="2e894-176">Use to specify the environment variable to store the configuration in.</span></span>  
  
|<span data-ttu-id="2e894-177">Значение</span><span class="sxs-lookup"><span data-stu-id="2e894-177">Value</span></span>|<span data-ttu-id="2e894-178">Описание</span><span class="sxs-lookup"><span data-stu-id="2e894-178">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2e894-179">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="2e894-179">**Environment variable**</span></span>|<span data-ttu-id="2e894-180">Выберите переменную среды из списка.</span><span class="sxs-lookup"><span data-stu-id="2e894-180">Select an environment variable from the list.</span></span>|  
  
#### <a name="configuration-type-option--parent-package-variable"></a><span data-ttu-id="2e894-181">Тип конфигурации — переменная родительского пакета</span><span class="sxs-lookup"><span data-stu-id="2e894-181">Configuration Type Option = Parent Package Variable</span></span>  
 <span data-ttu-id="2e894-182">**Указать параметры конфигурации непосредственно**</span><span class="sxs-lookup"><span data-stu-id="2e894-182">**Specify configuration settings directly**</span></span>  
 <span data-ttu-id="2e894-183">Позволяет непосредственно указать параметры конфигурации.</span><span class="sxs-lookup"><span data-stu-id="2e894-183">Use to specify settings directly.</span></span>  
  
|<span data-ttu-id="2e894-184">Значение</span><span class="sxs-lookup"><span data-stu-id="2e894-184">Value</span></span>|<span data-ttu-id="2e894-185">Описание</span><span class="sxs-lookup"><span data-stu-id="2e894-185">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2e894-186">**Родительская переменная**</span><span class="sxs-lookup"><span data-stu-id="2e894-186">**Parent variable**</span></span>|<span data-ttu-id="2e894-187">Укажите переменную родительского пакета, которая содержит сведения о конфигурации.</span><span class="sxs-lookup"><span data-stu-id="2e894-187">Specify the variable in the parent package that contains the configuration information.</span></span>|  
  
 <span data-ttu-id="2e894-188">**Сведения о расположении файла конфигурации хранятся в переменной среды**</span><span class="sxs-lookup"><span data-stu-id="2e894-188">**Configuration location is stored in an environment variable**</span></span>  
 <span data-ttu-id="2e894-189">Позволяет указать переменную среды, в которой хранится конфигурация.</span><span class="sxs-lookup"><span data-stu-id="2e894-189">Use to specify the environment variable that stores the configuration.</span></span>  
  
|<span data-ttu-id="2e894-190">Значение</span><span class="sxs-lookup"><span data-stu-id="2e894-190">Value</span></span>|<span data-ttu-id="2e894-191">Описание</span><span class="sxs-lookup"><span data-stu-id="2e894-191">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2e894-192">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="2e894-192">**Environment variable**</span></span>|<span data-ttu-id="2e894-193">Выберите переменную среды из списка.</span><span class="sxs-lookup"><span data-stu-id="2e894-193">Select an environment variable from the list.</span></span>|  
  
#### <a name="configuration-type-options--sql-server"></a><span data-ttu-id="2e894-194">Тип конфигурации — SQL Server</span><span class="sxs-lookup"><span data-stu-id="2e894-194">Configuration Type Options = SQL Server</span></span>  
 <span data-ttu-id="2e894-195">**Указать параметры конфигурации непосредственно**</span><span class="sxs-lookup"><span data-stu-id="2e894-195">**Specify configuration settings directly**</span></span>  
 <span data-ttu-id="2e894-196">Позволяет непосредственно указать параметры конфигурации.</span><span class="sxs-lookup"><span data-stu-id="2e894-196">Use to specify settings directly.</span></span>  
  
|<span data-ttu-id="2e894-197">Значение</span><span class="sxs-lookup"><span data-stu-id="2e894-197">Value</span></span>|<span data-ttu-id="2e894-198">Описание</span><span class="sxs-lookup"><span data-stu-id="2e894-198">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2e894-199">**Соединение**</span><span class="sxs-lookup"><span data-stu-id="2e894-199">**Connection**</span></span>|<span data-ttu-id="2e894-200">Выберите соединение из списка или нажмите **Создать** , чтобы создать новое соединение.</span><span class="sxs-lookup"><span data-stu-id="2e894-200">Select a connection from the list, or click **New** to create a new connection.</span></span>|  
|<span data-ttu-id="2e894-201">**Таблица конфигурации**</span><span class="sxs-lookup"><span data-stu-id="2e894-201">**Configuration table**</span></span>|<span data-ttu-id="2e894-202">Выберите существующую таблицу или нажмите кнопку **Создать** , чтобы ввести инструкцию SQL, создающую новую таблицу.</span><span class="sxs-lookup"><span data-stu-id="2e894-202">Select an existing table, or click **New** to write a SQL statement that creates a new table.</span></span>|  
|<span data-ttu-id="2e894-203">**Фильтр конфигурации**</span><span class="sxs-lookup"><span data-stu-id="2e894-203">**Configuration filter**</span></span>|<span data-ttu-id="2e894-204">Выберите существующее имя конфигурации или введите новое.</span><span class="sxs-lookup"><span data-stu-id="2e894-204">Select an existing configuration name or type a new name.</span></span><br /><br /> <span data-ttu-id="2e894-205">В одной и той же таблице можно хранить целый ряд конфигураций SQL Server, причем каждая конфигурация может включать множество элементов конфигурации.</span><span class="sxs-lookup"><span data-stu-id="2e894-205">Many SQL Server configurations can be stored in the same table, and each configuration can include multiple configuration items.</span></span><br /><br /> <span data-ttu-id="2e894-206">Это определяемое пользователем значение хранится в таблице, что позволяет обозначать элементы конфигурации, принадлежащие к конкретной конфигурации</span><span class="sxs-lookup"><span data-stu-id="2e894-206">This user-defined value is stored in the table to identify configuration items that belong to a particular configuration</span></span>|  
  
 <span data-ttu-id="2e894-207">**Сведения о расположении файла конфигурации хранятся в переменной среды**</span><span class="sxs-lookup"><span data-stu-id="2e894-207">**Configuration location is stored in an environment variable**</span></span>  
 <span data-ttu-id="2e894-208">Позволяет указать переменную среды, в которой хранится конфигурация.</span><span class="sxs-lookup"><span data-stu-id="2e894-208">Use to specify the environment variable where the configuration is stored.</span></span>  
  
|<span data-ttu-id="2e894-209">Значение</span><span class="sxs-lookup"><span data-stu-id="2e894-209">Value</span></span>|<span data-ttu-id="2e894-210">Описание</span><span class="sxs-lookup"><span data-stu-id="2e894-210">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2e894-211">**Переменная среды**</span><span class="sxs-lookup"><span data-stu-id="2e894-211">**Environment variable**</span></span>|<span data-ttu-id="2e894-212">Выберите переменную среды из списка.</span><span class="sxs-lookup"><span data-stu-id="2e894-212">Select an environment variable from the list.</span></span>|  
  
## <a name="select-objects-to-export-page"></a><span data-ttu-id="2e894-213">Страница «Выбор объектов для экспорта»</span><span class="sxs-lookup"><span data-stu-id="2e894-213">Select Objects to Export Page</span></span>  
 <span data-ttu-id="2e894-214">Страница **Выбор целевого свойства или свойств для экспорта** используется для указания свойств объекта, включенного в конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="2e894-214">Use the **Select Target Property or Select Properties to Export** page to specify the object properties that the configuration contains.</span></span> <span data-ttu-id="2e894-215">Возможность выбора нескольких свойств доступна только в случае выбора типа конфигурации XML.</span><span class="sxs-lookup"><span data-stu-id="2e894-215">The ability to select multiple properties is available only if you select the XML configuration type.</span></span>  
  
### <a name="options"></a><span data-ttu-id="2e894-216">Параметры</span><span class="sxs-lookup"><span data-stu-id="2e894-216">Options</span></span>  
 <span data-ttu-id="2e894-217">**Объекты**</span><span class="sxs-lookup"><span data-stu-id="2e894-217">**Objects**</span></span>  
 <span data-ttu-id="2e894-218">Позволяет раскрывать иерархию пакетов и выбирать свойства для экспорта.</span><span class="sxs-lookup"><span data-stu-id="2e894-218">Expand the package hierarchy and select the properties to export.</span></span>  
  
 <span data-ttu-id="2e894-219">**Атрибуты свойства**</span><span class="sxs-lookup"><span data-stu-id="2e894-219">**Property attributes**</span></span>  
 <span data-ttu-id="2e894-220">Позволяет просматривать атрибуты свойства.</span><span class="sxs-lookup"><span data-stu-id="2e894-220">View the attributes of a property.</span></span>  
  
 <span data-ttu-id="2e894-221">**Дальше**</span><span class="sxs-lookup"><span data-stu-id="2e894-221">**Next**</span></span>  
 <span data-ttu-id="2e894-222">Перейдите на следующую страницу мастера.</span><span class="sxs-lookup"><span data-stu-id="2e894-222">Go to the next page in the wizard.</span></span>  
  
## <a name="completing-the-wizard-page"></a><span data-ttu-id="2e894-223">Страница «Завершение работы мастера»</span><span class="sxs-lookup"><span data-stu-id="2e894-223">Completing the Wizard Page</span></span>  
 <span data-ttu-id="2e894-224">Используйте страницу **Завершение работы мастера** , чтобы задать имя конфигурации и просмотреть параметры настройки, используемые мастером при создании конфигурации.</span><span class="sxs-lookup"><span data-stu-id="2e894-224">Use the **Completing the Wizard** page to provide a name for the configuration and view settings used by the wizard to create the configuration.</span></span> <span data-ttu-id="2e894-225">После завершения работы мастера отображается в **Организаторе конфигураций пакетов** , который перечисляет все настройки для пакета.</span><span class="sxs-lookup"><span data-stu-id="2e894-225">After the wizard completes, the **Package Configurations Organizer** is displayed, which lists all configurations for the package.</span></span>  
  
### <a name="options"></a><span data-ttu-id="2e894-226">Параметры</span><span class="sxs-lookup"><span data-stu-id="2e894-226">Options</span></span>  
 <span data-ttu-id="2e894-227">**Имя конфигурации**</span><span class="sxs-lookup"><span data-stu-id="2e894-227">**Configuration name**</span></span>  
 <span data-ttu-id="2e894-228">Введите имя конфигурации.</span><span class="sxs-lookup"><span data-stu-id="2e894-228">Type the name of the configuration.</span></span>  
  
 <span data-ttu-id="2e894-229">**Предварительный просмотр**</span><span class="sxs-lookup"><span data-stu-id="2e894-229">**Preview**</span></span>  
 <span data-ttu-id="2e894-230">Просмотр параметров настройки, используемых мастером для создания конфигурации.</span><span class="sxs-lookup"><span data-stu-id="2e894-230">View the settings used by the wizard to create the configuration.</span></span>  
  
 <span data-ttu-id="2e894-231">**Готово**</span><span class="sxs-lookup"><span data-stu-id="2e894-231">**Finish**</span></span>  
 <span data-ttu-id="2e894-232">Создайте конфигурацию и выйдите из **мастера настройки пакета**.</span><span class="sxs-lookup"><span data-stu-id="2e894-232">Create the configuration and exit the **Package Configuration Wizard**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e894-233">См. также:</span><span class="sxs-lookup"><span data-stu-id="2e894-233">See Also</span></span>  
 [<span data-ttu-id="2e894-234">Создание конфигурации пакетов</span><span class="sxs-lookup"><span data-stu-id="2e894-234">Create Package Configurations</span></span>](../../2014/integration-services/create-package-configurations.md)  
  
  
