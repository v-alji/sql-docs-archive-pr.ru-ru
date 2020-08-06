---
title: Шаг 4. Добавление конфигураций пакетов | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: e04a5321-63d5-4ec5-85b9-cb4eaf6c87f6
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 416cf17f967a145fccef1341b77f71a02ff3f3b9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664351"
---
# <a name="step-4-adding-package-configurations"></a><span data-ttu-id="8ba28-102">Шаг 4. Добавление конфигурации пакета</span><span class="sxs-lookup"><span data-stu-id="8ba28-102">Step 4: Adding Package Configurations</span></span>
  <span data-ttu-id="8ba28-103">В этой задаче необходимо добавить конфигурацию каждому пакету.</span><span class="sxs-lookup"><span data-stu-id="8ba28-103">In this task, you will add a configuration to each package.</span></span> <span data-ttu-id="8ba28-104">Конфигурации позволяют обновлять значения свойств и объектов пакетов во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="8ba28-104">Configurations update the values of package properties and package objects at run time.</span></span>  
  
 [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="8ba28-105">предоставляют различные типы конфигурации.</span><span class="sxs-lookup"><span data-stu-id="8ba28-105">provides a variety of configuration types.</span></span> <span data-ttu-id="8ba28-106">Конфигурации можно сохранять в переменных среды, в записях реестра, пользовательских переменных, таблицах [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] и XML-файлах.</span><span class="sxs-lookup"><span data-stu-id="8ba28-106">You can store configurations in environment variables, registry entries, user-defined variables, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] tables, and XML files.</span></span> <span data-ttu-id="8ba28-107">Чтобы обеспечить дополнительную гибкость, службы [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] поддерживают косвенную конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="8ba28-107">To provide additional flexibility, [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] supports the use of indirect configurations.</span></span> <span data-ttu-id="8ba28-108">Это подразумевает использование переменной среды для указания расположения конфигурации, которая, в свою очередь, указывает фактические значения.</span><span class="sxs-lookup"><span data-stu-id="8ba28-108">This means that you use an environment variable to specify the location of the configuration, which in turn specifies the actual values.</span></span> <span data-ttu-id="8ba28-109">Для пакетов проекта из учебника по развертыванию используется сочетание XML-файлов конфигурации и косвенная конфигурация.</span><span class="sxs-lookup"><span data-stu-id="8ba28-109">The packages in the Deployment Tutorial project use a combination of XML configuration files and indirect configurations.</span></span> <span data-ttu-id="8ba28-110">В XML-файле конфигурации могут содержаться параметры конфигурации для различных свойств, а когда возможно, и для различных пакетов.</span><span class="sxs-lookup"><span data-stu-id="8ba28-110">An XML configuration file can include configurations for multiple properties, and when appropriate, can be referenced by multiple packages.</span></span> <span data-ttu-id="8ba28-111">В данном учебнике для каждого пакета используется отдельный файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="8ba28-111">In this tutorial, you will use a separate configuration file for each package.</span></span>  
  
 <span data-ttu-id="8ba28-112">В файлах конфигурации часто содержатся конфиденциальные данные, такие как строки соединения.</span><span class="sxs-lookup"><span data-stu-id="8ba28-112">Configuration files frequently contain sensitive information such as connection strings.</span></span> <span data-ttu-id="8ba28-113">Поэтому необходимо использовать список управления доступом (ACL), чтобы ограничить доступ к месту или папке, где хранятся эти файлы, и предоставить доступ только пользователям или учетным записям, обладающим разрешением на выполнение пакетов.</span><span class="sxs-lookup"><span data-stu-id="8ba28-113">Therefore, you should use an access control list (ACL) to restrict access to the location or folder where you store the files, and give access only to users or accounts that are permitted to run packages.</span></span> <span data-ttu-id="8ba28-114">Дополнительные сведения см. в разделе [Доступ к файлам, используемым пакетами](../../2014/integration-services/access-to-files-used-by-packages.md).</span><span class="sxs-lookup"><span data-stu-id="8ba28-114">For more information, see [Access to Files Used by Packages](../../2014/integration-services/access-to-files-used-by-packages.md).</span></span>  
  
 <span data-ttu-id="8ba28-115">Для успешного выполнения после разворачивания на целевом сервере пакетам (DataTransfer и LoadXMLData), добавленным в проект из учебника по развертыванию в предыдущей задаче, необходимы конфигурации.</span><span class="sxs-lookup"><span data-stu-id="8ba28-115">The packages (DataTransfer and LoadXMLData) that you added to the Deployment Tutorial project in the previous task need configurations to run successfully after they are deployed to the target server.</span></span> <span data-ttu-id="8ba28-116">Для выполнения настройки сначала необходимо создать косвенную конфигурацию для XML-файлов конфигурации и затем создать XML-файлы конфигурации.</span><span class="sxs-lookup"><span data-stu-id="8ba28-116">To implement configurations, you will first create the indirect configurations for the XML configuration files, and then you will create the XML configuration files.</span></span>  
  
 <span data-ttu-id="8ba28-117">Будут созданы два файла конфигурации, DataTransferConfig.dtsConfig и LoadXMLData.dtsConfig.</span><span class="sxs-lookup"><span data-stu-id="8ba28-117">You will create two configuration files, DataTransferConfig.dtsConfig and LoadXMLData.dtsConfig.</span></span> <span data-ttu-id="8ba28-118">Эти файлы содержат пары «имя-значение», обновляющие в пакетах свойства, которые указывают расположение используемых пакетом файлов данных и журналов.</span><span class="sxs-lookup"><span data-stu-id="8ba28-118">These files contain name-value pairs that update the properties in packages that specify the location of the data and log files used by the package.</span></span> <span data-ttu-id="8ba28-119">Позже, на одном из этапов процесса развертывания, потребуется обновить значения в файлах конфигурации, чтобы отразить новое место хранения файлов на целевом компьютере.</span><span class="sxs-lookup"><span data-stu-id="8ba28-119">Later, as a step in the deployment process, you will update the values in the configuration files to reflect the new location of the files on the destination computer.</span></span>  
  
 [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="8ba28-120">распознают, что файлы DataTransferConfig.dtsConfig и LoadXMLData.dtsConfig представляют собой зависимости пакетов DataTransfer и LoadXMLData, и на следующем занятии при создании комплекта развертывания в них автоматически будут содержаться эти файлы конфигурации.</span><span class="sxs-lookup"><span data-stu-id="8ba28-120">recognizes that the DataTransferConfig.dtsConfig and LoadXMLData.dtsConfig are dependencies of the DataTransfer and LoadXMLData packages, and automatically includes the configuration files when you create the deployment bundle in the next lesson.</span></span>  
  
### <a name="to-create-indirect-configuration-for-the-datatransfer-package"></a><span data-ttu-id="8ba28-121">Создание косвенной конфигурации для пакета DataTransfer</span><span class="sxs-lookup"><span data-stu-id="8ba28-121">To create indirect configuration for the DataTransfer package</span></span>  
  
1.  <span data-ttu-id="8ba28-122">В обозревателе решений дважды щелкните DataTransfer.dtsx.</span><span class="sxs-lookup"><span data-stu-id="8ba28-122">In Solution Explorer, double-click DataTransfer.dtsx.</span></span>  
  
2.  <span data-ttu-id="8ba28-123">В конструкторе служб [!INCLUDE[ssIS](../includes/ssis-md.md)] щелкните в области конструктора потока управления.</span><span class="sxs-lookup"><span data-stu-id="8ba28-123">In [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, click anywhere in the background of the control flow design surface.</span></span>  
  
3.  <span data-ttu-id="8ba28-124">В меню **Службы SSIS** выберите команду **Конфигурации пакетов**.</span><span class="sxs-lookup"><span data-stu-id="8ba28-124">On the **SSIS** menu, click **Package Configurations**.</span></span>  
  
4.  <span data-ttu-id="8ba28-125">В диалоговом окне **Организатор конфигурации пакетов**установите флажок **Включить конфигурации пакетов** , если эта функция еще не активирована, и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="8ba28-125">In the **Package Configuration Organize**r dialog box, select **Enable package configurations** if it is not already selected, and then click **Add**.</span></span>  
  
5.  <span data-ttu-id="8ba28-126">На странице приветствия мастера настройки пакета нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8ba28-126">On the welcome page of the Package Configuration Wizard, click **Next**.</span></span>  
  
6.  <span data-ttu-id="8ba28-127">На странице Выбор типа конфигурации выберите **XML-файл конфигурации** в списке **тип конфигурации** , выберите **Расположение конфигурации хранится в переменной среды** и введите `DataTransfer,` или выберите переменную среды **обмена** в списке.</span><span class="sxs-lookup"><span data-stu-id="8ba28-127">On the Select Configuration Type page, select **XML configuration file** in the **Configuration type** list, select the **Configuration location is stored in an environment variable** option, and type `DataTransfer,` or select the **DataTransfer** environment variable in the list.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8ba28-128">Чтобы переменная среды была доступна в списке, после добавления переменной может потребоваться перезагрузка компьютера.</span><span class="sxs-lookup"><span data-stu-id="8ba28-128">To make the environment variable available in the list, you may have to restart your computer after adding the variable.</span></span> <span data-ttu-id="8ba28-129">Если перезагрузка компьютера нежелательна, можно просто ввести имя переменной.</span><span class="sxs-lookup"><span data-stu-id="8ba28-129">If you do not want to restart the computer, you can type the name of the environment variable.</span></span>  
  
7.  <span data-ttu-id="8ba28-130">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8ba28-130">Click **Next**.</span></span>  
  
8.  <span data-ttu-id="8ba28-131">На странице «Завершение работы мастера» в окне **Имя конфигурации** введите **DataTransfer EV Configuration** , проверьте содержимое конфигурации на панели **Предварительный просмотр** и нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="8ba28-131">On the Completing the Wizard page, type **DataTransfer EV Configuration** in the **Configuration name** box, review the configuration contents in the **Preview** pane, and then click **Finish**.</span></span>  
  
9. <span data-ttu-id="8ba28-132">Закройте диалоговое окно **Организатор конфигурации пакетов**.</span><span class="sxs-lookup"><span data-stu-id="8ba28-132">Close the **Package Configuration Organize**r dialog box.</span></span>  
  
### <a name="to-create-the-xml-configuration-for-the-datatransfer-package"></a><span data-ttu-id="8ba28-133">Создание XML-конфигурации для пакета DataTransfer</span><span class="sxs-lookup"><span data-stu-id="8ba28-133">To create the XML configuration for the DataTransfer package</span></span>  
  
1.  <span data-ttu-id="8ba28-134">В обозревателе решений дважды щелкните DataTransfer.dtsx.</span><span class="sxs-lookup"><span data-stu-id="8ba28-134">In Solution Explorer, double-click DataTransfer.dtsx.</span></span>  
  
2.  <span data-ttu-id="8ba28-135">В конструкторе служб [!INCLUDE[ssIS](../includes/ssis-md.md)] щелкните в области конструктора потока управления.</span><span class="sxs-lookup"><span data-stu-id="8ba28-135">In [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, click anywhere in the background of the control flow design surface.</span></span>  
  
3.  <span data-ttu-id="8ba28-136">В меню **Службы SSIS** выберите команду **Конфигурации пакетов**.</span><span class="sxs-lookup"><span data-stu-id="8ba28-136">On the **SSIS** menu, click **Package Configurations**.</span></span>  
  
4.  <span data-ttu-id="8ba28-137">В диалоговом окне "Организатор конфигурации пакетов" установите флажок **Включить конфигурации пакетов** и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="8ba28-137">In the Package Configuration Organizer dialog box, select the **Enable Package Configurations** check-box, and then click **Add**.</span></span>  
  
5.  <span data-ttu-id="8ba28-138">На странице приветствия мастера настройки пакета нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8ba28-138">On the welcome page of the Package Configuration Wizard, click **Next**.</span></span>  
  
6.  <span data-ttu-id="8ba28-139">На странице выбора типа конфигурации в списке **Тип конфигурации** выберите **XML-файл конфигурации** и нажмите кнопку **Обзор**.</span><span class="sxs-lookup"><span data-stu-id="8ba28-139">On the Select Configuration Type page, select **XML configuration file** in the **Configuration type** list and then click **Browse**.</span></span>  
  
7.  <span data-ttu-id="8ba28-140">В диалоговом окне **Выберите расположение файла конфигурации** укажите путь к папке C:\DeploymentTutorial и в поле **Имя файла** введите **DataTransferConfig** , после чего нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="8ba28-140">In **Select Configuration File Location** dialog box, navigate to C:\DeploymentTutorial and type **DataTransferConfig** in the **File name** box, and then click **Save**.</span></span>  
  
8.  <span data-ttu-id="8ba28-141">На странице выбора типа конфигурации нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8ba28-141">On the Select Configuration Type page, click **Next**.</span></span>  
  
9. <span data-ttu-id="8ba28-142">На странице выбора свойств для экспорта раскройте разделы "DataTransfer", "Диспетчеры соединений", "Журнал учебника по развертыванию" и "Свойства", после чего установите флажок **Строка подключения** .</span><span class="sxs-lookup"><span data-stu-id="8ba28-142">On the Select Properties to Export page, expand DataTransfer, Connection Managers, Deployment Tutorial Log, and Properties, and then select the **Connection String** check-box.</span></span>  
  
10. <span data-ttu-id="8ba28-143">В разделе "Диспетчеры соединений" разверните узел "NewCustomers" и установите флажок **Строка подключения** .</span><span class="sxs-lookup"><span data-stu-id="8ba28-143">Within Connection Managers, expand NewCustomers, and then select the **Connection String** check-box.</span></span>  
  
11. <span data-ttu-id="8ba28-144">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8ba28-144">Click **Next**.</span></span>  
  
12. <span data-ttu-id="8ba28-145">На странице «Завершение работы мастера» в окне **Имя конфигурации** введите **DataTransfer Configuration** , проверьте содержимое конфигурации и нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="8ba28-145">On the Completing the Wizard page, type **DataTransfer Configuration** in the **Configuration name** box, review the content of the configuration, and then click **Finish**.</span></span>  
  
13. <span data-ttu-id="8ba28-146">В диалоговом окне **Организатор конфигурации пакетов** убедитесь, что конфигурация DataTransfer EV Configuration находится на первом месте в списке, а DataTransfer Configuration на втором, и нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="8ba28-146">In the **Package Configuration Organizer** dialog box, verify that DataTransfer EV Configuration is listed first, and DataTransfer Configuration is listed second, and then click **Close**.</span></span>  
  
### <a name="to-create-indirect-configuration-for-the-loadxmldata-package"></a><span data-ttu-id="8ba28-147">Создание косвенной конфигурации для пакета LoadXMLData</span><span class="sxs-lookup"><span data-stu-id="8ba28-147">To create indirect configuration for the LoadXMLData package</span></span>  
  
1.  <span data-ttu-id="8ba28-148">В обозревателе решений дважды щелкните LoadXMLData.dtsx.</span><span class="sxs-lookup"><span data-stu-id="8ba28-148">In Solution Explorer, double-click LoadXMLData.dtsx.</span></span>  
  
2.  <span data-ttu-id="8ba28-149">В конструкторе служб [!INCLUDE[ssIS](../includes/ssis-md.md)] щелкните в области конструктора потока управления.</span><span class="sxs-lookup"><span data-stu-id="8ba28-149">In [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, click anywhere in the background of the control flow design surface.</span></span>  
  
3.  <span data-ttu-id="8ba28-150">В меню **Службы SSIS** выберите команду **Конфигурации пакетов**.</span><span class="sxs-lookup"><span data-stu-id="8ba28-150">On the **SSIS** menu, click **Package Configurations**.</span></span>  
  
4.  <span data-ttu-id="8ba28-151">В диалоговом окне **Организатор конфигурации пакетов**нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="8ba28-151">In the **Package Configuration Organize**r dialog box, Click **Add**.</span></span>  
  
5.  <span data-ttu-id="8ba28-152">На странице приветствия мастера настройки пакета нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8ba28-152">On the welcome page of the Package Configuration Wizard, click **Next**.</span></span>  
  
6.  <span data-ttu-id="8ba28-153">На странице Выбор типа конфигурации выберите **XML-файл конфигурации** в списке **тип конфигурации** , выберите **Расположение конфигурации хранится в переменной среды** , введите `LoadXMLData` или выберите `LoadXMLData` переменную среды в списке.</span><span class="sxs-lookup"><span data-stu-id="8ba28-153">On the Select Configuration Type page, select **XML configuration file** in the **Configuration type** list, select the **Configuration location is stored in an environment variable** option, type `LoadXMLData` or select the `LoadXMLData` environment variable in the list.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8ba28-154">Чтобы переменная среды была доступна в списке, после добавления переменной может потребоваться перезагрузка компьютера.</span><span class="sxs-lookup"><span data-stu-id="8ba28-154">To make the environment variable available in the list, you may have to restart your computer after adding the variable.</span></span>  
  
7.  <span data-ttu-id="8ba28-155">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8ba28-155">Click **Next**.</span></span>  
  
8.  <span data-ttu-id="8ba28-156">На странице «Завершение работы мастера» в окне **Имя конфигурации** введите **LoadXMLData EV Configuration** , проверьте содержимое конфигурации и нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="8ba28-156">On the Completing the Wizard page, type **LoadXMLData EV Configuration** in the **Configuration name** box, review the content of the configuration, and then click **Finish**.</span></span>  
  
### <a name="to-create-the-xml-configuration-for-the-loadxmldata-package"></a><span data-ttu-id="8ba28-157">Создание XML-конфигурации для пакета LoadXMLData</span><span class="sxs-lookup"><span data-stu-id="8ba28-157">To create the XML configuration for the LoadXMLData package</span></span>  
  
1.  <span data-ttu-id="8ba28-158">В обозревателе решений дважды щелкните LoadXMLData.dtsx.</span><span class="sxs-lookup"><span data-stu-id="8ba28-158">In Solution Explorer, double-click LoadXMLData.dtsx.</span></span>  
  
2.  <span data-ttu-id="8ba28-159">В конструкторе служб [!INCLUDE[ssIS](../includes/ssis-md.md)] щелкните в области конструктора потока управления.</span><span class="sxs-lookup"><span data-stu-id="8ba28-159">In [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, click anywhere in the background of the control flow design surface.</span></span>  
  
3.  <span data-ttu-id="8ba28-160">В меню **Службы SSIS** выберите команду **Конфигурации пакетов**.</span><span class="sxs-lookup"><span data-stu-id="8ba28-160">On the **SSIS** menu, click **Package Configurations**.</span></span>  
  
4.  <span data-ttu-id="8ba28-161">В диалоговом окне "Организатор конфигурации пакетов" установите флажок **Включить конфигурации пакетов** и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="8ba28-161">In the Package Configuration Organizer dialog box, select the **Enable Package Configurations** check-box, and click **Add**.</span></span>  
  
5.  <span data-ttu-id="8ba28-162">На странице приветствия мастера настройки пакета нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8ba28-162">On the welcome page of the Package Configuration Wizard, click **Next**.</span></span>  
  
6.  <span data-ttu-id="8ba28-163">На странице выбора типа конфигурации в списке **Тип конфигурации** выберите **XML-файл конфигурации** и нажмите кнопку **Обзор**.</span><span class="sxs-lookup"><span data-stu-id="8ba28-163">On the Select Configuration Type page, select **XML configuration file** in the **Configuration type** list and click **Browse**.</span></span>  
  
7.  <span data-ttu-id="8ba28-164">В диалоговом окне **Выберите расположение файла конфигурации** укажите путь к папке C:\DeploymentTutorial и в поле **Имя файла** введите **LoadXMLDataConfig** , после чего нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="8ba28-164">In **Select Configuration File Location** dialog box, navigate to C:\DeploymentTutorial and type **LoadXMLDataConfig** in the **File name** box, and then click **Save**.</span></span>  
  
8.  <span data-ttu-id="8ba28-165">На странице выбора типа конфигурации нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8ba28-165">On the Select Configuration Type page, click **Next**.</span></span>  
  
9. <span data-ttu-id="8ba28-166">На странице выбора свойств для экспорта разверните узлы "LoadXMLData", "Исполняемые объекты", "Загрузка XML-данных" и "Свойства", после чего установите флажки **[XMLSource].[XMLData]** и **[XMLSource].[XMLSchemaDefinition]** .</span><span class="sxs-lookup"><span data-stu-id="8ba28-166">On the Select Properties to Export page, expand LoadXMLData, Executables, Load XML Data, and Properties, and then select the **[XMLSource].[XMLData]** and **[XMLSource].[XMLSchemaDefinition]** check boxes.</span></span>  
  
10. <span data-ttu-id="8ba28-167">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8ba28-167">Click **Next**.</span></span>  
  
11. <span data-ttu-id="8ba28-168">На странице «Завершение работы мастера» в окне **Имя конфигурации** введите **LoadXMLData Configuration** , проверьте содержимое конфигурации и нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="8ba28-168">On the Completing the Wizard page, type **LoadXMLData Configuration** in the **Configuration name** box, review the content of the configuration, and then click **Finish**.</span></span>  
  
12. <span data-ttu-id="8ba28-169">В диалоговом окне **Организатор конфигурации пакетов** убедитесь, что конфигурация LoadXMLData EV Configuration находится на первом месте в списке, а LoadXMLData Configuration на втором, и нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="8ba28-169">In the **Package Configuration Organizer** dialog box, verify that the LoadXMLData EV Configuration is listed first, and the LoadXMLData Configuration is listed second, and then click **Close**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="8ba28-170">Следующая задача занятия</span><span class="sxs-lookup"><span data-stu-id="8ba28-170">Next Task in Lesson</span></span>  
 [<span data-ttu-id="8ba28-171">Шаг 5. Тестирование обновленных пакетов</span><span class="sxs-lookup"><span data-stu-id="8ba28-171">Step 5: Testing the Updated Packages</span></span>](../integration-services/lesson-1-5-testing-the-updated-packages.md)  
  
<span data-ttu-id="8ba28-172">![Значок Integration Services (маленький)](media/dts-16.gif "Значок служб Integration Services (маленький)")  **следит за обновлениями Integration Services**</span><span class="sxs-lookup"><span data-stu-id="8ba28-172">![Integration Services icon (small)](media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="8ba28-173">Чтобы загрузить новейшую документацию, статьи, образцы и видеоматериалы корпорации Майкрософт, а также лучшие решения участников сообщества, посетите страницу служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] на сайте MSDN:</span><span class="sxs-lookup"><span data-stu-id="8ba28-173">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="8ba28-174">Посетить страницу «Службы Integration Services» на сайте MSDN</span><span class="sxs-lookup"><span data-stu-id="8ba28-174">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="8ba28-175">Чтобы получать автоматические уведомления об этих обновлениях, подпишитесь на RSS-каналы, предлагаемые на этой странице.</span><span class="sxs-lookup"><span data-stu-id="8ba28-175">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ba28-176">См. также:</span><span class="sxs-lookup"><span data-stu-id="8ba28-176">See Also</span></span>  
 <span data-ttu-id="8ba28-177">[Конфигурации пакетов](../../2014/integration-services/package-configurations.md) </span><span class="sxs-lookup"><span data-stu-id="8ba28-177">[Package Configurations](../../2014/integration-services/package-configurations.md) </span></span>  
 <span data-ttu-id="8ba28-178">[Создание конфигураций пакетов](../../2014/integration-services/create-package-configurations.md) </span><span class="sxs-lookup"><span data-stu-id="8ba28-178">[Create Package Configurations](../../2014/integration-services/create-package-configurations.md) </span></span>  
 [<span data-ttu-id="8ba28-179">Доступ к файлам, используемым пакетами</span><span class="sxs-lookup"><span data-stu-id="8ba28-179">Access to Files Used by Packages</span></span>](../../2014/integration-services/access-to-files-used-by-packages.md)  
  
  
