---
title: Шаг 2. Активация и настройка конфигураций пакетов | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 005218ab-8dd5-48e9-a185-6bc60cd43a7a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a804efcd84ebe563a13f61443fe19096788ca809
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657150"
---
# <a name="step-2-enabling-and-configuring-package-configurations"></a><span data-ttu-id="8aa89-102">Шаг 2. Активация и настройка конфигурации пакетов</span><span class="sxs-lookup"><span data-stu-id="8aa89-102">Step 2: Enabling and Configuring Package Configurations</span></span>
  <span data-ttu-id="8aa89-103">В этой задаче вы преобразуете проект в модель развертывания пакета и включите конфигурации пакетов с помощью мастера настройки пакета.</span><span class="sxs-lookup"><span data-stu-id="8aa89-103">In this task, you will convert the project to the Package Deployment Model and enable package configurations using the Package Configuration Wizard.</span></span> <span data-ttu-id="8aa89-104">Этот мастер будет использован для создания файла конфигурации в формате XML, который содержит параметры конфигурации для свойства `Directory` контейнера «цикл по каждому элементу».</span><span class="sxs-lookup"><span data-stu-id="8aa89-104">You will use this wizard to generate an XML configuration file that contains configuration settings for the `Directory` property of the Foreach Loop container.</span></span> <span data-ttu-id="8aa89-105">Значение свойства Directory содержится в новой переменной уровня пакета, обновление которой можно осуществлять в процессе выполнения.</span><span class="sxs-lookup"><span data-stu-id="8aa89-105">The value of the Directory property is supplied by a new package-level variable that you can update at run time.</span></span> <span data-ttu-id="8aa89-106">Кроме того, будет заполнена новая папка с образцами данных для использования при проверке.</span><span class="sxs-lookup"><span data-stu-id="8aa89-106">Additionally, you will populate a new sample data folder to use during testing.</span></span>  
  
### <a name="to-create-a-new-package-level-variable-mapped-to-the-directory-property"></a><span data-ttu-id="8aa89-107">Создание новой переменной уровня пакета, сопоставленной со свойством Directory</span><span class="sxs-lookup"><span data-stu-id="8aa89-107">To create a new package-level variable mapped to the Directory property</span></span>  
  
