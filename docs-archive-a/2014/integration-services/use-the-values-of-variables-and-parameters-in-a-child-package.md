---
title: Использование значений переменных и параметров в дочернем пакете | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- variables [Integration Services], passing between packages
- configurations [Integration Services]
- packages [Integration Services], configurations
- variables [Integration Services], adding
ms.assetid: 9b939edb-4e17-48e5-8428-855beb10049c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 28561db91e5e924d8b25f9c7be7a4a51c6c315ab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666122"
---
# <a name="use-the-values-of-variables-and-parameters-in-a-child-package"></a><span data-ttu-id="41a00-102">Использование значений переменных и параметров в дочернем пакете</span><span class="sxs-lookup"><span data-stu-id="41a00-102">Use the Values of Variables and Parameters in a Child Package</span></span>
  <span data-ttu-id="41a00-103">Данная процедура описывает создание конфигурации пакета, которая использует тип конфигурации родительской переменной.</span><span class="sxs-lookup"><span data-stu-id="41a00-103">This procedure describes how to create a package configuration that uses the parent variable configuration type.</span></span> <span data-ttu-id="41a00-104">Данный тип конфигурации, позволяет дочернему пакету, который запускается из родительского, получить доступ к переменной в родительском элементе.</span><span class="sxs-lookup"><span data-stu-id="41a00-104">This configuration type enables a child package that is run from a parent package to access a variable in the parent.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="41a00-105">Чтобы передать значения в дочерний пакет, можно настроить задачу «Выполнение пакета» так, чтобы значения стали доступны для дочернего пакета. Для этого переменные, параметры родительского пакета, либо параметры проекта необходимо сопоставить с параметрами дочернего пакета.</span><span class="sxs-lookup"><span data-stu-id="41a00-105">You can also pass values to a child package by configuring the Execute Package Task to map parent package variables or parameters, or project parameters, to child package parameters.</span></span> <span data-ttu-id="41a00-106">Дополнительные сведения см. в статье [Execute Package Task](control-flow/execute-package-task.md).</span><span class="sxs-lookup"><span data-stu-id="41a00-106">For more information, see [Execute Package Task](control-flow/execute-package-task.md).</span></span>  
  
 <span data-ttu-id="41a00-107">Нет необходимости создавать переменные в родительских пакетах до создания пакета конфигурации в дочернем пакете.</span><span class="sxs-lookup"><span data-stu-id="41a00-107">It is not necessary to create the variable in the parent package before you create the package configuration in the child package.</span></span> <span data-ttu-id="41a00-108">Можно добавить переменные в родительский пакет в любое время, но нужно использовать правильное имя родительской переменной в конфигурации пакета.</span><span class="sxs-lookup"><span data-stu-id="41a00-108">You can add the variable to the parent package at any time, but you must use the exact name of the parent variable in the package configuration.</span></span> <span data-ttu-id="41a00-109">Тем не менее перед созданием конфигурации родительской переменной в дочернем пакете должна быть переменная, изменяемая конфигурацией.</span><span class="sxs-lookup"><span data-stu-id="41a00-109">However, before you can create a parent variable configuration, there must be an existing variable in the child package that the configuration can update.</span></span> <span data-ttu-id="41a00-110">Дополнительные сведения о добавлении и настройке переменных см. в разделе [Добавление, удаление и изменение области определяемой пользователем переменной в пакете](../../2014/integration-services/add-delete-change-scope-of-user-defined-variable-in-a-package.md).</span><span class="sxs-lookup"><span data-stu-id="41a00-110">For more information about adding and configuring variables, see [Add, Delete, Change Scope of User-Defined Variable in a Package](../../2014/integration-services/add-delete-change-scope-of-user-defined-variable-in-a-package.md).</span></span>  
  
 <span data-ttu-id="41a00-111">Область видимости переменной родительского пакета, которая используется в конфигурации родительской переменной, может быть установлена в задаче «Выполнение пакета», в контейнере задачи или в пакете.</span><span class="sxs-lookup"><span data-stu-id="41a00-111">The scope of the variable in the parent package that is used in a parent variable configuration can be set to the Execute Package task, to the container that has the task, or to the package.</span></span> <span data-ttu-id="41a00-112">Если в пакете имеется несколько переменных с одним именем, используется переменная, наиболее близкая к области задачи «Выполнение пакета».</span><span class="sxs-lookup"><span data-stu-id="41a00-112">If multiple variables with the same name are defined in a package, the variable that is closest in scope to the Execute Package task is used.</span></span> <span data-ttu-id="41a00-113">Ближайшей областью к задаче «Выполнение пакета» является сама задача.</span><span class="sxs-lookup"><span data-stu-id="41a00-113">The closest scope to the Execute Package task is the task itself.</span></span>  
  
### <a name="to-add-a-variable-to-a-parent-package"></a><span data-ttu-id="41a00-114">Добавление переменной в родительский пакет</span><span class="sxs-lookup"><span data-stu-id="41a00-114">To add a variable to a parent package</span></span>  
  
