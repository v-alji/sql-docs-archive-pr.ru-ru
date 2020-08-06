---
title: Создание конфигураций пакетов | Документация Майкрософт
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Integration Services packages, configurations
- Package Configurations Organizer dialog box
- SSIS packages, configurations
- Integration Services packages, configurations
- configurations [Integration Services]
- packages [Integration Services], configurations
- deploying packages [Integration Services], configurations
ms.assetid: 91ac0347-f908-44f5-bd3d-115790223af4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 58c93242c9ef51a5e00076bd367e46b43187098e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658323"
---
# <a name="create-package-configurations"></a><span data-ttu-id="ec927-102">Создание конфигурации пакетов</span><span class="sxs-lookup"><span data-stu-id="ec927-102">Create Package Configurations</span></span>
  <span data-ttu-id="ec927-103">Конфигурации пакетов создаются с помощью диалогового окна **Организатор конфигураций пакетов**, а также мастера настройки пакетов.</span><span class="sxs-lookup"><span data-stu-id="ec927-103">You create package configurations by using the **Package Configuration Organizer** dialog box and the Package Configuration Wizard.</span></span> <span data-ttu-id="ec927-104">Для доступа к этим средствам выберите **Конфигурация пакетов** в меню **службы SSIS** среды [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ec927-104">To access these tools, click **Package Configurations** on the **SSIS** menu in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ec927-105">Вы также можете получить доступ к **организатору конфигураций пакетов**, нажав кнопку с многоточием рядом со свойством **конфигурации** .</span><span class="sxs-lookup"><span data-stu-id="ec927-105">You can also access the **Package Configuration Organizer**, by clicking the ellipsis button next to the **Configuration** property.</span></span> <span data-ttu-id="ec927-106">Свойство «Конфигурация» отображается в окне свойств пакета.</span><span class="sxs-lookup"><span data-stu-id="ec927-106">The Configuration property appears in the properties window for the package.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ec927-107">Доступны конфигурации для модели развертывания пакетов.</span><span class="sxs-lookup"><span data-stu-id="ec927-107">Configurations are available for the package deployment model.</span></span> <span data-ttu-id="ec927-108">Для моделей развертывания проектов вместо конфигураций используются параметры.</span><span class="sxs-lookup"><span data-stu-id="ec927-108">Parameters are used in place of configurations for the project deployment model.</span></span> <span data-ttu-id="ec927-109">Модель развертывания проектов позволяет развертывать проекты служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] на сервере служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ec927-109">The project deployment model enables you to deploy [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] projects to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] server.</span></span> <span data-ttu-id="ec927-110">Дополнительные сведения о моделях развертывания см. в разделе [Deployment of Projects and Packages](packages/deploy-integration-services-ssis-projects-and-packages.md).</span><span class="sxs-lookup"><span data-stu-id="ec927-110">For more information about the deployment models, see [Deployment of Projects and Packages](packages/deploy-integration-services-ssis-projects-and-packages.md).</span></span>  
  
 <span data-ttu-id="ec927-111">В окне **Организатор конфигураций пакетов** можно разрешить пакетам использовать, добавить и удалить конфигурации, а также настроить порядок загрузки конфигураций.</span><span class="sxs-lookup"><span data-stu-id="ec927-111">In the **Package Configuration Organizer** dialog box, you can enable packages to use configurations, add and delete configurations, and set the preferred order in which configurations should be loaded.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ec927-112">При загрузке в указанном порядке конфигурации загружаются с верхней части списка, показанного в диалоговом окне **Организатор конфигураций пакетов** , в нижнюю часть списка.</span><span class="sxs-lookup"><span data-stu-id="ec927-112">When package configurations load in the preferred order, configurations load from the top of the list shown in the **Package Configuration Organizer** dialog box to the bottom of the list.</span></span> <span data-ttu-id="ec927-113">Однако во время выполнения конфигурации пакетов могут загружаться в другом порядке.</span><span class="sxs-lookup"><span data-stu-id="ec927-113">However, at run time, package configurations might not load in the preferred order.</span></span> <span data-ttu-id="ec927-114">В частности, конфигурации родительских пакетов загружаются после всех остальных конфигураций.</span><span class="sxs-lookup"><span data-stu-id="ec927-114">In particular, parent package configurations load after configurations of other types.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ec927-115">Если для одного свойства объекта задано несколько конфигураций, то при запуске будет загружаться значение, которое применялось в прошлый раз.</span><span class="sxs-lookup"><span data-stu-id="ec927-115">If multiple configurations set the same object property, the value loaded last is used at run time.</span></span>  
  
 <span data-ttu-id="ec927-116">В окне **Организатор конфигураций пакетов** можно запускать мастер настройки пакетов, с помощью которого создаются конфигурации.</span><span class="sxs-lookup"><span data-stu-id="ec927-116">From the **Package Configuration Organizer** dialog box, you run the Package Configuration Wizard, which guides you through the steps to create a configuration.</span></span> <span data-ttu-id="ec927-117">Чтобы запустить мастер настройки пакетов, добавьте новую конфигурацию в диалоговом окне **Организатор конфигураций пакетов** или измените существующую конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="ec927-117">To run the Package Configuration Wizard, add a new configuration in the **Package Configurations Organizer** dialog box or edit an existing one.</span></span> <span data-ttu-id="ec927-118">На страницах мастера предлагается выбрать тип конфигурации, способ доступа к ней (напрямую или с помощью переменных среды), а также свойства, которые будут сохранены в конфигурации.</span><span class="sxs-lookup"><span data-stu-id="ec927-118">On the wizard pages, you choose the configuration type, select whether you want to access the configuration directly or use environment variables, and select the properties to save in the configuration.</span></span>  
  
 <span data-ttu-id="ec927-119">Следующий пример демонстрирует целевые свойства переменных и пакетов в том порядке, в котором они появляются на странице «Завершение работы мастера» мастера настройки пакета:</span><span class="sxs-lookup"><span data-stu-id="ec927-119">The following example shows the target properties of a variable and a package as they appear on the Completing the Wizard page of the Package Configuration Wizard.:</span></span>  
  
 <span data-ttu-id="ec927-120">\Package.Variables[User::TodaysDate].Properties[RaiseChangedEvent]</span><span class="sxs-lookup"><span data-stu-id="ec927-120">\Package.Variables[User::TodaysDate].Properties[RaiseChangedEvent]</span></span>  
  
 <span data-ttu-id="ec927-121">\Package.Properties[MaximumErrorCount]</span><span class="sxs-lookup"><span data-stu-id="ec927-121">\Package.Properties[MaximumErrorCount]</span></span>  
  
 <span data-ttu-id="ec927-122">\Package.Properties[LoggingMode]</span><span class="sxs-lookup"><span data-stu-id="ec927-122">\Package.Properties[LoggingMode]</span></span>  
  
 <span data-ttu-id="ec927-123">\Package.Properties[LocaleID]</span><span class="sxs-lookup"><span data-stu-id="ec927-123">\Package.Properties[LocaleID]</span></span>  
  
 <span data-ttu-id="ec927-124">\Package\My SQL Task.Variables[User::varTableName].Properties[Value]</span><span class="sxs-lookup"><span data-stu-id="ec927-124">\Package\My SQL Task.Variables[User::varTableName].Properties[Value]</span></span>  
  
 <span data-ttu-id="ec927-125">В этом примере конфигурация обновляет следующие свойства:</span><span class="sxs-lookup"><span data-stu-id="ec927-125">In this example, the configuration updates these properties:</span></span>  
  