1.  <span data-ttu-id="8aa89-108">Щелкните фон вкладки **Поток управления** в конструкторе служб [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8aa89-108">Click the background of the **Control Flow** tab in [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="8aa89-109">Этим устанавливается область действия переменной, которая создается для пакета.</span><span class="sxs-lookup"><span data-stu-id="8aa89-109">This sets the scope for the variable you will create to the package.</span></span>  
  
2.  <span data-ttu-id="8aa89-110">В меню служб [!INCLUDE[ssIS](../includes/ssis-md.md)] выберите пункт **Переменные**.</span><span class="sxs-lookup"><span data-stu-id="8aa89-110">On the [!INCLUDE[ssIS](../includes/ssis-md.md)] menu, select **Variables**.</span></span>  
  
3.  <span data-ttu-id="8aa89-111">В окне **Переменные** щелкните значок Добавить переменную .</span><span class="sxs-lookup"><span data-stu-id="8aa89-111">In the **Variables** window, click the Add Variable icon.</span></span>  
  
4.  <span data-ttu-id="8aa89-112">В поле **Имя** введите **varFolderName**.</span><span class="sxs-lookup"><span data-stu-id="8aa89-112">In the **Name** box, type **varFolderName**.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="8aa89-113">В именах переменных учитывается регистр.</span><span class="sxs-lookup"><span data-stu-id="8aa89-113">Variable names are case sensitive.</span></span>  
  
5.  <span data-ttu-id="8aa89-114">Убедитесь, что в поле **область** указано имя пакета, занятие 5.</span><span class="sxs-lookup"><span data-stu-id="8aa89-114">Verify that the **Scope** box shows the name of the package, Lesson 5.</span></span>  
  
6.  <span data-ttu-id="8aa89-115">В поле **Тип данных** переменной `varFolderName` установите значение **String**.</span><span class="sxs-lookup"><span data-stu-id="8aa89-115">Set the value of the **Data Type** box of the `varFolderName` variable to **String**.</span></span>  
  
7.  <span data-ttu-id="8aa89-116">Вернитесь на вкладку **Поток управления** и дважды щелкните контейнер **Цикл по каждому файлу в папке** .</span><span class="sxs-lookup"><span data-stu-id="8aa89-116">Return to the **Control Flow** tab and double-click the **Foreach File in Folder** container.</span></span>  
  
8.  <span data-ttu-id="8aa89-117">На странице **коллекция** в **редакторе циклов по каждому**элементу щелкните **выражения**, а затем нажмите кнопку с многоточием **(...)**.</span><span class="sxs-lookup"><span data-stu-id="8aa89-117">On the **Collection** page of the **Foreach Loop Editor**, click **Expressions**, and then click the ellipsis button **(...)**.</span></span>  
  
9. <span data-ttu-id="8aa89-118">В **редакторе выражений свойств**щелкните список **свойств** и выберите `Directory` .</span><span class="sxs-lookup"><span data-stu-id="8aa89-118">In the **Property Expressions Editor**, click in the **Property** list, and select `Directory`.</span></span>  
  
10. <span data-ttu-id="8aa89-119">В поле **выражение** нажмите кнопку с многоточием **(...)**.</span><span class="sxs-lookup"><span data-stu-id="8aa89-119">In the **Expression** box, click the ellipsis button **(...)**.</span></span>  
  
11. <span data-ttu-id="8aa89-120">В окне **Построитель выражений**раскройте папку "Переменные" и перетащите переменную **User::varFolderName** в поле **Выражение** .</span><span class="sxs-lookup"><span data-stu-id="8aa89-120">In the **Expression Builder**, expand the Variables folder, and drag the variable **User::varFolderName** to the **Expression** box.</span></span>  
  
12. <span data-ttu-id="8aa89-121">Нажмите кнопку **ОК** для выхода из окна **Построитель выражений**.</span><span class="sxs-lookup"><span data-stu-id="8aa89-121">Click **OK** to exit the **Expression Builder**.</span></span>  
  
13. <span data-ttu-id="8aa89-122">Нажмите кнопку **ОК** для выхода из окна **Редактор выражений свойств**.</span><span class="sxs-lookup"><span data-stu-id="8aa89-122">Click **OK** to exit the **Property Expressions Editor**.</span></span>  
  
14. <span data-ttu-id="8aa89-123">Нажмите кнопку **ОК** , чтобы закрыть **редактор циклов по каждому элементу**.</span><span class="sxs-lookup"><span data-stu-id="8aa89-123">Click **OK** to exit the **Foreach Loop Editor**.</span></span>  
  
### <a name="to-enable-package-configurations"></a><span data-ttu-id="8aa89-124">Включение конфигураций пакетов</span><span class="sxs-lookup"><span data-stu-id="8aa89-124">To enable package configurations</span></span>  
  
1.  <span data-ttu-id="8aa89-125">В **меню Проект**выберите команду **преобразовать в модель развертывания пакета**.</span><span class="sxs-lookup"><span data-stu-id="8aa89-125">On the **Project Menu**, click **Convert to Package Deployment Model**.</span></span>  
  
2.  <span data-ttu-id="8aa89-126">Нажмите кнопку **ОК** в окне предупреждения и после завершения преобразования нажмите кнопку **ОК** в диалоговом окне **Преобразование в модель развертывания пакета** .</span><span class="sxs-lookup"><span data-stu-id="8aa89-126">Click **OK** on the warning prompt and, once the conversion is complete, click **OK** on the **Convert to Package Deployment Model** dialog.</span></span>  
  
3.  <span data-ttu-id="8aa89-127">Щелкните фон вкладки **Поток управления** в конструкторе служб [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8aa89-127">Click the background of the **Control Flow** tab in [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span>  
  
4.  <span data-ttu-id="8aa89-128">В меню **Службы SSIS** выберите команду **Конфигурации пакетов**.</span><span class="sxs-lookup"><span data-stu-id="8aa89-128">On the **SSIS** menu, click **Package Configurations**.</span></span>  
  
5.  <span data-ttu-id="8aa89-129">В диалоговом окне **Организатор конфигураций пакетов** выберите **Включить конфигурации пакетов**и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="8aa89-129">In the **Package Configurations Organizer** dialog box, select **Enable Package Configurations**, and then click **Add**.</span></span>  
  
6.  <span data-ttu-id="8aa89-130">На странице приветствия мастера настройки пакета нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8aa89-130">On the welcome page of the Package Configuration Wizard, click **Next**.</span></span>  
  
7.  <span data-ttu-id="8aa89-131">Убедитесь в том, что на странице **Выбор типа конфигурации** свойство **Тип конфигурации** имеет значение **XML-файл конфигурации**.</span><span class="sxs-lookup"><span data-stu-id="8aa89-131">On the **Select Configuration Type** page, verify that the **Configuration type** is set to **XML configuration file**.</span></span>  
  
8.  <span data-ttu-id="8aa89-132">На странице **Выбор типа конфигурации** нажмите кнопку **Обзор**.</span><span class="sxs-lookup"><span data-stu-id="8aa89-132">On the **Select Configuration Type** page, click **Browse**.</span></span>  
  
9. <span data-ttu-id="8aa89-133">По умолчанию в диалоговом окне **Выберите расположение файла конфигурации** будет открыта папка проекта.</span><span class="sxs-lookup"><span data-stu-id="8aa89-133">By default, the **Select Configuration File Location** dialog box will open to the project folder.</span></span>  
  
10. <span data-ttu-id="8aa89-134">В диалоговом окне **Выберите расположение файла конфигурации** в поле **Имя файла** введите **SSISTutorial**и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="8aa89-134">In the **Select Configuration File Location** dialog box, for **File name** type **SSISTutorial**, and then click **Save**.</span></span>  
  
11. <span data-ttu-id="8aa89-135">На странице **Выбор типа конфигурации** нажмите кнопку **Далее.**</span><span class="sxs-lookup"><span data-stu-id="8aa89-135">On the **Select Configuration Type** page, click **Next.**</span></span>  
  
12. <span data-ttu-id="8aa89-136">На странице **Выбор свойств для экспорта** в области **объекты** разверните узел **переменные**, разверните узел **VarFolderName**, разверните узел **Свойства**и выберите **значение**.</span><span class="sxs-lookup"><span data-stu-id="8aa89-136">On the **Select Properties to Export** page, in the **Objects** pane, expand **Variables**, expand **varFolderName**, expand **Properties**, and then select **Value**.</span></span>  
  
13. <span data-ttu-id="8aa89-137">На странице **Выбор свойств для экспорта** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8aa89-137">On the **Select Properties to Export** page, click **Next**.</span></span>  
  
14. <span data-ttu-id="8aa89-138">На странице **Завершение работы мастера** введите имя конфигурации, например **Конфигурация свойства "Каталог" для учебника по службам SSIS**.</span><span class="sxs-lookup"><span data-stu-id="8aa89-138">On the **Completing the Wizard** page, type a configuration name for the configuration, such as **SSIS Tutorial Directory configuration**.</span></span> <span data-ttu-id="8aa89-139">Это имя будет отображаться в диалоговом окне **Организатор конфигураций пакетов** .</span><span class="sxs-lookup"><span data-stu-id="8aa89-139">This is the configuration name that is displayed in the **Package Configuration Organizer** dialog box.</span></span>  
  
15. <span data-ttu-id="8aa89-140">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="8aa89-140">Click **Finish**.</span></span>  
  
16. <span data-ttu-id="8aa89-141">Нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="8aa89-141">Click **Close**.</span></span>  
  
17. <span data-ttu-id="8aa89-142">Мастер создает файл конфигурации с именем SSISTutorial. dtsConfig, который содержит параметры конфигурации для `value` переменной, которая, в свою очередь, задает `Directory` свойство перечислителя.</span><span class="sxs-lookup"><span data-stu-id="8aa89-142">The wizard creates a configuration file, named SSISTutorial.dtsConfig, that contains configuration settings for the `value` of the variable that in turn sets the `Directory` property of the enumerator.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8aa89-143">Файл конфигурации обычно содержит множество данных о свойствах пакета, но в этом учебнике будут использованы только следующие сведения о конфигурации.</span><span class="sxs-lookup"><span data-stu-id="8aa89-143">A configuration file typically contains complex information about the package properties, but for this tutorial the only configuration information should be</span></span>  
    > <span data-ttu-id="8aa89-144"><Configuration ConfiguredType="Property"</span><span class="sxs-lookup"><span data-stu-id="8aa89-144"><Configuration ConfiguredType="Property"</span></span>  
    > <span data-ttu-id="8aa89-145">Path = "\Паккаже.вариаблес [пользователь:: varFolderName]. Properties [значение] "ValueType =" строка "\></span><span class="sxs-lookup"><span data-stu-id="8aa89-145">Path="\Package.Variables[User::varFolderName].Properties[Value]" ValueType="String"\></span></span>  
    >  \<ConfiguredValue>\</ConfiguredValue>  
    > <span data-ttu-id="8aa89-146">\</Configuration>.</span><span class="sxs-lookup"><span data-stu-id="8aa89-146">\</Configuration>.</span></span>  
  
### <a name="to-create-and-populate-a-new-sample-data-folder"></a><span data-ttu-id="8aa89-147">Создание и заполнение новой папки с образцами данных</span><span class="sxs-lookup"><span data-stu-id="8aa89-147">To create and populate a new sample data folder</span></span>  
  
1.  <span data-ttu-id="8aa89-148">В проводнике Windows на корневом уровне диска (например, C: \\ ) создайте новую папку с именем `New Sample Data` .</span><span class="sxs-lookup"><span data-stu-id="8aa89-148">In Windows Explorer, at the root level of your drive (for example, C:\\), create a new folder named `New Sample Data`.</span></span>  
  
2.  <span data-ttu-id="8aa89-149">Найдите образцы файлов на вашем компьютере и скопируйте три файла из папки.</span><span class="sxs-lookup"><span data-stu-id="8aa89-149">Locate the sample files on your computer and copy three of the files from the folder.</span></span>  
  
3.  <span data-ttu-id="8aa89-150">В `New Sample Data` папке вставьте скопированные файлы.</span><span class="sxs-lookup"><span data-stu-id="8aa89-150">In the `New Sample Data` folder, paste the copied files.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="8aa89-151">Следующая задача занятия</span><span class="sxs-lookup"><span data-stu-id="8aa89-151">Next Task in Lesson</span></span>  
 [<span data-ttu-id="8aa89-152">Шаг 3. Изменение значения конфигурации свойства Directory</span><span class="sxs-lookup"><span data-stu-id="8aa89-152">Step 3: Modifying the Directory Property Configuration Value</span></span>](lesson-5-3-modifying-the-directory-property-configuration-value.md)  
  
  
