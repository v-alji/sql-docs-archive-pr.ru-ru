---
title: Конфигурации пакетов | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- package configuration syntax [Integration Services]
- SQL Server Integration Services packages, configurations
- SSIS packages, configurations
- XML [Integration Services]
- Integration Services packages, configurations
- configuration syntax [Integration Services]
- indirect configurations [Integration Services]
- configurations [Integration Services]
- direct configurations [Integration Services]
- packages [Integration Services], configurations
ms.assetid: d20e0311-1fc9-4ddc-a381-6d127cf11b69
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0d22dbfedcf4cf7084e1667586f9774926f3b2a2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668995"
---
# <a name="package-configurations"></a><span data-ttu-id="35b0e-102">Конфигурации пакетов</span><span class="sxs-lookup"><span data-stu-id="35b0e-102">Package Configurations</span></span>
  <span data-ttu-id="35b0e-103">Службы [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] содержат конфигурацию пакетов, которую можно использовать для обновления значений свойств во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="35b0e-103">[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] provides package configurations that you can use to update the values of properties at run time.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="35b0e-104">Доступны конфигурации для модели развертывания пакетов.</span><span class="sxs-lookup"><span data-stu-id="35b0e-104">Configurations are available for the package deployment model.</span></span> <span data-ttu-id="35b0e-105">Для моделей развертывания проектов вместо конфигураций используются параметры.</span><span class="sxs-lookup"><span data-stu-id="35b0e-105">Parameters are used in place of configurations for the project deployment model.</span></span> <span data-ttu-id="35b0e-106">Модель развертывания проектов позволяет развертывать проекты служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] на сервере служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="35b0e-106">The project deployment model enables you to deploy [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] projects to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] server.</span></span> <span data-ttu-id="35b0e-107">Дополнительные сведения о моделях развертывания см. в разделе [Deployment of Projects and Packages](packages/deploy-integration-services-ssis-projects-and-packages.md).</span><span class="sxs-lookup"><span data-stu-id="35b0e-107">For more information about the deployment models, see [Deployment of Projects and Packages](packages/deploy-integration-services-ssis-projects-and-packages.md).</span></span>  
  
 <span data-ttu-id="35b0e-108">Конфигурация представляет собой пару вида «свойство-значение», которая добавляется к завершенному пакету.</span><span class="sxs-lookup"><span data-stu-id="35b0e-108">A configuration is a property/value pair that you add to a completed package.</span></span> <span data-ttu-id="35b0e-109">Обычно свойства пакета устанавливаются в объектах пакета во время его разработки, а затем к пакету добавляется конфигурация.</span><span class="sxs-lookup"><span data-stu-id="35b0e-109">Typically, you create a package set properties on the package objects during package development, and then add the configuration to the package.</span></span> <span data-ttu-id="35b0e-110">При выполнении пакета он получает новые значения свойств из конфигурации.</span><span class="sxs-lookup"><span data-stu-id="35b0e-110">When the package runs, it gets the new values of the property from the configuration.</span></span> <span data-ttu-id="35b0e-111">Например, с помощью конфигурации можно изменить строку соединения в диспетчере соединений или обновить значение переменной.</span><span class="sxs-lookup"><span data-stu-id="35b0e-111">For example, by using a configuration, you can change the connection string of a connection manager, or update the value of a variable.</span></span>  
  
 <span data-ttu-id="35b0e-112">Конфигурации пакета дают следующие преимущества.</span><span class="sxs-lookup"><span data-stu-id="35b0e-112">Package configurations provide the following benefits:</span></span>  
  
-   <span data-ttu-id="35b0e-113">Конфигурации облегчают перенос пакетов из среды разработки в рабочую среду.</span><span class="sxs-lookup"><span data-stu-id="35b0e-113">Configurations make it easier to move packages from a development environment to a production environment.</span></span> <span data-ttu-id="35b0e-114">Например, конфигурация может обновить путь к исходному файлу или изменить имя базы данных или сервера.</span><span class="sxs-lookup"><span data-stu-id="35b0e-114">For example, a configuration can update the path of a source file, or change the name of a database or server.</span></span>  
  