-   <span data-ttu-id="ec927-126">Свойство RaiseChangedEvent пользовательской переменной `TodaysDate`.</span><span class="sxs-lookup"><span data-stu-id="ec927-126">The RaiseChangedEvent property of user-defined variable, `TodaysDate`.</span></span>  
  
-   <span data-ttu-id="ec927-127">Свойства MaximumErrorCount, LoggingMode и LocaleID пакета.</span><span class="sxs-lookup"><span data-stu-id="ec927-127">The MaximumErrorCount, LoggingMode, and LocaleID properties of the package.</span></span>  
  
-   <span data-ttu-id="ec927-128">Свойство Value пользовательской переменной `varTableName`в рамках области задачи "My SQL Task".</span><span class="sxs-lookup"><span data-stu-id="ec927-128">The Value property of user-defined variable, `varTableName`, within scope of the task, My SQL Task.</span></span>  
  
 <span data-ttu-id="ec927-129">«\Package» представляет собой корневой каталог, а точки (.) разделяют объекты, определяющие путь к свойству, которое изменяет конфигурация.</span><span class="sxs-lookup"><span data-stu-id="ec927-129">The "\Package" represents the root, and periods (.) separate the objects that define the path to the property that the configuration updates.</span></span> <span data-ttu-id="ec927-130">Имена переменных и свойств заключаются в скобки.</span><span class="sxs-lookup"><span data-stu-id="ec927-130">The names of variables and properties are enclosed in brackets.</span></span> <span data-ttu-id="ec927-131">Термин «Package» всегда используется в конфигурациях, независимо от имени пакета; тем не менее, другие объекты в пути используют пользовательские имена.</span><span class="sxs-lookup"><span data-stu-id="ec927-131">The term Package is always used in configuration, regardless of the package name; however, all other objects in the path use their user-defined names.</span></span>  
  
 <span data-ttu-id="ec927-132">После окончания работы мастера новая конфигурация добавляется в список конфигураций в диалоговом окне **Организатор конфигураций пакетов** .</span><span class="sxs-lookup"><span data-stu-id="ec927-132">After the wizard finishes, the new configuration is added to the configuration list in the **Package Configuration Organizer** dialog box.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ec927-133">Последняя страница мастера настройки пакета перечисляет целевые свойства в конфигурации.</span><span class="sxs-lookup"><span data-stu-id="ec927-133">The last page in the Package Configuration Wizard, Completing the Wizard, lists the target properties in the configuration.</span></span> <span data-ttu-id="ec927-134">Если во время запуска пакета с помощью программы командной строки **dtexec** необходимо изменить его свойства, можно сформировать строки, представляющие пути свойства, запустив мастер настройки пакетов, а затем скопировав и вставив их в окно командной строки, чтобы использовать в качестве параметров программы **dtexec.**</span><span class="sxs-lookup"><span data-stu-id="ec927-134">If you want to update properties when you run packages by using the **dtexec** command prompt utility, you can generate the strings that represent the property paths by running the Package Configuration Wizard and then copy and paste them into the command prompt window for use with the set option of **dtexec.**</span></span>  
  
 <span data-ttu-id="ec927-135">В приведенной ниже таблице описаны столбцы списка конфигураций в диалоговом окне **Организатор конфигураций пакетов** .</span><span class="sxs-lookup"><span data-stu-id="ec927-135">The following table describes the columns in the configuration list in the **Package Configuration Organizer** dialog box.</span></span>  
  