1.  <span data-ttu-id="41a00-115">В среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]откройте проект служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , содержащий пакет, к которому нужно добавить переменную для передачи в дочерний пакет.</span><span class="sxs-lookup"><span data-stu-id="41a00-115">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package to which you want to add a variable to pass to a child package.</span></span>  
  
2.  <span data-ttu-id="41a00-116">Чтобы открыть пакет, дважды щелкните его в обозревателе решений.</span><span class="sxs-lookup"><span data-stu-id="41a00-116">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="41a00-117">Для определения области переменной в конструкторе служб [!INCLUDE[ssIS](../includes/ssis-md.md)] выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="41a00-117">In [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, to define the scope of the variable, do one of the following:</span></span>  
  
    -   <span data-ttu-id="41a00-118">Чтобы установить в качестве области область пакета, щелкните в любом месте области конструктора на вкладке **Поток управления** .</span><span class="sxs-lookup"><span data-stu-id="41a00-118">To set the scope to the package, click anywhere on the design surface of the **Control Flow** tab.</span></span>  
  
    -   <span data-ttu-id="41a00-119">Чтобы установить в качестве области родительский контейнер задачи «Выполнение пакета», щелкните этот контейнер.</span><span class="sxs-lookup"><span data-stu-id="41a00-119">To set the scope to a parent container of the Execute Package task, click the container.</span></span>  
  
    -   <span data-ttu-id="41a00-120">Для настройки области задачи «Выполнение пакета» щелкните задачу.</span><span class="sxs-lookup"><span data-stu-id="41a00-120">To set the scope to the Execute Package task, click the task.</span></span>  
  
4.  <span data-ttu-id="41a00-121">Добавьте и настройте переменную.</span><span class="sxs-lookup"><span data-stu-id="41a00-121">Add and configure a variable.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="41a00-122">Выберите тип данных, совместимый с данными, которые хранятся в переменной.</span><span class="sxs-lookup"><span data-stu-id="41a00-122">Select a data type that is compatible with the data that the variable will store.</span></span>  
  
5.  <span data-ttu-id="41a00-123">Чтобы сохранить обновленный пакет, выберите пункт **Сохранить выбранные элементы** в меню **Файл** .</span><span class="sxs-lookup"><span data-stu-id="41a00-123">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
### <a name="to-add-a-variable-to-a-child-package"></a><span data-ttu-id="41a00-124">Добавление переменной в дочерний пакет</span><span class="sxs-lookup"><span data-stu-id="41a00-124">To add a variable to a child package</span></span>  
  
1.  <span data-ttu-id="41a00-125">В среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]откройте проект служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] с пакетом, в который необходимо вставить конфигурацию родительской переменной.</span><span class="sxs-lookup"><span data-stu-id="41a00-125">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package to which you want to add a parent variable configuration.</span></span>  
  