-   <span data-ttu-id="35b0e-115">Конфигурации полезны при развертывании пакетов на множестве разных серверов.</span><span class="sxs-lookup"><span data-stu-id="35b0e-115">Configurations are useful when you deploy packages to many different servers.</span></span> <span data-ttu-id="35b0e-116">Например, переменная в конфигурации каждого развернутого пакета может иметь различное значение места на диске; если доступное место на диске не соответствует этому значению, данный пакет не запускается.</span><span class="sxs-lookup"><span data-stu-id="35b0e-116">For example, a variable in the configuration for each deployed package can contain a different disk space value, and if the available disk space does not meet this value, the package does not run.</span></span>  
  
-   <span data-ttu-id="35b0e-117">Конфигурации делают пакеты более гибкими.</span><span class="sxs-lookup"><span data-stu-id="35b0e-117">Configurations make packages more flexible.</span></span> <span data-ttu-id="35b0e-118">Например, конфигурация может обновить значение переменной, используемой в выражении свойства.</span><span class="sxs-lookup"><span data-stu-id="35b0e-118">For example, a configuration can update the value of a variable that is used in a property expression.</span></span>  
  
 [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="35b0e-119">поддерживают несколько различных методов хранения конфигураций пакетов, таких как XML-файлы, таблицы в базе данных [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , переменные среды и пакета.</span><span class="sxs-lookup"><span data-stu-id="35b0e-119">supports several different methods of storing package configurations, such as XML files, tables in a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] database, and environment and package variables.</span></span>  
  
 <span data-ttu-id="35b0e-120">Каждая конфигурация является парой вида «свойство-значение».</span><span class="sxs-lookup"><span data-stu-id="35b0e-120">Each configuration is a property/value pair.</span></span> <span data-ttu-id="35b0e-121">XML-файл конфигурации и [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] могут включать несколько конфигураций.</span><span class="sxs-lookup"><span data-stu-id="35b0e-121">The XML configuration file and [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] configuration types can include multiple configurations.</span></span>  
  
 <span data-ttu-id="35b0e-122">Конфигурации включаются при создании программы развертывания для установки пакетов.</span><span class="sxs-lookup"><span data-stu-id="35b0e-122">The configurations are included when you create a package deployment utility for installing packages.</span></span> <span data-ttu-id="35b0e-123">При установке пакета обновление конфигураций может быть одним из этапов установки.</span><span class="sxs-lookup"><span data-stu-id="35b0e-123">When you install the packages, the configurations can be updated as a step in the package installation.</span></span>  
  
## <a name="understanding-how-package-configurations-are-applied-at-run-time"></a><span data-ttu-id="35b0e-124">Основные сведения о применении параметров конфигурации пакетов во время выполнения</span><span class="sxs-lookup"><span data-stu-id="35b0e-124">Understanding How Package Configurations Are Applied at Run Time</span></span>  
 <span data-ttu-id="35b0e-125">Если для выполнения развернутого пакета используется программа командной строки **dtexec** (dtexec.exe), эта программа применяет параметры конфигурации пакета дважды.</span><span class="sxs-lookup"><span data-stu-id="35b0e-125">When you use the **dtexec** command prompt utility (dtexec.exe) to run a deployed package, the utility applies package configurations twice.</span></span> <span data-ttu-id="35b0e-126">до и после применения настроек, указанных в командной строке.</span><span class="sxs-lookup"><span data-stu-id="35b0e-126">The utility applies configurations both before and after it applies the options that you specified on command line.</span></span>  
  
 <span data-ttu-id="35b0e-127">Когда программа загружает и выполняет пакет, события происходят в следующем порядке.</span><span class="sxs-lookup"><span data-stu-id="35b0e-127">As the utility loads and runs the package, events occur in the following order:</span></span>  
  
1.  <span data-ttu-id="35b0e-128">Программа **dtexec** загружает пакет.</span><span class="sxs-lookup"><span data-stu-id="35b0e-128">The **dtexec** utility loads the package.</span></span>  
  
2.  <span data-ttu-id="35b0e-129">Программа применяет параметры конфигурации, заданные в пакете во время разработки, в порядке, который указан в пакете.</span><span class="sxs-lookup"><span data-stu-id="35b0e-129">The utility applies the configurations that were specified in the package at design time and in the order that is specified in the package.</span></span> <span data-ttu-id="35b0e-130">(Единственным исключением являются параметры конфигурации переменных родительского пакета.</span><span class="sxs-lookup"><span data-stu-id="35b0e-130">(The one exception to this is the Parent Package Variables configurations.</span></span> <span data-ttu-id="35b0e-131">Программа применяет их только один раз, в ходе дальнейшего процесса.)</span><span class="sxs-lookup"><span data-stu-id="35b0e-131">The utility applies these configurations only once and later in the process.)</span></span>  
  
3.  <span data-ttu-id="35b0e-132">Затем программа применяет параметры, указанные в командной строке.</span><span class="sxs-lookup"><span data-stu-id="35b0e-132">The utility then applies any options that you specified on the command line.</span></span>  
  
4.  <span data-ttu-id="35b0e-133">Затем программа повторно загружает параметры конфигурации, заданные в пакете во время разработки, в порядке, который указан в пакете.</span><span class="sxs-lookup"><span data-stu-id="35b0e-133">The utility then reloads the configurations that were specified in the package at design time and in the order specified in the package.</span></span> <span data-ttu-id="35b0e-134">(Исключением из этого правила вновь являются параметры конфигурации переменных родительского пакета.)</span><span class="sxs-lookup"><span data-stu-id="35b0e-134">(Again, the exception to this rule is the Parent Package Variables configurations).</span></span> <span data-ttu-id="35b0e-135">Программа применяет указанные параметры командной строки для повторной загрузки параметров конфигурации.</span><span class="sxs-lookup"><span data-stu-id="35b0e-135">The utility uses any command-line options that were specified to reload the configurations.</span></span> <span data-ttu-id="35b0e-136">Поэтому возможна повторная загрузка различных значений из различных расположений.</span><span class="sxs-lookup"><span data-stu-id="35b0e-136">Therefore, different values might be reloaded from a different location.</span></span>  
  
5.  <span data-ttu-id="35b0e-137">Программа применяет параметры конфигурации переменных родительского пакета.</span><span class="sxs-lookup"><span data-stu-id="35b0e-137">The utility applies the Parent Package Variable configurations.</span></span>  
  
6.  <span data-ttu-id="35b0e-138">Программа выполняет пакет.</span><span class="sxs-lookup"><span data-stu-id="35b0e-138">The utility runs the package.</span></span>  
  
 <span data-ttu-id="35b0e-139">Способ, которым программа **dtexec** применяет параметры конфигурации, влияет на следующие параметры командной строки:</span><span class="sxs-lookup"><span data-stu-id="35b0e-139">The way in which the **dtexec** utility applies configurations affects the following command-line options:</span></span>  
  
-   <span data-ttu-id="35b0e-140">Во время выполнения можно использовать параметр **/Connection** или **/Set** , чтобы загрузить параметры конфигурации пакета из расположения, отличного от указанного во время разработки.</span><span class="sxs-lookup"><span data-stu-id="35b0e-140">You can use the **/Connection** or **/Set** option at run time to load package configurations from a location other than the location that you specified at design time.</span></span>  
  
-   <span data-ttu-id="35b0e-141">С помощью параметра **/ConfigFile** можно загрузить дополнительные конфигурации, не указанные во время разработки.</span><span class="sxs-lookup"><span data-stu-id="35b0e-141">You can use the **/ConfigFile** option to load additional configurations that you did not specify at design time.</span></span>  
  
 <span data-ttu-id="35b0e-142">Однако к этим параметрам командной строки применяются некоторые ограничения.</span><span class="sxs-lookup"><span data-stu-id="35b0e-142">However, these command-line options do have some restrictions:</span></span>  
  
-   <span data-ttu-id="35b0e-143">Нельзя использовать параметр **/Set** или **/Connection** для переопределения единичных значений, которые также задаются конфигурацией.</span><span class="sxs-lookup"><span data-stu-id="35b0e-143">You cannot use the **/Set** or the **/Connection** option to override single values that are also set by a configuration.</span></span>  
  
-   <span data-ttu-id="35b0e-144">Нельзя использовать параметр **/ConfigFile** для загрузки конфигураций, которые заменяют параметры, указанные во время разработки.</span><span class="sxs-lookup"><span data-stu-id="35b0e-144">You cannot use the **/ConfigFile** option to load configurations that replace the configurations that you specified at design time.</span></span>  
  
 <span data-ttu-id="35b0e-145">Дополнительные сведения об этих параметрах и о различиях в работе этих параметров [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] в и более ранних версиях см. [в разделе изменения в работе Integration Services функций в SQL Server 2014](../../2014/integration-services/behavior-changes-to-integration-services-features-in-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="35b0e-145">For more information about these options, and how the behavior of these options differs between [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] and earlier versions, see [Behavior Changes to Integration Services Features in SQL Server 2014](../../2014/integration-services/behavior-changes-to-integration-services-features-in-sql-server-2014.md).</span></span>  
  
## <a name="package-configuration-types"></a><span data-ttu-id="35b0e-146">Типы конфигураций пакета</span><span class="sxs-lookup"><span data-stu-id="35b0e-146">Package Configuration Types</span></span>  
 <span data-ttu-id="35b0e-147">Следующая таблица описывает типы конфигураций пакета.</span><span class="sxs-lookup"><span data-stu-id="35b0e-147">The following table describes the package configuration types.</span></span>  
  
|<span data-ttu-id="35b0e-148">Тип</span><span class="sxs-lookup"><span data-stu-id="35b0e-148">Type</span></span>|<span data-ttu-id="35b0e-149">Описание</span><span class="sxs-lookup"><span data-stu-id="35b0e-149">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="35b0e-150">XML-файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="35b0e-150">XML configuration file</span></span>|<span data-ttu-id="35b0e-151">XML-файл содержит конфигурации.</span><span class="sxs-lookup"><span data-stu-id="35b0e-151">An XML file contains the configurations.</span></span> <span data-ttu-id="35b0e-152">XML-файл может включать несколько конфигураций.</span><span class="sxs-lookup"><span data-stu-id="35b0e-152">The XML file can include multiple configurations.</span></span>|  
|<span data-ttu-id="35b0e-153">Переменная среды</span><span class="sxs-lookup"><span data-stu-id="35b0e-153">Environment variable</span></span>|<span data-ttu-id="35b0e-154">Переменная среды содержит конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="35b0e-154">An environment variable contains the configuration.</span></span>|  
|<span data-ttu-id="35b0e-155">Параметр реестра</span><span class="sxs-lookup"><span data-stu-id="35b0e-155">Registry entry</span></span>|<span data-ttu-id="35b0e-156">Параметр реестра содержит конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="35b0e-156">A Registry entry contains the configuration.</span></span>|  
|<span data-ttu-id="35b0e-157">Переменная родительского пакета</span><span class="sxs-lookup"><span data-stu-id="35b0e-157">Parent package variable</span></span>|<span data-ttu-id="35b0e-158">Переменная пакета содержит конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="35b0e-158">A variable in the package contains the configuration.</span></span> <span data-ttu-id="35b0e-159">Этот тип конфигурации обычно используется для обновления свойств вызываемых пакетов.</span><span class="sxs-lookup"><span data-stu-id="35b0e-159">This configuration type is typically used to update properties in child packages.</span></span>|  
|<span data-ttu-id="35b0e-160">Таблица [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="35b0e-160">[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] table</span></span>|<span data-ttu-id="35b0e-161">Таблица в базе данных [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] содержит конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="35b0e-161">A table in a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] database contains the configuration.</span></span> <span data-ttu-id="35b0e-162">Таблица может включать несколько конфигураций.</span><span class="sxs-lookup"><span data-stu-id="35b0e-162">The table can include multiple configurations.</span></span>|  
  
### <a name="xml-configuration-files"></a><span data-ttu-id="35b0e-163">XML-файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="35b0e-163">XML Configuration Files</span></span>  
 <span data-ttu-id="35b0e-164">Выбрав тип конфигурации **XML-файл конфигурации** , можно создать новый файл конфигурации, использовать существующий и добавить новые конфигурации или использовать существующий и перезаписать его содержимое.</span><span class="sxs-lookup"><span data-stu-id="35b0e-164">If you select the **XML configuration file** configuration type, you can create a new configuration file, reuse an existing file and add new configurations, or reuse an existing file but overwrite existing file content.</span></span>  
  
 <span data-ttu-id="35b0e-165">XML-файл конфигурации содержит следующие два раздела.</span><span class="sxs-lookup"><span data-stu-id="35b0e-165">An XML configuration file includes two sections:</span></span>  
  
-   <span data-ttu-id="35b0e-166">Заголовок, содержащий сведения о файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="35b0e-166">A heading that contains information about the configuration file.</span></span> <span data-ttu-id="35b0e-167">Этот элемент включает атрибуты, такие как дата создания файла и имя создателя файла.</span><span class="sxs-lookup"><span data-stu-id="35b0e-167">This element includes attributes such as when the file was created and the name of the person who generated the file.</span></span>  
  
-   <span data-ttu-id="35b0e-168">Элементы конфигурации, содержащие сведения о каждой конфигурации.</span><span class="sxs-lookup"><span data-stu-id="35b0e-168">Configuration elements that contain information about each configuration.</span></span> <span data-ttu-id="35b0e-169">Этот элемент включает атрибуты, такие как путь свойства и заданное значение свойства.</span><span class="sxs-lookup"><span data-stu-id="35b0e-169">This element includes attributes such as the property path and the configured value of a property.</span></span>  
  
 <span data-ttu-id="35b0e-170">Следующий программный код на языке XML показывает синтаксис XML-файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="35b0e-170">The following XML code demonstrates the syntax of an XML configuration file.</span></span> <span data-ttu-id="35b0e-171">В этом примере показана конфигурация свойства Value для целочисленной переменной с именем `MyVar`.</span><span class="sxs-lookup"><span data-stu-id="35b0e-171">This example shows a configuration for the Value property of an integer variable named `MyVar`.</span></span>  
  
```  
<?xml version="1.0"?>  
<DTSConfiguration>  
   <DTSConfigurationHeading>  
      <DTSConfigurationFileInfo  
          GeneratedBy="DomainName\UserName"  
          GeneratedFromPackageName="Package"  
          GeneratedFromPackageID="{2AF06766-817A-4E28-9878-0DE37A150648}"  
          GeneratedDate="2/01/2005 5:58:09 PM"/>  
   </DTSConfigurationHeading>  
   <Configuration ConfiguredType="Property" Path="\Package.Variables[User::MyVar].Value" ValueType="Int32">  
      <ConfiguredValue>0</ConfiguredValue>  
   </Configuration>  
</DTSConfiguration>  
  
```  
  
### <a name="registry-entry"></a><span data-ttu-id="35b0e-172">Параметр реестра</span><span class="sxs-lookup"><span data-stu-id="35b0e-172">Registry Entry</span></span>  
 <span data-ttu-id="35b0e-173">Если для хранения конфигурации нужно использовать параметр реестра, то можно либо использовать существующий раздел, либо создать новый подраздел в разделе HKEY_CURRENT_USER.</span><span class="sxs-lookup"><span data-stu-id="35b0e-173">If you want to use a Registry entry to store the configuration, you can either use an existing key or create a new key in HKEY_CURRENT_USER.</span></span> <span data-ttu-id="35b0e-174">Используемый раздел реестра должен иметь значение с именем `Value`.</span><span class="sxs-lookup"><span data-stu-id="35b0e-174">The Registry key that you use must have a value named `Value`.</span></span> <span data-ttu-id="35b0e-175">Значение может иметь строковый тип или тип DWORD.</span><span class="sxs-lookup"><span data-stu-id="35b0e-175">The value can be a DWORD or a string.</span></span>  
  
 <span data-ttu-id="35b0e-176">Если выбран тип конфигурации **Запись реестра** , необходимо ввести имя раздела реестра в соответствующее поле.</span><span class="sxs-lookup"><span data-stu-id="35b0e-176">If you select the **Registry entry** configuration type, you type the name of the Registry key in the Registry entry box.</span></span> <span data-ttu-id="35b0e-177">Формат — \<registry key>.</span><span class="sxs-lookup"><span data-stu-id="35b0e-177">The format is \<registry key>.</span></span> <span data-ttu-id="35b0e-178">Если есть необходимость применить раздел реестра, не находящийся в корне куста HKEY_CURRENT_USER, используйте для указания этого раздела формат \<Registry key\registry key\\...>.</span><span class="sxs-lookup"><span data-stu-id="35b0e-178">If you want to use a Registry key that is not at the root of HKEY_CURRENT_USER, use the format \<Registry key\registry key\\...> to identify the key.</span></span> <span data-ttu-id="35b0e-179">Например, чтобы использовать раздел MyPackage, расположенный в разделе SSISPackages, введите `SSISPackages\MyPackage`.</span><span class="sxs-lookup"><span data-stu-id="35b0e-179">For example, to use the MyPackage key located in SSISPackages, type `SSISPackages\MyPackage`.</span></span>  
  
### <a name="sql-server"></a><span data-ttu-id="35b0e-180">SQL Server</span><span class="sxs-lookup"><span data-stu-id="35b0e-180">SQL Server</span></span>  
 <span data-ttu-id="35b0e-181">При выборе типа конфигурации **SQL Server** задается соединение с базой данных [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , в которой необходимо хранить конфигурации.</span><span class="sxs-lookup"><span data-stu-id="35b0e-181">If you select the **SQL Server** configuration type, you specify the connection to the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] database in which you want to store the configurations.</span></span> <span data-ttu-id="35b0e-182">Можно сохранить конфигурации в существующей таблице или создать новую в указанной базе данных.</span><span class="sxs-lookup"><span data-stu-id="35b0e-182">You can save the configurations to an existing table or create a new table in the specified database.</span></span>  
  
 <span data-ttu-id="35b0e-183">Следующая инструкция SQL показывает применяемую по умолчанию инструкцию CREATE TABLE, которую предоставляет мастер настройки пакета.</span><span class="sxs-lookup"><span data-stu-id="35b0e-183">The following SQL statement shows the default CREATE TABLE statement that the Package Configuration Wizard provides.</span></span>  
  
```  
CREATE TABLE [dbo].[SSIS Configurations]  
(  
ConfigurationFilter NVARCHAR(255) NOT NULL,  
ConfiguredValue NVARCHAR(255) NULL,  
PackagePath NVARCHAR(255) NOT NULL,  
ConfiguredValueType NVARCHAR(20) NOT NULL  
)  
  
```  
  
 <span data-ttu-id="35b0e-184">Имя, задаваемое для конфигурации, является значением, которое хранится в столбце **ConfigurationFilter** .</span><span class="sxs-lookup"><span data-stu-id="35b0e-184">The name that you provide for the configuration is the value stored in the **ConfigurationFilter** column.</span></span>  
  
## <a name="direct-and-indirect-configurations"></a><span data-ttu-id="35b0e-185">Прямые и косвенные конфигурации</span><span class="sxs-lookup"><span data-stu-id="35b0e-185">Direct and Indirect Configurations</span></span>  
 [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="35b0e-186">предоставляют прямые и косвенные конфигурации.</span><span class="sxs-lookup"><span data-stu-id="35b0e-186">provides direct and indirect configurations.</span></span> <span data-ttu-id="35b0e-187">Если задать конфигурации напрямую, службы [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] создадут прямую связь между элементом конфигурации и свойством объекта пакета.</span><span class="sxs-lookup"><span data-stu-id="35b0e-187">If you specify configurations directly, [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] creates a direct link between the configuration item and the package object property.</span></span> <span data-ttu-id="35b0e-188">Прямые конфигурации используются в том случае, когда местоположение источника не меняется.</span><span class="sxs-lookup"><span data-stu-id="35b0e-188">Direct configurations are a better choice when the location of the source does not change.</span></span> <span data-ttu-id="35b0e-189">Например, если пользователь уверен, что все развертываемые элементы пакета используют один и тот же путь к файлу, можно задать XML-файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="35b0e-189">For example, if you are sure that all deployments in the package use the same file path, you can specify an XML configuration file.</span></span>  
  
 <span data-ttu-id="35b0e-190">Косвенные конфигурации используют переменные среды.</span><span class="sxs-lookup"><span data-stu-id="35b0e-190">Indirect configurations use environment variables.</span></span> <span data-ttu-id="35b0e-191">Конфигурация указывает на переменную среды, содержащую значение конфигурации, вместо задания значения конфигурации напрямую.</span><span class="sxs-lookup"><span data-stu-id="35b0e-191">Instead of specifying the configuration setting directly, the configuration points to an environment variable, which in turn contains the configuration value.</span></span> <span data-ttu-id="35b0e-192">Использовать косвенные конфигурации лучше в случае, когда местоположение конфигурации меняется для каждого развертываемого пакета.</span><span class="sxs-lookup"><span data-stu-id="35b0e-192">Using indirect configurations is a better choice when the location of the configuration can change for each deployment of a package.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="35b0e-193">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="35b0e-193">Related Tasks</span></span>  
 [<span data-ttu-id="35b0e-194">Создание конфигурации пакетов</span><span class="sxs-lookup"><span data-stu-id="35b0e-194">Create Package Configurations</span></span>](../../2014/integration-services/create-package-configurations.md)  
  
## <a name="related-content"></a><span data-ttu-id="35b0e-195">См. также</span><span class="sxs-lookup"><span data-stu-id="35b0e-195">Related Content</span></span>  
  
-   <span data-ttu-id="35b0e-196">Техническая статья [Understanding Integration Services Package Configurations](https://go.microsoft.com/fwlink/?LinkId=165643)(Основные сведения о конфигурации пакетов служб Integration Services) на сайте msdn.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="35b0e-196">Technical article, [Understanding Integration Services Package Configurations](https://go.microsoft.com/fwlink/?LinkId=165643), on msdn.microsoft.com</span></span>  
  
-   <span data-ttu-id="35b0e-197">Запись блога, [Создание пакетов в конфигурациях пакетов кода](https://go.microsoft.com/fwlink/?LinkId=217663)на www.sqlis.com.</span><span class="sxs-lookup"><span data-stu-id="35b0e-197">Blog entry, [Creating packages in code - Package Configurations](https://go.microsoft.com/fwlink/?LinkId=217663), on www.sqlis.com.</span></span>  
  
-   <span data-ttu-id="35b0e-198">Запись блога, [Пример API — программное добавление файла конфигурации в пакет](https://go.microsoft.com/fwlink/?LinkId=217664)на blogs.MSDN.com.</span><span class="sxs-lookup"><span data-stu-id="35b0e-198">Blog entry, [API Sample - Programmatically add a configuration file to a package](https://go.microsoft.com/fwlink/?LinkId=217664), on blogs.msdn.com.</span></span>  
  
  