|<span data-ttu-id="ec927-136">Столбец</span><span class="sxs-lookup"><span data-stu-id="ec927-136">Column</span></span>|<span data-ttu-id="ec927-137">Описание</span><span class="sxs-lookup"><span data-stu-id="ec927-137">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="ec927-138">**Имя конфигурации**</span><span class="sxs-lookup"><span data-stu-id="ec927-138">**Configuration Name**</span></span>|<span data-ttu-id="ec927-139">Имя конфигурации.</span><span class="sxs-lookup"><span data-stu-id="ec927-139">The name of the configuration.</span></span>|  
|<span data-ttu-id="ec927-140">**Тип конфигурации**</span><span class="sxs-lookup"><span data-stu-id="ec927-140">**Configuration Type**</span></span>|<span data-ttu-id="ec927-141">Тип конфигурации.</span><span class="sxs-lookup"><span data-stu-id="ec927-141">The configuration type.</span></span>|  
|<span data-ttu-id="ec927-142">**Строка конфигурации**</span><span class="sxs-lookup"><span data-stu-id="ec927-142">**Configuration String**</span></span>|<span data-ttu-id="ec927-143">Расположение конфигурации.</span><span class="sxs-lookup"><span data-stu-id="ec927-143">The location of the configuration.</span></span> <span data-ttu-id="ec927-144">Расположением может быть путь, переменная среды, раздел реестра, имя переменной в родительском пакете или таблица в базе данных [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ec927-144">The location can be a path, an environment variable, a Registry key, a parent package variable name, or a table in a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] database.</span></span>|  
|<span data-ttu-id="ec927-145">**Целевой объект**</span><span class="sxs-lookup"><span data-stu-id="ec927-145">**Target Object**</span></span>|<span data-ttu-id="ec927-146">Имя объекта со свойством, у которого есть конфигурация.</span><span class="sxs-lookup"><span data-stu-id="ec927-146">The name of the object with a property that has a configuration.</span></span> <span data-ttu-id="ec927-147">Если конфигурация является XML-файлом конфигурации, столбец остается пустым, потому что конфигурация может обновлять несколько объектов.</span><span class="sxs-lookup"><span data-stu-id="ec927-147">If the configuration is an XML configuration file, the column is blank, because the configuration can update multiple objects.</span></span>|  
|<span data-ttu-id="ec927-148">**Целевое свойство**</span><span class="sxs-lookup"><span data-stu-id="ec927-148">**Target Property**</span></span>|<span data-ttu-id="ec927-149">Имя свойства.</span><span class="sxs-lookup"><span data-stu-id="ec927-149">The name of the property.</span></span> <span data-ttu-id="ec927-150">Если конфигурация записывается в XML-файл конфигурации или таблицу SQL Server, столбец остается пустым, потому что конфигурация может обновлять несколько объектов.</span><span class="sxs-lookup"><span data-stu-id="ec927-150">If the configuration writes to an XML configuration file or a SQL Server table, the column is blank, because the configuration can update multiple objects.</span></span>|  
  
### <a name="to-create-a-package-configuration"></a><span data-ttu-id="ec927-151">Создание конфигурации пакета</span><span class="sxs-lookup"><span data-stu-id="ec927-151">To create a package configuration</span></span>  
  
1.  <span data-ttu-id="ec927-152">В среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]откройте проект служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , содержащий необходимый пакет.</span><span class="sxs-lookup"><span data-stu-id="ec927-152">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="ec927-153">Чтобы открыть пакет, дважды щелкните его в обозревателе решений.</span><span class="sxs-lookup"><span data-stu-id="ec927-153">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="ec927-154">В конструкторе служб [!INCLUDE[ssIS](../includes/ssis-md.md)] перейдите на вкладку **Поток управления**, **Поток данных**, **Обработчики события**или **Обозреватель пакетов** .</span><span class="sxs-lookup"><span data-stu-id="ec927-154">In [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, click the **Control Flow**, **Data Flow**, **Event Handler**, or **Package Explorer** tab.</span></span>  
  
4.  <span data-ttu-id="ec927-155">В меню **Службы SSIS** выберите команду **Конфигурации пакетов**.</span><span class="sxs-lookup"><span data-stu-id="ec927-155">On the **SSIS** menu, click **Package Configurations**.</span></span>  
  
5.  <span data-ttu-id="ec927-156">В диалоговом окне **Организатор конфигурации пакетов** выберите **Включить конфигурации пакетов**и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="ec927-156">In the **Package Configuration Organizer** dialog box, select **Enable package configurations**, and then click **Add**.</span></span>  
  
6.  <span data-ttu-id="ec927-157">На странице приветствия мастера настройки пакетов нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="ec927-157">On the welcome page of the Package Configuration Wizard page, click **Next**.</span></span>  
  
7.  <span data-ttu-id="ec927-158">На странице «Выбор типа конфигурации» следует выбрать тип конфигурации и установить свойства, относящиеся к этому типу конфигурации.</span><span class="sxs-lookup"><span data-stu-id="ec927-158">On the Select Configuration Type page, specify the configuration type, and then set the properties that are relevant to the configuration type.</span></span> <span data-ttu-id="ec927-159">Дополнительные сведения см. в статье [Справочник по пользовательскому интерфейсу мастера конфигурации пакетов](../../2014/integration-services/package-configuration-wizard-ui-reference.md).</span><span class="sxs-lookup"><span data-stu-id="ec927-159">For more information, see [Package Configuration Wizard UI Reference](../../2014/integration-services/package-configuration-wizard-ui-reference.md).</span></span>  
  
8.  <span data-ttu-id="ec927-160">На странице «Выбор свойств для экспорта» выберите свойства объектов пакетов, которые будут включены в конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="ec927-160">On the Select Properties to Export page, select the properties of package objects to include in the configuration.</span></span> <span data-ttu-id="ec927-161">Если тип конфигурации поддерживает только одно свойство, заголовком текущей страницы мастера будет «Выбор целевого свойства».</span><span class="sxs-lookup"><span data-stu-id="ec927-161">If the configuration type supports only one property, the title of this wizard page is Select Target Property.</span></span> <span data-ttu-id="ec927-162">Дополнительные сведения см. в статье [Справочник по пользовательскому интерфейсу мастера конфигурации пакетов](../../2014/integration-services/package-configuration-wizard-ui-reference.md).</span><span class="sxs-lookup"><span data-stu-id="ec927-162">For more information, see [Package Configuration Wizard UI Reference](../../2014/integration-services/package-configuration-wizard-ui-reference.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ec927-163">Только конфигурации типов **XML-файл конфигурации** и **SQL Server** поддерживают включение нескольких свойств в конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="ec927-163">Only the **XML Configuration File** and **SQL Server** configuration types support including multiple properties in a configuration.</span></span>  
  
9. <span data-ttu-id="ec927-164">На странице "Завершение работы мастера" введите имя конфигурации и нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="ec927-164">On the Completing the Wizard page, type the name of the configuration, and then click **Finish**.</span></span>  
  
10. <span data-ttu-id="ec927-165">Просмотрите конфигурацию в диалоговом окне **Организатор конфигураций пакетов** .</span><span class="sxs-lookup"><span data-stu-id="ec927-165">View the configuration in the **Package Configuration Organizer** dialog box.</span></span>  
  
11. <span data-ttu-id="ec927-166">Щелкните **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="ec927-166">Click **Close**.</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="ec927-167">Внешние ресурсы</span><span class="sxs-lookup"><span data-stu-id="ec927-167">External Resources</span></span>  
  
-   <span data-ttu-id="ec927-168">Техническая статья [Understanding Integration Services Package Configurations](https://go.microsoft.com/fwlink/?LinkId=165643)(Основные сведения о конфигурации пакетов служб Integration Services) на сайте msdn.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="ec927-168">Technical article, [Understanding Integration Services Package Configurations](https://go.microsoft.com/fwlink/?LinkId=165643), on msdn.microsoft.com</span></span>  
  
-   <span data-ttu-id="ec927-169">Запись блога, [Создание пакетов в конфигурациях пакетов кода](https://go.microsoft.com/fwlink/?LinkId=217663)на www.sqlis.com.</span><span class="sxs-lookup"><span data-stu-id="ec927-169">Blog entry, [Creating packages in code - Package Configurations](https://go.microsoft.com/fwlink/?LinkId=217663), on www.sqlis.com.</span></span>  
  
-   <span data-ttu-id="ec927-170">Запись блога, [Пример API — программное добавление файла конфигурации в пакет](https://go.microsoft.com/fwlink/?LinkId=217664)на blogs.MSDN.com.</span><span class="sxs-lookup"><span data-stu-id="ec927-170">Blog entry, [API Sample - Programmatically add a configuration file to a package](https://go.microsoft.com/fwlink/?LinkId=217664), on blogs.msdn.com.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec927-171">См. также:</span><span class="sxs-lookup"><span data-stu-id="ec927-171">See Also</span></span>  
 <span data-ttu-id="ec927-172">[Конфигурации пакетов](../../2014/integration-services/package-configurations.md) </span><span class="sxs-lookup"><span data-stu-id="ec927-172">[Package Configurations](../../2014/integration-services/package-configurations.md) </span></span>  
 <span data-ttu-id="ec927-173">[Развертывание пакетов &#40;&#41;SSIS](packages/legacy-package-deployment-ssis.md) </span><span class="sxs-lookup"><span data-stu-id="ec927-173">[Package Deployment &#40;SSIS&#41;](packages/legacy-package-deployment-ssis.md) </span></span>  
 [<span data-ttu-id="ec927-174">Программная работа с переменными</span><span class="sxs-lookup"><span data-stu-id="ec927-174">Working with Variables Programmatically</span></span>](building-packages-programmatically/working-with-variables-programmatically.md)  
  
  