2.  <span data-ttu-id="41a00-126">Чтобы открыть пакет, дважды щелкните его в обозревателе решений.</span><span class="sxs-lookup"><span data-stu-id="41a00-126">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="41a00-127">Чтобы установить в качестве области область пакета, щелкните в любом месте конструктора служб [!INCLUDE[ssIS](../includes/ssis-md.md)] на вкладке **Поток управления** .</span><span class="sxs-lookup"><span data-stu-id="41a00-127">In [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, to set the scope to the package, click anywhere on the design surface of the **Control Flow** tab.</span></span>  
  
4.  <span data-ttu-id="41a00-128">Добавьте и настройте переменную.</span><span class="sxs-lookup"><span data-stu-id="41a00-128">Add and configure a variable.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="41a00-129">Выберите тип данных, совместимый с данными, которые хранятся в переменной.</span><span class="sxs-lookup"><span data-stu-id="41a00-129">Select a data type that is compatible with the data that the variable will store.</span></span>  
  
5.  <span data-ttu-id="41a00-130">Чтобы сохранить обновленный пакет, выберите пункт **Сохранить выбранные элементы** в меню **Файл** .</span><span class="sxs-lookup"><span data-stu-id="41a00-130">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
### <a name="to-add-a-parent-package-configuration-to-a-child-package"></a><span data-ttu-id="41a00-131">Добавление конфигурации родительского пакета в дочерний пакет</span><span class="sxs-lookup"><span data-stu-id="41a00-131">To add a parent package configuration to a child package</span></span>  
  
1.  <span data-ttu-id="41a00-132">Если дочерний пакет еще не открыт, откройте его в среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="41a00-132">If it is not already open, open the child package in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="41a00-133">Щелкните в любом месте вкладки **Поток управления** области конструктора.</span><span class="sxs-lookup"><span data-stu-id="41a00-133">Click anywhere on the design surface of the **Control Flow** tab.</span></span>  
  
3.  <span data-ttu-id="41a00-134">В меню **Службы SSIS** выберите команду **Конфигурации пакетов**.</span><span class="sxs-lookup"><span data-stu-id="41a00-134">On the **SSIS** menu, click **Package Configurations**.</span></span>  
  
4.  <span data-ttu-id="41a00-135">В диалоговом окне **Организатор конфигурации пакетов** выберите **Включить конфигурации пакетов**и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="41a00-135">In the **Package Configuration Organizer** dialog box, select **Enable package configuration**, and then click **Add**.</span></span>  
  
5.  <span data-ttu-id="41a00-136">На странице приветствия мастера настройки пакета нажмите кнопку **Далее.**</span><span class="sxs-lookup"><span data-stu-id="41a00-136">On the welcome page of the Package Configuration Wizard, click **Next.**</span></span>  
  
6.  <span data-ttu-id="41a00-137">На странице «Выбор типа конфигурации» в списке **Тип конфигурации** выберите **Переменная родительского пакета** и выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="41a00-137">On the Select Configuration Type page, in the **Configuration type** list, select **Parent package variable** and do one of the following:</span></span>  
  
    -   <span data-ttu-id="41a00-138">Выберите **Указать параметры конфигурации непосредственно**, затем в поле **Родительская переменная** введите имя переменной родительского пакета для использования в конфигурации.</span><span class="sxs-lookup"><span data-stu-id="41a00-138">Select **Specify configuration settings directly**, and then in the **Parent variable** box, provide the name of the variable in the parent package to use in the configuration.</span></span>  
  
        > [!IMPORTANT]  
        >  <span data-ttu-id="41a00-139">В именах переменных учитывается регистр.</span><span class="sxs-lookup"><span data-stu-id="41a00-139">Variable names are case sensitive.</span></span>  
  
    -   <span data-ttu-id="41a00-140">Выберите **Сведения о расположении файла конфигурации хранятся в переменной среды** , затем в узле **Список переменных среды**выберите переменную окружения, содержащую имя переменной.</span><span class="sxs-lookup"><span data-stu-id="41a00-140">Select or **Configuration location is stored in an environment variable,** and then in the **Environment variable list**, select the environmentvariable that contains the name of the variable.</span></span>  
  
7.  <span data-ttu-id="41a00-141">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="41a00-141">Click **Next**.</span></span>  
  
8.  <span data-ttu-id="41a00-142">В окне «Выбор целевого свойства» разверните узел **Переменная** , разверните узел **Свойства** переменной для настройки и выберите свойство для установки в конфигурации.</span><span class="sxs-lookup"><span data-stu-id="41a00-142">On the Select Target Property page, expand the **Variable** node, and expand the **Properties** node of the variable to configure, and then click the property to be set by the configuration.</span></span>  
  
9. <span data-ttu-id="41a00-143">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="41a00-143">Click **Next**.</span></span>  
  
10. <span data-ttu-id="41a00-144">На странице «Завершение работы мастера» при необходимости измените имя конфигурации и просмотрите сведения о конфигурации.</span><span class="sxs-lookup"><span data-stu-id="41a00-144">On the Completing the Wizard page, optionally, modify the default name of the configuration and review the configuration information.</span></span>  
  
11. <span data-ttu-id="41a00-145">Нажмите **Готово** , чтобы завершить работу мастера и вернуться к диалоговому окну **Организатор конфигураций пакетов** .</span><span class="sxs-lookup"><span data-stu-id="41a00-145">Click **Finish** to complete the wizard and return to the **Package Configuration Organizer** dialog box.</span></span>  
  
12. <span data-ttu-id="41a00-146">В диалоговом окне **Организатор конфигураций пакетов** в поле **Конфигурация** перечислены новые конфигурации.</span><span class="sxs-lookup"><span data-stu-id="41a00-146">In the **Package Configuration Organizer** dialog box, the **Configuration** box lists the new configuration.</span></span>  
  
13. <span data-ttu-id="41a00-147">Щелкните **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="41a00-147">Click **Close**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41a00-148">См. также:</span><span class="sxs-lookup"><span data-stu-id="41a00-148">See Also</span></span>  
 <span data-ttu-id="41a00-149">[Конфигурации пакетов](../../2014/integration-services/package-configurations.md) </span><span class="sxs-lookup"><span data-stu-id="41a00-149">[Package Configurations](../../2014/integration-services/package-configurations.md) </span></span>  
 <span data-ttu-id="41a00-150">[Создание конфигураций пакетов](../../2014/integration-services/create-package-configurations.md) </span><span class="sxs-lookup"><span data-stu-id="41a00-150">[Create Package Configurations](../../2014/integration-services/create-package-configurations.md) </span></span>  
 <span data-ttu-id="41a00-151">[Переменные в службах Integration Services (SSIS)](integration-services-ssis-variables.md) </span><span class="sxs-lookup"><span data-stu-id="41a00-151">[Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md) </span></span>  
 [<span data-ttu-id="41a00-152">Использование переменных в пакетах</span><span class="sxs-lookup"><span data-stu-id="41a00-152">Use Variables in Packages</span></span>](../../2014/integration-services/use-variables-in-packages.md)  
  
  
