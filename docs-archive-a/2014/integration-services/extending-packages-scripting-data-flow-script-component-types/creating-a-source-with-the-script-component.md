---
title: Создание источника с помощью компонента скрипта | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- Script component [Integration Services], source components
- output columns [Integration Services]
- sources [Integration Services], components
ms.assetid: 547c4179-ea82-4265-8c6f-04a2aa77a3c0
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7a352348f7f47157c5f2ec6d3ff01cea47de0ffb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664995"
---
# <a name="creating-a-source-with-the-script-component"></a><span data-ttu-id="24b7f-102">Создание источника с помощью компонента скрипта</span><span class="sxs-lookup"><span data-stu-id="24b7f-102">Creating a Source with the Script Component</span></span>
  <span data-ttu-id="24b7f-103">Компонент источника в потоке данных пакета служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] можно использовать для загрузки данных из источника данных для передачи в нижележащие преобразования и назначения.</span><span class="sxs-lookup"><span data-stu-id="24b7f-103">You use a source component in the data flow of an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package to load data from a data source to pass on to downstream transformations and destinations.</span></span> <span data-ttu-id="24b7f-104">Обычно подключение к источнику данных осуществляется через существующий диспетчер соединений.</span><span class="sxs-lookup"><span data-stu-id="24b7f-104">Ordinarily you connect to the data source through an existing connection manager.</span></span>

 <span data-ttu-id="24b7f-105">Общие сведения о компоненте скрипта см. в разделе [расширение потока данных с помощью компонента скрипта] (. /екстендинг-паккажес-скриптинг/дата-флов-скрипт-компонент/екстендинг-се-дата-флов-вис-се-скрипт-компонент.мд.</span><span class="sxs-lookup"><span data-stu-id="24b7f-105">For an overview of the Script component, see [Extending the Data Flow with the Script Component](../extending-packages-scripting/data-flow-script-component/extending-the-data-flow-with-the-script-component.md.</span></span>

 <span data-ttu-id="24b7f-106">Компонент скрипта и формируемый им код инфраструктуры значительно упрощают процесс создания пользовательских компонентов потока данных.</span><span class="sxs-lookup"><span data-stu-id="24b7f-106">The Script component and the infrastructure code that it generates for you simplify significantly the process of developing a custom data flow component.</span></span> <span data-ttu-id="24b7f-107">Однако, чтобы понять работу этого компонента скрипта, может потребоваться ознакомиться с шагами, связанными с разработкой пользовательского компонента потока данных.</span><span class="sxs-lookup"><span data-stu-id="24b7f-107">However, to understand how the Script component works, you may find it useful to read through the steps that are involved in developing a custom data flow component.</span></span> <span data-ttu-id="24b7f-108">См. раздел [Разработка пользовательского компонента потока данных](../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md) и особенно раздел [Разработка пользовательского компонента источника](../extending-packages-custom-objects-data-flow-types/developing-a-custom-source-component.md).</span><span class="sxs-lookup"><span data-stu-id="24b7f-108">See the section [Developing a Custom Data Flow Component](../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md), especially the topic [Developing a Custom Source Component](../extending-packages-custom-objects-data-flow-types/developing-a-custom-source-component.md).</span></span>

## <a name="getting-started-with-a-source-component"></a><span data-ttu-id="24b7f-109">Приступая к работе с компонентом источника</span><span class="sxs-lookup"><span data-stu-id="24b7f-109">Getting Started with a Source Component</span></span>
 <span data-ttu-id="24b7f-110">При добавлении компонента скрипта в область "Поток данных" конструктора служб [!INCLUDE[ssIS](../../includes/ssis-md.md)] открывается диалоговое окно **Выбор типа компонента скрипта** с приглашением выбрать скрипт источника, назначения или преобразования.</span><span class="sxs-lookup"><span data-stu-id="24b7f-110">When you add a Script component to the Data Flow pane of [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, the **Select Script Component Type** dialog box opens and prompts you to select a Source, Destination, or Transformation script.</span></span> <span data-ttu-id="24b7f-111">В этом диалоговом окне выберите скрипт **Источник**.</span><span class="sxs-lookup"><span data-stu-id="24b7f-111">In this dialog box, select **Source**.</span></span>

## <a name="configuring-a-source-component-in-metadata-design-mode"></a><span data-ttu-id="24b7f-112">Настройка компонента источника в режиме конструктора метаданных</span><span class="sxs-lookup"><span data-stu-id="24b7f-112">Configuring a Source Component in Metadata-Design Mode</span></span>
 <span data-ttu-id="24b7f-113">После выбора для создания компонента источника необходимо настроить этот компонент с помощью окна **Редактор преобразования "скрипт"** .</span><span class="sxs-lookup"><span data-stu-id="24b7f-113">After selecting to create a source component, you configure the component by using the **Script Transformation Editor**.</span></span> <span data-ttu-id="24b7f-114">Дополнительные сведения см. в разделе [Настройка компонента скрипта в редакторе компонента скрипта](../extending-packages-scripting/data-flow-script-component/configuring-the-script-component-in-the-script-component-editor.md).</span><span class="sxs-lookup"><span data-stu-id="24b7f-114">For more information, see [Configuring the Script Component in the Script Component Editor](../extending-packages-scripting/data-flow-script-component/configuring-the-script-component-in-the-script-component-editor.md).</span></span>

 <span data-ttu-id="24b7f-115">Компонент источника потока данных не имеет входов и поддерживает один или несколько выходов.</span><span class="sxs-lookup"><span data-stu-id="24b7f-115">A data flow source component has no inputs and supports one or more outputs.</span></span> <span data-ttu-id="24b7f-116">Настройка выходов для компонента представляет собой один из шагов, который должен быть выполнен в режиме конструктора метаданных с помощью окна **Редактор преобразования "скрипт"** до начала написания пользовательского скрипта.</span><span class="sxs-lookup"><span data-stu-id="24b7f-116">Configuring the outputs for the component is one of the steps that you must complete in metadata design mode, by using the **Script Transformation Editor**, before you write your custom script.</span></span>

 <span data-ttu-id="24b7f-117">Можно также указать язык скрипта, задавая свойство **ScriptLanguage** на странице **Скрипт** окна **Редактор преобразования "скрипт"** .</span><span class="sxs-lookup"><span data-stu-id="24b7f-117">You can also specify the script language by setting the **ScriptLanguage** property on the **Script** page of the **Script Transformation Editor**.</span></span>

> [!NOTE]
>  <span data-ttu-id="24b7f-118">Чтобы установить значение по умолчанию языка скрипта для компонентов скрипта и задач "Скрипт", воспользуйтесь параметром **Язык сценариев** на странице **Общие** диалогового окна **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="24b7f-118">To set the default script language for Script components and Script Tasks, use the **Scripting language** option on the **General** page of the **Options** dialog box.</span></span> <span data-ttu-id="24b7f-119">Дополнительные сведения см. в разделе [General Page](../general-page-of-integration-services-designers-options.md).</span><span class="sxs-lookup"><span data-stu-id="24b7f-119">For more information, see [General Page](../general-page-of-integration-services-designers-options.md).</span></span>

### <a name="adding-connection-managers"></a><span data-ttu-id="24b7f-120">Добавление диспетчеров соединений</span><span class="sxs-lookup"><span data-stu-id="24b7f-120">Adding Connection Managers</span></span>
 <span data-ttu-id="24b7f-121">Как правило, в компоненте источника используется существующий диспетчер соединений для подключения к источнику данных, из которого загружаются данные в поток данных.</span><span class="sxs-lookup"><span data-stu-id="24b7f-121">Ordinarily a source component uses an existing connection manager to connect to the data source from which it loads data into the data flow.</span></span> <span data-ttu-id="24b7f-122">На странице **Диспетчеры соединений** в **редакторе преобразования "Скрипт"** нажмите кнопку **Добавить**, чтобы добавить нужный диспетчер соединений.</span><span class="sxs-lookup"><span data-stu-id="24b7f-122">On the **Connection Managers** page of the **Script Transformation Editor**, click **Add** to add the appropriate connection manager.</span></span>

 <span data-ttu-id="24b7f-123">Но диспетчер соединений представляет собой всего лишь удобный модуль, который инкапсулирует и хранит информацию, необходимую для подключения к источнику данных конкретного типа.</span><span class="sxs-lookup"><span data-stu-id="24b7f-123">However, a connection manager is only a convenient unit that encapsulates and stores the information that it must have to connect to a data source of a particular type.</span></span> <span data-ttu-id="24b7f-124">Чтобы загрузить или сохранить конкретные данные, необходимо написать собственный пользовательский код, а также, возможно, открыть и закрыть соединение с источником данных.</span><span class="sxs-lookup"><span data-stu-id="24b7f-124">You must write your own custom code to load or save your data, and possibly to open and close the connection to the data source also.</span></span>

 <span data-ttu-id="24b7f-125">Общие сведения об использовании диспетчеров соединений в компоненте скрипта см. в разделе [Соединение с источниками данных в компоненте скрипта](../extending-packages-scripting/data-flow-script-component/connecting-to-data-sources-in-the-script-component.md).</span><span class="sxs-lookup"><span data-stu-id="24b7f-125">For general information about how to use connection managers with the Script component, see [Connecting to Data Sources in the Script Component](../extending-packages-scripting/data-flow-script-component/connecting-to-data-sources-in-the-script-component.md).</span></span>

 <span data-ttu-id="24b7f-126">Дополнительные сведения о странице **Диспетчеры соединений** окна **Редактор преобразования "Скрипт"** см. в разделе [Редактор преобразования "Скрипт" (страница "Диспетчеры соединений")](../script-transformation-editor-connection-managers-page.md).</span><span class="sxs-lookup"><span data-stu-id="24b7f-126">For more information about the **Connection Managers** page of the **Script Transformation Editor**, see [Script Transformation Editor &#40;Connection Managers Page&#41;](../script-transformation-editor-connection-managers-page.md).</span></span>

### <a name="configuring-outputs-and-output-columns"></a><span data-ttu-id="24b7f-127">Настройка выходов и выходных столбцов</span><span class="sxs-lookup"><span data-stu-id="24b7f-127">Configuring Outputs and Output Columns</span></span>
 <span data-ttu-id="24b7f-128">Компонент источника не имеет входов и поддерживает один или несколько выходов.</span><span class="sxs-lookup"><span data-stu-id="24b7f-128">A source component has no inputs and supports one or more outputs.</span></span> <span data-ttu-id="24b7f-129">На странице **Входы и выходы** окна **Редактор преобразования "скрипт"** по умолчанию был создан один выход, но не созданы какие-либо выходные столбцы.</span><span class="sxs-lookup"><span data-stu-id="24b7f-129">On the **Inputs and Outputs** page of the **Script Transformation Editor**, a single output has been created by default, but no output columns have been created.</span></span> <span data-ttu-id="24b7f-130">На этой странице редактора может понадобиться настроить следующие элементы.</span><span class="sxs-lookup"><span data-stu-id="24b7f-130">On this page of the editor, you may need or want to configure the following items.</span></span>

-   <span data-ttu-id="24b7f-131">Необходимо вручную добавить и настроить выходные столбцы для каждого выхода.</span><span class="sxs-lookup"><span data-stu-id="24b7f-131">You must add and configure output columns manually for each output.</span></span> <span data-ttu-id="24b7f-132">Выберите папку "Выходные столбцы" для каждого выхода, а затем используйте кнопки **Добавить столбец** и **Удалить столбец**, чтобы управлять выходными столбцами для каждого выхода компонента источника.</span><span class="sxs-lookup"><span data-stu-id="24b7f-132">Select the Output Columns folder for each output, and then use the **Add Column** and **Remove Column** buttons to manage the output columns for each output of the source component.</span></span> <span data-ttu-id="24b7f-133">В дальнейшем можно будет ссылаться на выходные столбцы в скрипте по именам, присвоенным здесь, используя свойства типизированного метода доступа, созданные в автоматически сформированном коде.</span><span class="sxs-lookup"><span data-stu-id="24b7f-133">Later, you will refer to the output columns in your script by the names that you assign here, by using the typed accessor properties created for you in the auto-generated code.</span></span>

-   <span data-ttu-id="24b7f-134">Может потребоваться создать один или несколько дополнительных выводов, таких как эмулируемый вывод ошибок для строк, содержащих непредвиденные значения.</span><span class="sxs-lookup"><span data-stu-id="24b7f-134">You may want to create one or more additional outputs, such as a simulated error output for rows that contain unexpected values.</span></span> <span data-ttu-id="24b7f-135">Используйте кнопки **Добавить выход** и **Удалить выход** для управления выходами компонента источника.</span><span class="sxs-lookup"><span data-stu-id="24b7f-135">Use the **Add Output** and **Remove Output** buttons to manage the outputs of the source component.</span></span> <span data-ttu-id="24b7f-136">Все входные строки направляются во все доступные выходы, если только не задано идентичное ненулевое значение для свойства `ExclusionGroup` тех выходов, куда планируется направить каждую строку только для одного из выходов, использующих одно и то же значение `ExclusionGroup`.</span><span class="sxs-lookup"><span data-stu-id="24b7f-136">All input rows are directed to all available outputs unless you also specify an identical non-zero value for the `ExclusionGroup` property of those outputs where you intend to direct each row to only one of the outputs that share the same `ExclusionGroup` value.</span></span> <span data-ttu-id="24b7f-137">Конкретное целочисленное значение, выбранное для идентификации группы `ExclusionGroup`, не имеет значения.</span><span class="sxs-lookup"><span data-stu-id="24b7f-137">The particular integer value selected to identify the `ExclusionGroup` is not significant.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="24b7f-138">Также можно использовать ненулевое значение для свойства `ExclusionGroup` с единственным выходом, если не нужно выводить все строки.</span><span class="sxs-lookup"><span data-stu-id="24b7f-138">You can also use a non-zero `ExclusionGroup` property value with a single output when you do not want to output all rows.</span></span> <span data-ttu-id="24b7f-139">Однако в этом случае необходимо явно вызывать метод **DirectRowTo\<outputbuffer>** для каждой строки, которую следует отправить на выход.</span><span class="sxs-lookup"><span data-stu-id="24b7f-139">In this case, however, you must explicitly call the **DirectRowTo\<outputbuffer>** method for each row that you want to send to the output.</span></span>

-   <span data-ttu-id="24b7f-140">Может потребоваться присвоить выходам понятные имена.</span><span class="sxs-lookup"><span data-stu-id="24b7f-140">You may want to assign a friendly name to the outputs.</span></span> <span data-ttu-id="24b7f-141">В дальнейшем можно будет ссылаться на выходы по их именам в скрипте, используя свойства типизированного метода доступа, созданные в автоматически сформированном коде.</span><span class="sxs-lookup"><span data-stu-id="24b7f-141">Later, you will refer to the outputs by their names in your script, by using the typed accessor properties created for you in the auto-generated code.</span></span>

-   <span data-ttu-id="24b7f-142">Обычно несколько выходов в одной и той же группе `ExclusionGroup` имеют одинаковые выходные столбцы.</span><span class="sxs-lookup"><span data-stu-id="24b7f-142">Ordinarily multiple outputs in the same `ExclusionGroup` have the same output columns.</span></span> <span data-ttu-id="24b7f-143">Однако, если создается моделируемый вывод ошибок, может потребоваться добавить дополнительные столбцы для хранения сведений об ошибках.</span><span class="sxs-lookup"><span data-stu-id="24b7f-143">However, if you are creating a simulated error output, you may want to add more columns to store error information.</span></span> <span data-ttu-id="24b7f-144">Сведения об обработке ошибочных строк в подсистеме обработки потока данных см. в разделе [Использование выводов ошибок в компоненте потока данных](../extending-packages-custom-objects/data-flow/using-error-outputs-in-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="24b7f-144">For information about how the data flow engine processes error rows, see [Using Error Outputs in a Data Flow Component](../extending-packages-custom-objects/data-flow/using-error-outputs-in-a-data-flow-component.md).</span></span> <span data-ttu-id="24b7f-145">Тем не менее в компоненте скрипта необходимо написать собственный код, чтобы заполнить дополнительные столбцы соответствующими сведениями об ошибках.</span><span class="sxs-lookup"><span data-stu-id="24b7f-145">In the Script component, however, you must write your own code to fill the additional columns with appropriate error information.</span></span> <span data-ttu-id="24b7f-146">Дополнительные сведения см. в разделе [Имитация вывода ошибок для компонента скрипта](../extending-packages-scripting-data-flow-script-component-examples/simulating-an-error-output-for-the-script-component.md).</span><span class="sxs-lookup"><span data-stu-id="24b7f-146">For more information, see [Simulating an Error Output for the Script Component](../extending-packages-scripting-data-flow-script-component-examples/simulating-an-error-output-for-the-script-component.md).</span></span>

 <span data-ttu-id="24b7f-147">Дополнительные сведения о странице **Входы и выходы** **редактора преобразования "Скрипт"** см. в разделе [Редактор преобразования "Скрипт" (страница "Входы и выходы")](../script-transformation-editor-inputs-and-outputs-page.md).</span><span class="sxs-lookup"><span data-stu-id="24b7f-147">For more information about the **Inputs and Outputs** page of the **Script Transformation Editor**, see [Script Transformation Editor &#40;Inputs and Outputs Page&#41;](../script-transformation-editor-inputs-and-outputs-page.md).</span></span>

### <a name="adding-variables"></a><span data-ttu-id="24b7f-148">Добавление переменных</span><span class="sxs-lookup"><span data-stu-id="24b7f-148">Adding Variables</span></span>
 <span data-ttu-id="24b7f-149">При наличии существующих переменных, значения которых необходимо использовать в скрипте, их можно добавить в `ReadOnlyVariables` `ReadWriteVariables` поля свойств и на странице **Скрипт** в **редакторе преобразования "Скрипт**".</span><span class="sxs-lookup"><span data-stu-id="24b7f-149">If there are any existing variables whose values you want to use in your script, you can add them in the `ReadOnlyVariables` and `ReadWriteVariables` property fields on the **Script** page of the **Script Transformation Editor**.</span></span>

 <span data-ttu-id="24b7f-150">При вводе нескольких переменных в поля свойств разделяйте имена переменных запятыми.</span><span class="sxs-lookup"><span data-stu-id="24b7f-150">When you enter multiple variables in the property fields, separate the variable names by commas.</span></span> <span data-ttu-id="24b7f-151">Можно также ввести несколько переменных, нажав кнопку с многоточием (**...**) рядом с `ReadOnlyVariables` `ReadWriteVariables` полями свойств и и выбрав переменные в диалоговом окне **Выбор переменных** .</span><span class="sxs-lookup"><span data-stu-id="24b7f-151">You can also enter multiple variables by clicking the ellipsis (**...**) button next to the `ReadOnlyVariables` and `ReadWriteVariables` property fields and selecting variables in the **Select variables** dialog box.</span></span>

 <span data-ttu-id="24b7f-152">Общие сведения об использовании переменных в компоненте скрипта см. в разделе [Использование переменных в компоненте скрипта](../extending-packages-scripting/data-flow-script-component/using-variables-in-the-script-component.md).</span><span class="sxs-lookup"><span data-stu-id="24b7f-152">For general information about how to use variables with the Script component, see [Using Variables in the Script Component](../extending-packages-scripting/data-flow-script-component/using-variables-in-the-script-component.md).</span></span>

 <span data-ttu-id="24b7f-153">Дополнительные сведения о странице **Скрипт** в окне **Редактор преобразования "Скрипт"** см. в разделе [Редактор преобразования "Скрипт" (страница "Скрипт")](../script-transformation-editor-script-page.md).</span><span class="sxs-lookup"><span data-stu-id="24b7f-153">For more information about the **Script** page of the **Script Transformation Editor**, see [Script Transformation Editor &#40;Script Page&#41;](../script-transformation-editor-script-page.md).</span></span>

## <a name="scripting-a-source-component-in-code-design-mode"></a><span data-ttu-id="24b7f-154">Сценарная поддержка компонента источника в режиме конструктора кода</span><span class="sxs-lookup"><span data-stu-id="24b7f-154">Scripting a Source Component in Code-Design Mode</span></span>
 <span data-ttu-id="24b7f-155">После настройки метаданных для компонента откройте интегрированную среду разработки средств [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] для приложений (VSTA), чтобы написать код пользовательского скрипта.</span><span class="sxs-lookup"><span data-stu-id="24b7f-155">After you have configured the metadata for your component, open the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications (VSTA) IDE to code your custom script.</span></span> <span data-ttu-id="24b7f-156">Чтобы открыть среду VSTA, щелкните **Изменить скрипт** на странице **Скрипт** окна **Редактор преобразования "скрипт"** .</span><span class="sxs-lookup"><span data-stu-id="24b7f-156">To open VSTA, click **Edit Script** on the **Script** page of the **Script Transformation Editor**.</span></span> <span data-ttu-id="24b7f-157">Можно написать скрипт на языке [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Basic или [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual C# в зависимости от того, какой язык скриптов выбран в качестве значения свойства **ScriptLanguage**.</span><span class="sxs-lookup"><span data-stu-id="24b7f-157">You can write your script by using either [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Basic or [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual C#, depending on the script language selected for the **ScriptLanguage** property.</span></span>

 <span data-ttu-id="24b7f-158">Важные сведения, относящиеся ко всем типам компонентов, создаваемым с помощью компонента скрипта, см. в разделе [Кодирование и отладка компонента скрипта](../extending-packages-scripting/data-flow-script-component/coding-and-debugging-the-script-component.md).</span><span class="sxs-lookup"><span data-stu-id="24b7f-158">For important information that applies to all kinds of components created by using the Script component, see [Coding and Debugging the Script Component](../extending-packages-scripting/data-flow-script-component/coding-and-debugging-the-script-component.md).</span></span>

### <a name="understanding-the-auto-generated-code"></a><span data-ttu-id="24b7f-159">Основные сведения об автоматически создаваемом коде</span><span class="sxs-lookup"><span data-stu-id="24b7f-159">Understanding the Auto-generated Code</span></span>
 <span data-ttu-id="24b7f-160">При открытии интегрированной среды разработки VSTA после создания и настройки компонента источника в редакторе кода появляется класс `ScriptMain`, который можно изменять.</span><span class="sxs-lookup"><span data-stu-id="24b7f-160">When you open the VSTA IDE after creating and configuring a source component, the editable `ScriptMain` class appears in the code editor.</span></span> <span data-ttu-id="24b7f-161">Пользовательский код пишется в классе `ScriptMain`.</span><span class="sxs-lookup"><span data-stu-id="24b7f-161">You write your custom code in the `ScriptMain` class.</span></span>

 <span data-ttu-id="24b7f-162">Класс `ScriptMain` включает заглушку для метода `CreateNewOutputRows`.</span><span class="sxs-lookup"><span data-stu-id="24b7f-162">The `ScriptMain` class includes a stub for the `CreateNewOutputRows` method.</span></span> <span data-ttu-id="24b7f-163">Метод `CreateNewOutputRows` является самым важным методом в компоненте источника.</span><span class="sxs-lookup"><span data-stu-id="24b7f-163">The `CreateNewOutputRows` is the most important method in a source component.</span></span>

 <span data-ttu-id="24b7f-164">Если открыть окно **обозревателя проектов** в VSTA, то можно увидеть, что компонент скрипта также создал элементы проекта только для чтения `BufferWrapper` и `ComponentWrapper` .</span><span class="sxs-lookup"><span data-stu-id="24b7f-164">If you open the **Project Explorer** window in VSTA, you can see that the Script component has also generated read-only `BufferWrapper` and `ComponentWrapper` project items.</span></span> <span data-ttu-id="24b7f-165">Класс `ScriptMain` наследует класс `UserComponent` в элементе проекта `ComponentWrapper`.</span><span class="sxs-lookup"><span data-stu-id="24b7f-165">The `ScriptMain` class inherits from `UserComponent` class in the `ComponentWrapper` project item.</span></span>

 <span data-ttu-id="24b7f-166">Во время выполнения подсистема обработки потока данных вызывает метод `PrimeOutput` в классе `UserComponent`, который переопределяет метод <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponentHost.PrimeOutput%2A> родительского класса <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent>.</span><span class="sxs-lookup"><span data-stu-id="24b7f-166">At run time, the data flow engine invokes the `PrimeOutput` method in the `UserComponent` class, which overrides the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponentHost.PrimeOutput%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent> parent class.</span></span> <span data-ttu-id="24b7f-167">Метод `PrimeOutput` в свою очередь вызывает следующие методы.</span><span class="sxs-lookup"><span data-stu-id="24b7f-167">The `PrimeOutput` method in turn calls the following methods:</span></span>

1.  <span data-ttu-id="24b7f-168">Метод `CreateNewOutputRows`, переопределяемый в классе `ScriptMain` для добавления строк от источника данных в выходные буферы (которые вначале пусты).</span><span class="sxs-lookup"><span data-stu-id="24b7f-168">The `CreateNewOutputRows` method, which you override in `ScriptMain` to add rows from the data source to the output buffers, which are empty at first.</span></span>

2.  <span data-ttu-id="24b7f-169">Метод `FinishOutputs`, который по умолчанию не содержит кода.</span><span class="sxs-lookup"><span data-stu-id="24b7f-169">The `FinishOutputs` method, which is empty by default.</span></span> <span data-ttu-id="24b7f-170">Переопределите этот метод в классе `ScriptMain`, чтобы выполнять любую обработку, необходимую для завершения вывода.</span><span class="sxs-lookup"><span data-stu-id="24b7f-170">Override this method in `ScriptMain` to perform any processing that is required to complete the output.</span></span>

3.  <span data-ttu-id="24b7f-171">Закрытый метод `MarkOutputsAsFinished`, который вызывает метод <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptBuffer.SetEndOfRowset%2A> родительского класса <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptBuffer> для уведомления подсистемы обработки потока данных о завершении вывода.</span><span class="sxs-lookup"><span data-stu-id="24b7f-171">The private `MarkOutputsAsFinished` method, which calls the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptBuffer.SetEndOfRowset%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptBuffer> parent class to indicate to the data flow engine that the output is finished.</span></span> <span data-ttu-id="24b7f-172">Не следует вызывать метод `SetEndOfRowset` явно в собственном коде.</span><span class="sxs-lookup"><span data-stu-id="24b7f-172">You do not have to call `SetEndOfRowset` explicitly in your own code.</span></span>

### <a name="writing-your-custom-code"></a><span data-ttu-id="24b7f-173">Написание пользовательского кода</span><span class="sxs-lookup"><span data-stu-id="24b7f-173">Writing Your Custom Code</span></span>
 <span data-ttu-id="24b7f-174">Чтобы завершить создание пользовательского компонента источника, может потребоваться написать скрипт в следующих методах, доступных в классе `ScriptMain`.</span><span class="sxs-lookup"><span data-stu-id="24b7f-174">To finish creating a custom source component, you may want to write script in the following methods available in the `ScriptMain` class.</span></span>

1.  <span data-ttu-id="24b7f-175">Переопределите метод `AcquireConnections` для соединения с внешним источником данных.</span><span class="sxs-lookup"><span data-stu-id="24b7f-175">Override the `AcquireConnections` method to connect to the external data source.</span></span> <span data-ttu-id="24b7f-176">Извлеките из диспетчера соединений объект соединения или необходимые сведения о соединении.</span><span class="sxs-lookup"><span data-stu-id="24b7f-176">Extract the connection object, or the required connection information, from the connection manager.</span></span>

2.  <span data-ttu-id="24b7f-177">Переопределите метод `PreExecute` для загрузки данных, если можно загрузить все исходные данные одновременно.</span><span class="sxs-lookup"><span data-stu-id="24b7f-177">Override the `PreExecute` method to load data, if you can load all the source data at the same time.</span></span> <span data-ttu-id="24b7f-178">Например, можно выполнить метод `SqlCommand` для соединения [!INCLUDE[vstecado](../../includes/vstecado-md.md)] с базой данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и загрузить все исходные данные одновременно в объект `SqlDataReader`.</span><span class="sxs-lookup"><span data-stu-id="24b7f-178">For example, you can execute a `SqlCommand` against an [!INCLUDE[vstecado](../../includes/vstecado-md.md)] connection to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database and load all the source data at the same time into a `SqlDataReader`.</span></span> <span data-ttu-id="24b7f-179">Если требуется загружать исходные данные в виде отдельных строк (например, при чтении текстового файла), то можно загружать данные в цикле по строкам в методе `CreateNewOutputRows`.</span><span class="sxs-lookup"><span data-stu-id="24b7f-179">If you must load the source data one row at a time (for example, when reading a text file), you can load the data as you loop through rows in `CreateNewOutputRows`.</span></span>

3.  <span data-ttu-id="24b7f-180">Используйте переопределенный метод `CreateNewOutputRows`, чтобы добавлять новые строки в пустые выходные буфера и заполнять новые строки вывода значениями каждого столбца.</span><span class="sxs-lookup"><span data-stu-id="24b7f-180">Use the overridden `CreateNewOutputRows` method to add new rows to the empty output buffers and to fill in the values of each column in the new output rows.</span></span> <span data-ttu-id="24b7f-181">Используйте метод `AddRow` каждого выходного буфера, чтобы добавить новую пустую строку, а затем задавайте значения каждого столбца.</span><span class="sxs-lookup"><span data-stu-id="24b7f-181">Use the `AddRow` method of each output buffer to add an empty new row, and then set the values of each column.</span></span> <span data-ttu-id="24b7f-182">Обычно значения копируются из столбцов, загруженных из внешнего источника.</span><span class="sxs-lookup"><span data-stu-id="24b7f-182">Typically you copy values from the columns loaded from the external source.</span></span>

4.  <span data-ttu-id="24b7f-183">Переопределите метод `PostExecute`, чтобы завершить обработку данных.</span><span class="sxs-lookup"><span data-stu-id="24b7f-183">Override the `PostExecute` method to finish processing the data.</span></span> <span data-ttu-id="24b7f-184">Например, можно закрыть модуль `SqlDataReader`, который использовался для загрузки данных.</span><span class="sxs-lookup"><span data-stu-id="24b7f-184">For example, you can close the `SqlDataReader` that you used to load data.</span></span>

5.  <span data-ttu-id="24b7f-185">Переопределите метод `ReleaseConnections`, если необходимо разорвать соединение с внешним источником данных.</span><span class="sxs-lookup"><span data-stu-id="24b7f-185">Override the `ReleaseConnections` method to disconnect from the external data source, if required.</span></span>

## <a name="examples"></a><span data-ttu-id="24b7f-186">Примеры</span><span class="sxs-lookup"><span data-stu-id="24b7f-186">Examples</span></span>
 <span data-ttu-id="24b7f-187">В следующих примерах демонстрируется пользовательский код, который необходим в классе `ScriptMain` для создания компонента источника.</span><span class="sxs-lookup"><span data-stu-id="24b7f-187">The following examples demonstrate the custom code that is required in the `ScriptMain` class to create a source component.</span></span>

> [!NOTE]
>  <span data-ttu-id="24b7f-188">В этих примерах используется таблица **Person. Address** в `AdventureWorks` образце базы данных и передайте ее первый и четвертый столбцы, столбцы **интаддрессид** и **nvarchar (30) City** через поток данных.</span><span class="sxs-lookup"><span data-stu-id="24b7f-188">These examples use the **Person.Address** table in the `AdventureWorks` sample database and pass its first and fourth columns, the **intAddressID** and **nvarchar(30)City** columns, through the data flow.</span></span> <span data-ttu-id="24b7f-189">Эти же данные используются в образцах источника, преобразования и назначения, приведенных в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="24b7f-189">The same data is used in the source, transformation, and destination samples in this section.</span></span> <span data-ttu-id="24b7f-190">Для каждого примера приведены необходимые дополнительные условия и принимаемые предположения.</span><span class="sxs-lookup"><span data-stu-id="24b7f-190">Additional prerequisites and assumptions are documented for each example.</span></span>

### <a name="adonet-source-example"></a><span data-ttu-id="24b7f-191">Пример источника ADO.NET</span><span class="sxs-lookup"><span data-stu-id="24b7f-191">ADO.NET Source Example</span></span>
 <span data-ttu-id="24b7f-192">В этом примере демонстрируется компонент источника, в котором применяется существующий диспетчер соединений [!INCLUDE[vstecado](../../includes/vstecado-md.md)] для загрузки данных из таблицы [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] в поток данных.</span><span class="sxs-lookup"><span data-stu-id="24b7f-192">This example demonstrates a source component that uses an existing [!INCLUDE[vstecado](../../includes/vstecado-md.md)] connection manager to load data from a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table into the data flow.</span></span>

 <span data-ttu-id="24b7f-193">Для запуска этого образца кода необходимо настроить пакет и компонент следующим образом.</span><span class="sxs-lookup"><span data-stu-id="24b7f-193">If you want to run this sample code, you must configure the package and the component as follows:</span></span>

1.  <span data-ttu-id="24b7f-194">Создайте диспетчер соединений [!INCLUDE[vstecado](../../includes/vstecado-md.md)], использующий поставщик `SqlClient` для соединения с базой данных `AdventureWorks`.</span><span class="sxs-lookup"><span data-stu-id="24b7f-194">Create an [!INCLUDE[vstecado](../../includes/vstecado-md.md)] connection manager that uses the `SqlClient` provider to connect to the `AdventureWorks` database.</span></span>

2.  <span data-ttu-id="24b7f-195">Добавьте новый компонент скрипта в область конструктора потока данных и настройте его в качестве источника.</span><span class="sxs-lookup"><span data-stu-id="24b7f-195">Add a new Script component to the Data Flow designer surface and configure it as a source.</span></span>

3.  <span data-ttu-id="24b7f-196">Откройте **редактор преобразования "Скрипт"** .</span><span class="sxs-lookup"><span data-stu-id="24b7f-196">Open the **Script Transformation Editor**.</span></span> <span data-ttu-id="24b7f-197">На странице **Входы и выходы** измените имя выхода по умолчанию на более описательное имя, такое как **MyAddressOutput**, а также добавьте и настройте два выходных столбца: **AddressID** и **City**.</span><span class="sxs-lookup"><span data-stu-id="24b7f-197">On the **Inputs and Outputs** page, rename the default output with a more descriptive name such as **MyAddressOutput**, and add and configure the two output columns, **AddressID** and **City**.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="24b7f-198">Измените тип данных выходного столбца **City** на DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="24b7f-198">Be sure to change the data type of the **City** output column to DT_WSTR.</span></span>

4.  <span data-ttu-id="24b7f-199">На странице **Диспетчеры соединений** добавьте или создайте диспетчер соединений [!INCLUDE[vstecado](../../includes/vstecado-md.md)] и присвойте ему описательное имя, такое как **MyADONETConnection**.</span><span class="sxs-lookup"><span data-stu-id="24b7f-199">On the **Connection Managers** page, add or create the [!INCLUDE[vstecado](../../includes/vstecado-md.md)] connection manager and give it a name such as **MyADONETConnection**.</span></span>

5.  <span data-ttu-id="24b7f-200">На странице **Скрипт** нажмите кнопку **Изменить скрипт** и введите следующий скрипт.</span><span class="sxs-lookup"><span data-stu-id="24b7f-200">On the **Script** page, click **Edit Script** and enter the script that follows.</span></span> <span data-ttu-id="24b7f-201">Затем закройте среду разработки скриптов и **редактор преобразования "скрипт"** .</span><span class="sxs-lookup"><span data-stu-id="24b7f-201">Then close the script development environment and the **Script Transformation Editor**.</span></span>

6.  <span data-ttu-id="24b7f-202">Создайте и настройте компонент назначения, такой как назначение [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], или образец компонента назначения, демонстрируемый в разделе [Создание назначения с помощью компонента скрипта](../extending-packages-scripting-data-flow-script-component-types/creating-a-destination-with-the-script-component.md), который ожидает получения столбцов **AddressID** и **City**.</span><span class="sxs-lookup"><span data-stu-id="24b7f-202">Create and configure a destination component, such as a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] destination, or the sample destination component demonstrated in [Creating a Destination with the Script Component](../extending-packages-scripting-data-flow-script-component-types/creating-a-destination-with-the-script-component.md), that expects the **AddressID** and **City** columns.</span></span> <span data-ttu-id="24b7f-203">Затем соедините компонент источника с назначением.</span><span class="sxs-lookup"><span data-stu-id="24b7f-203">Then connect the source component to the destination.</span></span> <span data-ttu-id="24b7f-204">(Источник можно подключить непосредственно к назначению без каких-либо преобразований.) Вы можете создать целевую таблицу, выполнив следующую [!INCLUDE[tsql](../../includes/tsql-md.md)] команду в `AdventureWorks` базе данных:</span><span class="sxs-lookup"><span data-stu-id="24b7f-204">(You can connect a source directly to a destination without any transformations.) You can create a destination table by running the following [!INCLUDE[tsql](../../includes/tsql-md.md)] command in the `AdventureWorks` database:</span></span>

    ```
    CREATE TABLE [Person].[Address2]([AddressID] [int] NOT NULL,
        [City] [nvarchar](30) NOT NULL)
    ```

7.  <span data-ttu-id="24b7f-205">Запустите образец.</span><span class="sxs-lookup"><span data-stu-id="24b7f-205">Run the sample.</span></span>

    ```vb
    Imports System.Data.SqlClient
    ...
    Public Class ScriptMain
        Inherits UserComponent

        Dim connMgr As IDTSConnectionManager100
        Dim sqlConn As SqlConnection
        Dim sqlReader As SqlDataReader

        Public Overrides Sub AcquireConnections(ByVal Transaction As Object)

            connMgr = Me.Connections.MyADONETConnection
            sqlConn = CType(connMgr.AcquireConnection(Nothing), SqlConnection)

        End Sub

        Public Overrides Sub PreExecute()

            Dim cmd As New SqlCommand("SELECT AddressID, City, StateProvinceID FROM Person.Address", sqlConn)
            sqlReader = cmd.ExecuteReader

        End Sub

        Public Overrides Sub CreateNewOutputRows()

            Do While sqlReader.Read
                With MyAddressOutputBuffer
                    .AddRow()
                    .AddressID = sqlReader.GetInt32(0)
                    .City = sqlReader.GetString(1)
                End With
            Loop

        End Sub

        Public Overrides Sub PostExecute()

            sqlReader.Close()

        End Sub

        Public Overrides Sub ReleaseConnections()

            connMgr.ReleaseConnection(sqlConn)

        End Sub

    End Class
    ```

    ```csharp
    using System.Data.SqlClient;
    public class ScriptMain:
        UserComponent

    {
        IDTSConnectionManager100 connMgr;
        SqlConnection sqlConn;
        SqlDataReader sqlReader;

        public override void AcquireConnections(object Transaction)
        {
            connMgr = this.Connections.MyADONETConnection;
            sqlConn = (SqlConnection)connMgr.AcquireConnection(null);

        }

        public override void PreExecute()
        {

            SqlCommand cmd = new SqlCommand("SELECT AddressID, City, StateProvinceID FROM Person.Address", sqlConn);
            sqlReader = cmd.ExecuteReader();

        }

        public override void CreateNewOutputRows()
        {

            while (sqlReader.Read())
            {
                {
                    MyAddressOutputBuffer.AddRow();
                    MyAddressOutputBuffer.AddressID = sqlReader.GetInt32(0);
                    MyAddressOutputBuffer.City = sqlReader.GetString(1);
                }
            }

        }

        public override void PostExecute()
        {

            sqlReader.Close();

        }

        public override void ReleaseConnections()
        {

            connMgr.ReleaseConnection(sqlConn);

        }

    }
    ```

### <a name="flat-file-source-example"></a><span data-ttu-id="24b7f-206">Пример источника «Неструктурированный файл»</span><span class="sxs-lookup"><span data-stu-id="24b7f-206">Flat File Source Example</span></span>
 <span data-ttu-id="24b7f-207">В этом примере демонстрируется компонент источника, в котором используется существующий диспетчер соединений с неструктурированными файлами для загрузки данных из неструктурированного файла в поток данных.</span><span class="sxs-lookup"><span data-stu-id="24b7f-207">This example demonstrates a source component that uses an existing Flat File connection manager to load data from a flat file into the data flow.</span></span> <span data-ttu-id="24b7f-208">Исходные данные неструктурированного файла создаются при экспорте их из [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="24b7f-208">The flat file source data is created by exporting it from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>

 <span data-ttu-id="24b7f-209">Для запуска этого образца кода необходимо настроить пакет и компонент следующим образом.</span><span class="sxs-lookup"><span data-stu-id="24b7f-209">If you want to run this sample code, you must configure the package and the component as follows:</span></span>

1.  <span data-ttu-id="24b7f-210">С помощью [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] мастера импорта и экспорта экспортируйте таблицу **Person. Address** из `AdventureWorks` образца базы данных в неструктурированный файл с разделителями-запятыми.</span><span class="sxs-lookup"><span data-stu-id="24b7f-210">Use the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Import and Export Wizard to export the **Person.Address** table from the `AdventureWorks` sample database to a comma-delimited flat file.</span></span> <span data-ttu-id="24b7f-211">В этом образце используется файл с именем ExportedAddresses.txt.</span><span class="sxs-lookup"><span data-stu-id="24b7f-211">This sample uses the file name ExportedAddresses.txt.</span></span>

2.  <span data-ttu-id="24b7f-212">Создайте диспетчер соединений с неструктурированными файлами, который подключается к экспортированному файлу данных.</span><span class="sxs-lookup"><span data-stu-id="24b7f-212">Create a Flat File connection manager that connects to the exported data file.</span></span>

3.  <span data-ttu-id="24b7f-213">Добавьте новый компонент скрипта в область конструктора потока данных и настройте его в качестве источника.</span><span class="sxs-lookup"><span data-stu-id="24b7f-213">Add a new Script component to the Data Flow designer surface and configure it as a source.</span></span>

4.  <span data-ttu-id="24b7f-214">Откройте **редактор преобразования "Скрипт"** .</span><span class="sxs-lookup"><span data-stu-id="24b7f-214">Open the **Script Transformation Editor**.</span></span> <span data-ttu-id="24b7f-215">На странице **Входы и выходы** измените имя выхода по умолчанию на более описательное имя, такое как **MyAddressOutput**.</span><span class="sxs-lookup"><span data-stu-id="24b7f-215">On the **Inputs and Outputs** page, rename the default output with a more descriptive name such as **MyAddressOutput**.</span></span> <span data-ttu-id="24b7f-216">Добавьте и настройте два выходных столбца: **AddressID** и **City**.</span><span class="sxs-lookup"><span data-stu-id="24b7f-216">Add and configure the two output columns, **AddressID** and **City**.</span></span>

5.  <span data-ttu-id="24b7f-217">На странице **Диспетчеры соединений** добавьте или создайте диспетчер соединений с неструктурированными файлами, используя описательное имя, такое как **MyFlatFileSrcConnectionManager**.</span><span class="sxs-lookup"><span data-stu-id="24b7f-217">On the **Connection Managers** page, add or create the Flat File connection manager, using a descriptive name such as **MyFlatFileSrcConnectionManager**.</span></span>

6.  <span data-ttu-id="24b7f-218">На странице **Скрипт** нажмите кнопку **Изменить скрипт** и введите следующий скрипт.</span><span class="sxs-lookup"><span data-stu-id="24b7f-218">On the **Script** page, click **Edit Script** and enter the script that follows.</span></span> <span data-ttu-id="24b7f-219">Затем закройте среду разработки скриптов и **редактор преобразования "скрипт"** .</span><span class="sxs-lookup"><span data-stu-id="24b7f-219">Then close the script development environment and the **Script Transformation Editor**.</span></span>

7.  <span data-ttu-id="24b7f-220">Создайте и настройте компонент назначения, такой как компонент назначения [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], или образец компонента назначения, демонстрируемый в разделе [Создание назначения с помощью компонента скрипта](../extending-packages-scripting-data-flow-script-component-types/creating-a-destination-with-the-script-component.md).</span><span class="sxs-lookup"><span data-stu-id="24b7f-220">Create and configure a destination component, such as a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] destination, or the sample destination component demonstrated in [Creating a Destination with the Script Component](../extending-packages-scripting-data-flow-script-component-types/creating-a-destination-with-the-script-component.md).</span></span> <span data-ttu-id="24b7f-221">Затем соедините компонент источника с назначением.</span><span class="sxs-lookup"><span data-stu-id="24b7f-221">Then connect the source component to the destination.</span></span> <span data-ttu-id="24b7f-222">(Источник можно подключить непосредственно к назначению без каких-либо преобразований.) Вы можете создать целевую таблицу, выполнив следующую [!INCLUDE[tsql](../../includes/tsql-md.md)] команду в `AdventureWorks` базе данных:</span><span class="sxs-lookup"><span data-stu-id="24b7f-222">(You can connect a source directly to a destination without any transformations.) You can create a destination table by running the following [!INCLUDE[tsql](../../includes/tsql-md.md)] command in the `AdventureWorks` database:</span></span>

    ```
    CREATE TABLE [Person].[Address2]([AddressID] [int] NOT NULL,
        [City] [nvarchar](30) NOT NULL)
    ```

8.  <span data-ttu-id="24b7f-223">Запустите образец.</span><span class="sxs-lookup"><span data-stu-id="24b7f-223">Run the sample.</span></span>

    ```vb
    Imports System.IO
    ...
    Public Class ScriptMain
        Inherits UserComponent

        Private textReader As StreamReader
        Private exportedAddressFile As String

        Public Overrides Sub AcquireConnections(ByVal Transaction As Object)

            Dim connMgr As IDTSConnectionManager100 = _
                Me.Connections.MyFlatFileSrcConnectionManager
            exportedAddressFile = _
                CType(connMgr.AcquireConnection(Nothing), String)

        End Sub

        Public Overrides Sub PreExecute()
            MyBase.PreExecute()
            textReader = New StreamReader(exportedAddressFile)
        End Sub

        Public Overrides Sub CreateNewOutputRows()

            Dim nextLine As String
            Dim columns As String()

            Dim delimiters As Char()
            delimiters = ",".ToCharArray

            nextLine = textReader.ReadLine
            Do While nextLine IsNot Nothing
                columns = nextLine.Split(delimiters)
                With MyAddressOutputBuffer
                    .AddRow()
                    .AddressID = columns(0)
                    .City = columns(3)
                End With
                nextLine = textReader.ReadLine
            Loop

        End Sub

        Public Overrides Sub PostExecute()
            MyBase.PostExecute()
            textReader.Close()

        End Sub

    End Class
    ```

    ```csharp
    using System.IO;
    public class ScriptMain:
        UserComponent

    {
        private StreamReader textReader;
        private string exportedAddressFile;

        public override void AcquireConnections(object Transaction)
        {

            IDTSConnectionManager100 connMgr = this.Connections.MyFlatFileSrcConnectionManager;
            exportedAddressFile = (string)connMgr.AcquireConnection(null);

        }

        public override void PreExecute()
        {
            base.PreExecute();
            textReader = new StreamReader(exportedAddressFile);
        }

        public override void CreateNewOutputRows()
        {

            string nextLine;
            string[] columns;

            char[] delimiters;
            delimiters = ",".ToCharArray();

            nextLine = textReader.ReadLine();
            while (nextLine != null)
            {
                columns = nextLine.Split(delimiters);
                {
                    MyAddressOutputBuffer.AddRow();
                    MyAddressOutputBuffer.AddressID = columns[0];
                    MyAddressOutputBuffer.City = columns[3];
                }
                nextLine = textReader.ReadLine();
            }

        }

        public override void PostExecute()
        {

            base.PostExecute();
            textReader.Close();

        }

    }
    ```

<span data-ttu-id="24b7f-224">![Значок Integration Services (маленький)](../media/dts-16.gif "Значок служб Integration Services (маленький)")  **следит за обновлениями Integration Services**</span><span class="sxs-lookup"><span data-stu-id="24b7f-224">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="24b7f-225">Чтобы загрузить новейшую документацию, статьи, образцы и видеоматериалы корпорации Майкрософт, а также лучшие решения участников сообщества, посетите страницу служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] на сайте MSDN:</span><span class="sxs-lookup"><span data-stu-id="24b7f-225">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="24b7f-226">Посетить страницу «Службы Integration Services» на сайте MSDN</span><span class="sxs-lookup"><span data-stu-id="24b7f-226">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="24b7f-227">Чтобы получать автоматические уведомления об этих обновлениях, подпишитесь на RSS-каналы, предлагаемые на этой странице.</span><span class="sxs-lookup"><span data-stu-id="24b7f-227">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="24b7f-228">См. также:</span><span class="sxs-lookup"><span data-stu-id="24b7f-228">See Also</span></span>
 <span data-ttu-id="24b7f-229">[Создание назначения с помощью компонента скрипта](../extending-packages-scripting-data-flow-script-component-types/creating-a-destination-with-the-script-component.md) [Разработка пользовательского компонента источника](../extending-packages-custom-objects-data-flow-types/developing-a-custom-source-component.md)</span><span class="sxs-lookup"><span data-stu-id="24b7f-229">[Creating a Destination with the Script Component](../extending-packages-scripting-data-flow-script-component-types/creating-a-destination-with-the-script-component.md) [Developing a Custom Source Component](../extending-packages-custom-objects-data-flow-types/developing-a-custom-source-component.md)</span></span>


