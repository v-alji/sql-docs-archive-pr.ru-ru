---
title: Создание назначения с помощью компонента скрипта | Документы Майкрософт
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- Script component [Integration Services], destination components
- destinations [Integration Services], components
- input columns [Integration Services]
ms.assetid: 214e22e8-7e7d-4876-b690-c138e5721b81
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1245dde111b24d1c37e2c5550d236c97126ee725
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666177"
---
# <a name="creating-a-destination-with-the-script-component"></a><span data-ttu-id="8daf7-102">Создание назначения с помощью компонента скрипта</span><span class="sxs-lookup"><span data-stu-id="8daf7-102">Creating a Destination with the Script Component</span></span>
  <span data-ttu-id="8daf7-103">Компонент назначения в потоке данных пакета служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] используется для сохранения данных, полученных из вышестоящих источников и преобразований, в источник данных.</span><span class="sxs-lookup"><span data-stu-id="8daf7-103">You use a destination component in the data flow of an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package to save data received from upstream sources and transformations to a data source.</span></span> <span data-ttu-id="8daf7-104">Обычно компонент назначения подключается к источнику данных через существующий диспетчер соединений.</span><span class="sxs-lookup"><span data-stu-id="8daf7-104">Ordinarily the destination component connects to the data source through an existing connection manager.</span></span>

 <span data-ttu-id="8daf7-105">Общие сведения о компоненте скрипта см. в разделе [расширение потока данных с помощью компонента скрипта] (. /екстендинг-паккажес-скриптинг/дата-флов-скрипт-компонент/екстендинг-се-дата-флов-вис-се-скрипт-компонент.мд.</span><span class="sxs-lookup"><span data-stu-id="8daf7-105">For an overview of the Script component, see [Extending the Data Flow with the Script Component](../extending-packages-scripting/data-flow-script-component/extending-the-data-flow-with-the-script-component.md.</span></span>

 <span data-ttu-id="8daf7-106">Компонент скрипта и формируемый им код инфраструктуры значительно упрощают процесс создания пользовательских компонентов потока данных.</span><span class="sxs-lookup"><span data-stu-id="8daf7-106">The Script component and the infrastructure code that it generates for you simplify significantly the process of developing a custom data flow component.</span></span> <span data-ttu-id="8daf7-107">Однако чтобы понять, как работает компонент скрипта, может быть полезно ознакомиться с шагами по разработке пользовательских компонентов потока данных, описанными в разделе [Разработка пользовательского компонента потока данных](../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md) и в особенности в разделе [Разработка пользовательского компонента назначения](../extending-packages-custom-objects-data-flow-types/developing-a-custom-destination-component.md).</span><span class="sxs-lookup"><span data-stu-id="8daf7-107">However, to understand how the Script component works, you may find it useful to read through the steps for developing a custom data flow components in the [Developing a Custom Data Flow Component](../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md) section, and especially [Developing a Custom Destination Component](../extending-packages-custom-objects-data-flow-types/developing-a-custom-destination-component.md).</span></span>

## <a name="getting-started-with-a-destination-component"></a><span data-ttu-id="8daf7-108">Приступая к работе с компонентом назначения</span><span class="sxs-lookup"><span data-stu-id="8daf7-108">Getting Started with a Destination Component</span></span>
 <span data-ttu-id="8daf7-109">При добавлении компонента скрипта на вкладку "Поток данных" конструктора служб [!INCLUDE[ssIS](../../includes/ssis-md.md)] открывается диалоговое окно **Выбор типа компонента скрипта** с приглашением выбрать скрипт **Источник**, **Назначение** или **Преобразование**.</span><span class="sxs-lookup"><span data-stu-id="8daf7-109">When you add a Script component to the Data Flow tab of [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, the **Select Script Component Type** dialog box opens and prompts you to select a **Source**, **Destination**, or **Transformation** script.</span></span> <span data-ttu-id="8daf7-110">Выберите в этом диалоговом окне скрипт **Назначение**.</span><span class="sxs-lookup"><span data-stu-id="8daf7-110">In this dialog box, select **Destination**.</span></span>

 <span data-ttu-id="8daf7-111">Затем подключите выход преобразования к компоненту назначения в конструкторе служб [!INCLUDE[ssIS](../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8daf7-111">Next, connect the output of a transformation to the destination component in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="8daf7-112">Для целей тестирования можно напрямую соединить источник с назначением без преобразований.</span><span class="sxs-lookup"><span data-stu-id="8daf7-112">For testing, you can connect a source directly to a destination without any transformations.</span></span>

## <a name="configuring-a-destination-component-in-metadata-design-mode"></a><span data-ttu-id="8daf7-113">Настройка компонента назначения в режиме конструктора метаданных</span><span class="sxs-lookup"><span data-stu-id="8daf7-113">Configuring a Destination Component in Metadata-Design Mode</span></span>
 <span data-ttu-id="8daf7-114">Выбрав параметр создания компонента назначения, можно настроить его с помощью **редактора преобразования "Скрипт"** .</span><span class="sxs-lookup"><span data-stu-id="8daf7-114">After you select the option to create a destination component, you configure the component by using the **Script Transformation Editor**.</span></span> <span data-ttu-id="8daf7-115">Дополнительные сведения см. в разделе [Настройка компонента скрипта в редакторе компонента скрипта](../extending-packages-scripting/data-flow-script-component/configuring-the-script-component-in-the-script-component-editor.md).</span><span class="sxs-lookup"><span data-stu-id="8daf7-115">For more information, see [Configuring the Script Component in the Script Component Editor](../extending-packages-scripting/data-flow-script-component/configuring-the-script-component-in-the-script-component-editor.md).</span></span>

 <span data-ttu-id="8daf7-116">Чтобы выбрать язык скрипта в назначении скрипта, нужно задать свойство **ScriptLanguage** на странице **Скрипт** диалогового окна **Редактор преобразования "Скрипт"** .</span><span class="sxs-lookup"><span data-stu-id="8daf7-116">To select the script language that the Script destination will use, you set the **ScriptLanguage** property on the **Script** page of the **Script Transformation Editor** dialog box.</span></span>

> [!NOTE]
>  <span data-ttu-id="8daf7-117">Чтобы установить язык скрипта по умолчанию для компонента скрипта, воспользуйтесь параметром **Язык сценариев** на странице **Общие** диалогового окна **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="8daf7-117">To set the default scripting language for the Script component, use the **Scripting language** option on the **General** page of the **Options** dialog box.</span></span> <span data-ttu-id="8daf7-118">Дополнительные сведения см. в разделе [General Page](../general-page-of-integration-services-designers-options.md).</span><span class="sxs-lookup"><span data-stu-id="8daf7-118">For more information, see [General Page](../general-page-of-integration-services-designers-options.md).</span></span>

 <span data-ttu-id="8daf7-119">Компонент назначения потока данных имеет один вход и ни одного выхода.</span><span class="sxs-lookup"><span data-stu-id="8daf7-119">A data flow destination component has one input and no outputs.</span></span> <span data-ttu-id="8daf7-120">Настройка входа компонента является одним из шагов, которые необходимо выполнить в режиме конструктора метаданных с использованием **редактора преобразования "Скрипт"** , прежде чем приступать к написанию пользовательского скрипта.</span><span class="sxs-lookup"><span data-stu-id="8daf7-120">Configuring the input for the component is one of the steps that you must complete in metadata design mode, by using the **Script Transformation Editor**, before you write your custom script.</span></span>

### <a name="adding-connection-managers"></a><span data-ttu-id="8daf7-121">Добавление диспетчеров соединений</span><span class="sxs-lookup"><span data-stu-id="8daf7-121">Adding Connection Managers</span></span>
 <span data-ttu-id="8daf7-122">Обычно компонент назначения через существующий диспетчер соединений подключается к источнику данных, куда сохраняет данные из потока данных.</span><span class="sxs-lookup"><span data-stu-id="8daf7-122">Ordinarily a destination component uses an existing connection manager to connect to the data source to which it saves data from the data flow.</span></span> <span data-ttu-id="8daf7-123">На странице **Диспетчеры соединений** в **редакторе преобразования "Скрипт"** нажмите кнопку **Добавить**, чтобы добавить нужный диспетчер соединений.</span><span class="sxs-lookup"><span data-stu-id="8daf7-123">On the **Connection Managers** page of the **Script Transformation Editor**, click **Add** to add the appropriate connection manager.</span></span>

 <span data-ttu-id="8daf7-124">Однако диспетчер соединений представляет собой лишь удобную оболочку, которая инкапсулирует и хранит информацию, нужную для подключения к источнику данных определенного типа.</span><span class="sxs-lookup"><span data-stu-id="8daf7-124">However, a connection manager is just a convenient unit that encapsulates and stores the information that is required to connect to a data source of a particular type.</span></span> <span data-ttu-id="8daf7-125">Для загрузки и сохранения данных, и, возможно, также для открытия и закрытия соединения с источником данных нужно разрабатывать собственный код.</span><span class="sxs-lookup"><span data-stu-id="8daf7-125">You must write your own custom code to load or save your data, and possibly to open and close the connection to the data source.</span></span>

 <span data-ttu-id="8daf7-126">Общие сведения об использовании диспетчеров соединений в компоненте скрипта см. в разделе [Соединение с источниками данных в компоненте скрипта](../extending-packages-scripting/data-flow-script-component/connecting-to-data-sources-in-the-script-component.md).</span><span class="sxs-lookup"><span data-stu-id="8daf7-126">For general information about how to use connection managers with the Script component, see [Connecting to Data Sources in the Script Component](../extending-packages-scripting/data-flow-script-component/connecting-to-data-sources-in-the-script-component.md).</span></span>

 <span data-ttu-id="8daf7-127">Дополнительные сведения о странице **Диспетчеры соединений** окна **Редактор преобразования "Скрипт"** см. в разделе [Редактор преобразования "Скрипт" (страница "Диспетчеры соединений")](../script-transformation-editor-connection-managers-page.md).</span><span class="sxs-lookup"><span data-stu-id="8daf7-127">For more information about the **Connection Managers** page of the **Script Transformation Editor**, see [Script Transformation Editor &#40;Connection Managers Page&#41;](../script-transformation-editor-connection-managers-page.md).</span></span>

### <a name="configuring-inputs-and-input-columns"></a><span data-ttu-id="8daf7-128">Настройка входов и входных столбцов</span><span class="sxs-lookup"><span data-stu-id="8daf7-128">Configuring Inputs and Input Columns</span></span>
 <span data-ttu-id="8daf7-129">Компонент назначения имеет один вход и ни одного выхода.</span><span class="sxs-lookup"><span data-stu-id="8daf7-129">A destination component has one input and no outputs.</span></span>

 <span data-ttu-id="8daf7-130">На странице **Входные столбцы** в **редакторе преобразования "Скрипт"** список столбцов содержит доступные столбцы на выходе вышестоящего компонента в потоке данных.</span><span class="sxs-lookup"><span data-stu-id="8daf7-130">On the **Input Columns** page of the **Script Transformation Editor**, the column list shows the available columns from the output of the upstream component in the data flow.</span></span> <span data-ttu-id="8daf7-131">Выберите столбцы, которые нужно сохранить.</span><span class="sxs-lookup"><span data-stu-id="8daf7-131">Select the columns that you want to save.</span></span>

 <span data-ttu-id="8daf7-132">Дополнительные сведения о странице **Входные столбцы** **редактора преобразования "Скрипт"** см. в разделе [Редактор преобразования "Скрипт" (страница "Входные столбцы")](../script-transformation-editor-input-columns-page.md).</span><span class="sxs-lookup"><span data-stu-id="8daf7-132">For more information about the **Input Columns** page of the **Script Transformation Editor**, see [Script Transformation Editor &#40;Input Columns Page&#41;](../script-transformation-editor-input-columns-page.md).</span></span>

 <span data-ttu-id="8daf7-133">Страница **Входы и выходы** диалогового окна **Редактор преобразования "Скрипт"** показывает один вход, который можно переименовать.</span><span class="sxs-lookup"><span data-stu-id="8daf7-133">The **Inputs and Outputs** page of the **Script Transformation Editor** shows a single input, which you can rename.</span></span> <span data-ttu-id="8daf7-134">В скрипте можно ссылаться на столбец ввода по имени с помощью свойства метода доступа, созданного автоматически.</span><span class="sxs-lookup"><span data-stu-id="8daf7-134">You will refer to the input by its name in your script by using the accessor property created in the auto-generated code.</span></span>

 <span data-ttu-id="8daf7-135">Дополнительные сведения о странице **Входы и выходы** **редактора преобразования "Скрипт"** см. в разделе [Редактор преобразования "Скрипт" (страница "Входы и выходы")](../script-transformation-editor-inputs-and-outputs-page.md).</span><span class="sxs-lookup"><span data-stu-id="8daf7-135">For more information about the **Inputs and Outputs** page of the **Script Transformation Editor**, see [Script Transformation Editor &#40;Inputs and Outputs Page&#41;](../script-transformation-editor-inputs-and-outputs-page.md).</span></span>

### <a name="adding-variables"></a><span data-ttu-id="8daf7-136">Добавление переменных</span><span class="sxs-lookup"><span data-stu-id="8daf7-136">Adding Variables</span></span>
 <span data-ttu-id="8daf7-137">Если вы хотите использовать в скрипте существующие переменные, их можно добавить в `ReadOnlyVariables` `ReadWriteVariables` поля свойств и на странице **Скрипт** в **редакторе преобразования "Скрипт**".</span><span class="sxs-lookup"><span data-stu-id="8daf7-137">If you want to use existing variables in your script, you can add them in the `ReadOnlyVariables` and `ReadWriteVariables` property fields on the **Script** page of the **Script Transformation Editor**.</span></span>

 <span data-ttu-id="8daf7-138">Если в поле свойства добавляются несколько переменных, их имена нужно разделять запятыми.</span><span class="sxs-lookup"><span data-stu-id="8daf7-138">When you add multiple variables in the property fields, separate the variable names by commas.</span></span> <span data-ttu-id="8daf7-139">Можно также выбрать несколько переменных, нажав кнопку с многоточием (**...**) рядом с `ReadOnlyVariables` `ReadWriteVariables` полями свойств и, а затем выбрав переменные в диалоговом окне **Выбор переменных** .</span><span class="sxs-lookup"><span data-stu-id="8daf7-139">You can also select multiple variables by clicking the ellipsis (**...**) button next to the `ReadOnlyVariables` and `ReadWriteVariables` property fields, and then selecting the variables in the **Select variables** dialog box.</span></span>

 <span data-ttu-id="8daf7-140">Общие сведения об использовании переменных в компоненте скрипта см. в разделе [Использование переменных в компоненте скрипта](../extending-packages-scripting/data-flow-script-component/using-variables-in-the-script-component.md).</span><span class="sxs-lookup"><span data-stu-id="8daf7-140">For general information about how to use variables with the Script component, see [Using Variables in the Script Component](../extending-packages-scripting/data-flow-script-component/using-variables-in-the-script-component.md).</span></span>

 <span data-ttu-id="8daf7-141">Дополнительные сведения о странице **Скрипт** в окне **Редактор преобразования "Скрипт"** см. в разделе [Редактор преобразования "Скрипт" (страница "Скрипт")](../script-transformation-editor-script-page.md).</span><span class="sxs-lookup"><span data-stu-id="8daf7-141">For more information about the **Script** page of the **Script Transformation Editor**, see [Script Transformation Editor &#40;Script Page&#41;](../script-transformation-editor-script-page.md).</span></span>

## <a name="scripting-a-destination-component-in-code-design-mode"></a><span data-ttu-id="8daf7-142">Создание скрипта для компонента назначения в режиме конструктора кода</span><span class="sxs-lookup"><span data-stu-id="8daf7-142">Scripting a Destination Component in Code-Design Mode</span></span>
 <span data-ttu-id="8daf7-143">После настройки метаданных для компонента можно написать пользовательский скрипт.</span><span class="sxs-lookup"><span data-stu-id="8daf7-143">After you have configured the metadata for your component, you can write your custom script.</span></span> <span data-ttu-id="8daf7-144">В **редакторе преобразования "Скрипт"** на странице **Скрипт** нажмите кнопку **Изменить скрипт**, чтобы открыть интегрированную среду разработки средств [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] для приложений (VSTA), где можно добавить пользовательский скрипт.</span><span class="sxs-lookup"><span data-stu-id="8daf7-144">In the **Script Transformation Editor**, on the **Script** page, click **Edit Script** to open the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications (VSTA) IDE where you can add your custom script.</span></span> <span data-ttu-id="8daf7-145">Используемый язык скриптов зависит от значения свойства **ScriptLanguage**, указанного на странице **Скрипт**. В качестве значения можно выбрать язык [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Basic или [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual C#.</span><span class="sxs-lookup"><span data-stu-id="8daf7-145">The scripting language that you use depends on whether you selected [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Basic or [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual C# as the script language for the **ScriptLanguage** property on the **Script** page.</span></span>

 <span data-ttu-id="8daf7-146">Важные сведения, относящиеся ко всем типам компонентов, создаваемым с помощью компонента скрипта, см. в разделе [Кодирование и отладка компонента скрипта](../extending-packages-scripting/data-flow-script-component/coding-and-debugging-the-script-component.md).</span><span class="sxs-lookup"><span data-stu-id="8daf7-146">For important information that applies to all kinds of components created by using the Script component, see [Coding and Debugging the Script Component](../extending-packages-scripting/data-flow-script-component/coding-and-debugging-the-script-component.md).</span></span>

### <a name="understanding-the-auto-generated-code"></a><span data-ttu-id="8daf7-147">Основные сведения об автоматически создаваемом коде</span><span class="sxs-lookup"><span data-stu-id="8daf7-147">Understanding the Auto-generated Code</span></span>
 <span data-ttu-id="8daf7-148">При открытии интегрированной среды разработки VSTA после создания и настройки компонента назначения в редакторе кода появляется редактируемый класс `ScriptMain` с заглушкой для метода `ProcessInputRow`.</span><span class="sxs-lookup"><span data-stu-id="8daf7-148">When you open the VSTA IDE after you create and configuring a destination component, the editable `ScriptMain` class appears in the code editor with a stub for the `ProcessInputRow` method.</span></span> <span data-ttu-id="8daf7-149">Класс `ScriptMain` — место для размещения собственного кода, а метод `ProcessInputRow` — самый важный метод в компоненте назначения.</span><span class="sxs-lookup"><span data-stu-id="8daf7-149">The `ScriptMain` class is where you will write your custom code, and `ProcessInputRow` is the most important method in a destination component.</span></span>

 <span data-ttu-id="8daf7-150">Если открыть окно **обозревателя проектов** в VSTA, то можно увидеть, что компонент скрипта также создал элементы проекта только для чтения `BufferWrapper` и `ComponentWrapper` .</span><span class="sxs-lookup"><span data-stu-id="8daf7-150">If you open the **Project Explorer** window in VSTA, you can see that the Script component has also generated read-only `BufferWrapper` and `ComponentWrapper` project items.</span></span> <span data-ttu-id="8daf7-151">Класс `ScriptMain` наследует класс `UserComponent` в элементе проекта `ComponentWrapper`.</span><span class="sxs-lookup"><span data-stu-id="8daf7-151">The `ScriptMain` class inherits from `UserComponent` class in the `ComponentWrapper` project item.</span></span>

 <span data-ttu-id="8daf7-152">Во время выполнения подсистема обработки потока данных вызывает метод `ProcessInput` в классе `UserComponent`, который переопределяет метод <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.ProcessInput%2A> родительского класса <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent>.</span><span class="sxs-lookup"><span data-stu-id="8daf7-152">At run time, the data flow engine invokes the `ProcessInput` method in the `UserComponent` class, which overrides the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.ProcessInput%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent> parent class.</span></span> <span data-ttu-id="8daf7-153">В свою очередь, метод `ProcessInput` проходит по строкам во входном буфере и вызывает для каждой строки метод `ProcessInputRow`.</span><span class="sxs-lookup"><span data-stu-id="8daf7-153">The `ProcessInput` method in turn loops through the rows in the input buffer and calls the `ProcessInputRow` method one time for each row.</span></span>

### <a name="writing-your-custom-code"></a><span data-ttu-id="8daf7-154">Написание пользовательского кода</span><span class="sxs-lookup"><span data-stu-id="8daf7-154">Writing Your Custom Code</span></span>
 <span data-ttu-id="8daf7-155">Для завершения пользовательского компонента назначения можно ввести скрипты в следующие методы, доступные в классе `ScriptMain`.</span><span class="sxs-lookup"><span data-stu-id="8daf7-155">To finish creating a custom destination component, you may want to write script in the following methods available in the `ScriptMain` class.</span></span>

1.  <span data-ttu-id="8daf7-156">Переопределите метод `AcquireConnections` для соединения с внешним источником данных.</span><span class="sxs-lookup"><span data-stu-id="8daf7-156">Override the `AcquireConnections` method to connect to the external data source.</span></span> <span data-ttu-id="8daf7-157">Извлеките из диспетчера соединений объект соединения или необходимые сведения о соединении.</span><span class="sxs-lookup"><span data-stu-id="8daf7-157">Extract the connection object, or the required connection information, from the connection manager.</span></span>

2.  <span data-ttu-id="8daf7-158">Для подготовки к сохранению данных переопределите метод `PreExecute`.</span><span class="sxs-lookup"><span data-stu-id="8daf7-158">Override the `PreExecute` method to prepare to save the data.</span></span> <span data-ttu-id="8daf7-159">Например, в этом методе можно создать и настроить объект `SqlCommand` и его параметры.</span><span class="sxs-lookup"><span data-stu-id="8daf7-159">For example, you may want to create and configure a `SqlCommand` and its parameters in this method.</span></span>

3.  <span data-ttu-id="8daf7-160">Используйте переопределенный метод `ProcessInputRow` для копирования всех строк ввода во внешний источник данных.</span><span class="sxs-lookup"><span data-stu-id="8daf7-160">Use the overridden `ProcessInputRow` method to copy each input row to the external data source.</span></span> <span data-ttu-id="8daf7-161">Например, для назначения [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] можно скопировать значения столбцов в параметры `SqlCommand` и выполнить команду по одному разу для каждой строки.</span><span class="sxs-lookup"><span data-stu-id="8daf7-161">For example, for a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] destination, you can copy the column values into the parameters of a `SqlCommand` and execute the command one time for each row.</span></span> <span data-ttu-id="8daf7-162">Для назначения «Неструктурированный файл» можно записать значения столбцов в объект `StreamWriter`, разделяя значения разделителем столбцов.</span><span class="sxs-lookup"><span data-stu-id="8daf7-162">For a flat file destination, you can write the values for each column to a `StreamWriter`, separating the values by the column delimiter.</span></span>

4.  <span data-ttu-id="8daf7-163">Переопределите метод `PostExecute` для отключения от внешнего источника данных, если это требуется, и для выполнения всех прочих действий по очистке.</span><span class="sxs-lookup"><span data-stu-id="8daf7-163">Override the `PostExecute` method to disconnect from the external data source, if required, and to perform any other required cleanup.</span></span>

## <a name="examples"></a><span data-ttu-id="8daf7-164">Примеры</span><span class="sxs-lookup"><span data-stu-id="8daf7-164">Examples</span></span>
 <span data-ttu-id="8daf7-165">Следующие примеры демонстрируют код, нужный классу `ScriptMain` для создания компонента назначения.</span><span class="sxs-lookup"><span data-stu-id="8daf7-165">The examples that follow demonstrate code that is required in the `ScriptMain` class to create a destination component.</span></span>

> [!NOTE]
>  <span data-ttu-id="8daf7-166">В этих примерах используется таблица **Person. Address** в `AdventureWorks` образце базы данных и передайте ее первый и четвертый столбцы, столбцы **int \* AddressID**\* и **nvarchar (30) City** через поток данных.</span><span class="sxs-lookup"><span data-stu-id="8daf7-166">These examples use the **Person.Address** table in the `AdventureWorks` sample database and pass its first and fourth columns, the **int\*AddressID**\* and **nvarchar(30)City** columns, through the data flow.</span></span> <span data-ttu-id="8daf7-167">Эти же данные используются в образцах источника, преобразования и назначения, приведенных в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="8daf7-167">The same data is used in the source, transformation, and destination samples in this section.</span></span> <span data-ttu-id="8daf7-168">Для каждого примера приведены необходимые дополнительные условия и принимаемые предположения.</span><span class="sxs-lookup"><span data-stu-id="8daf7-168">Additional prerequisites and assumptions are documented for each example.</span></span>

### <a name="adonet-destination-example"></a><span data-ttu-id="8daf7-169">Пример назначения ADO.NET</span><span class="sxs-lookup"><span data-stu-id="8daf7-169">ADO.NET Destination Example</span></span>
 <span data-ttu-id="8daf7-170">В этом примере показан компонент назначения, который с помощью существующего диспетчера подключений [!INCLUDE[vstecado](../../includes/vstecado-md.md)] сохраняет данные из потока данных в таблицу [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8daf7-170">This example demonstrates a destination component that uses an existing [!INCLUDE[vstecado](../../includes/vstecado-md.md)] connection manager to save data from the data flow into a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span>

 <span data-ttu-id="8daf7-171">Для запуска этого образца кода необходимо настроить пакет и компонент следующим образом.</span><span class="sxs-lookup"><span data-stu-id="8daf7-171">If you want to run this sample code, you must configure the package and the component as follows:</span></span>

1.  <span data-ttu-id="8daf7-172">Создайте диспетчер соединений [!INCLUDE[vstecado](../../includes/vstecado-md.md)], использующий поставщик `SqlClient` для соединения с базой данных `AdventureWorks`.</span><span class="sxs-lookup"><span data-stu-id="8daf7-172">Create an [!INCLUDE[vstecado](../../includes/vstecado-md.md)] connection manager that uses the `SqlClient` provider to connect to the `AdventureWorks` database.</span></span>

2.  <span data-ttu-id="8daf7-173">Создайте целевую таблицу в базе данных `AdventureWorks`, выполнив следующую команду [!INCLUDE[tsql](../../includes/tsql-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="8daf7-173">Create a destination table by running the following [!INCLUDE[tsql](../../includes/tsql-md.md)] command in the `AdventureWorks` database:</span></span>

    ```
    CREATE TABLE [Person].[Address2]([AddressID] [int] NOT NULL,
        [City] [nvarchar](30) NOT NULL)
    ```

3.  <span data-ttu-id="8daf7-174">Добавьте новый компонент скрипта в область конструктора потока данных и настройте его в качестве назначения.</span><span class="sxs-lookup"><span data-stu-id="8daf7-174">Add a new Script component to the Data Flow designer surface and configure it as a destination.</span></span>

4.  <span data-ttu-id="8daf7-175">Соедините выход источника или преобразования, расположенного выше в потоке данных, с компонентом назначения в конструкторе служб [!INCLUDE[ssIS](../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8daf7-175">Connect the output of an upstream source or transformation to the destination component in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="8daf7-176">(Источник можно подключить непосредственно к назначению без каких-либо преобразований.) Этот вывод должен предоставлять данные из таблицы **Person. Address** `AdventureWorks` образца базы данных, содержащей по крайней мере столбцы **AddressID** и **City** .</span><span class="sxs-lookup"><span data-stu-id="8daf7-176">(You can connect a source directly to a destination without any transformations.) This output should provide data from the **Person.Address** table of the `AdventureWorks` sample database that contains at least the **AddressID** and **City** columns.</span></span>

5.  <span data-ttu-id="8daf7-177">Откройте **редактор преобразования "Скрипт"** .</span><span class="sxs-lookup"><span data-stu-id="8daf7-177">Open the **Script Transformation Editor**.</span></span> <span data-ttu-id="8daf7-178">На странице **Входные столбцы** выберите входные столбцы **AddressID** и **City**.</span><span class="sxs-lookup"><span data-stu-id="8daf7-178">On the **Input Columns** page, select the **AddressID** and **City** input columns.</span></span>

6.  <span data-ttu-id="8daf7-179">На странице **Входы и выходы** измените имя входа на более описательное, например **ВходАдреса**.</span><span class="sxs-lookup"><span data-stu-id="8daf7-179">On the **Inputs and Outputs** page, rename the input with a more descriptive name such as **MyAddressInput**.</span></span>

7.  <span data-ttu-id="8daf7-180">На странице **Диспетчеры соединений** добавьте или создайте диспетчер подключений [!INCLUDE[vstecado](../../includes/vstecado-md.md)] с описательным именем, например **MyADONETConnectionManager**.</span><span class="sxs-lookup"><span data-stu-id="8daf7-180">On the **Connection Managers** page, add or create the [!INCLUDE[vstecado](../../includes/vstecado-md.md)] connection manager with a name such as **MyADONETConnectionManager**.</span></span>

8.  <span data-ttu-id="8daf7-181">На странице **Скрипт** нажмите кнопку **Изменить скрипт** и введите следующий скрипт.</span><span class="sxs-lookup"><span data-stu-id="8daf7-181">On the **Script** page, click **Edit Script** and enter the script that follows.</span></span> <span data-ttu-id="8daf7-182">Затем закройте среду разработки скрипта.</span><span class="sxs-lookup"><span data-stu-id="8daf7-182">Then close the script development environment.</span></span>

9. <span data-ttu-id="8daf7-183">Закройте **редактор преобразования "Скрипт"** и запустите образец.</span><span class="sxs-lookup"><span data-stu-id="8daf7-183">Close the **Script Transformation Editor** and run the sample.</span></span>

```vb
Imports System.Data.SqlClient
...
Public Class ScriptMain
    Inherits UserComponent

    Dim connMgr As IDTSConnectionManager100
    Dim sqlConn As SqlConnection
    Dim sqlCmd As SqlCommand
    Dim sqlParam As SqlParameter

    Public Overrides Sub AcquireConnections(ByVal Transaction As Object)

        connMgr = Me.Connections.MyADONETConnectionManager
        sqlConn = CType(connMgr.AcquireConnection(Nothing), SqlConnection)

    End Sub

    Public Overrides Sub PreExecute()

        sqlCmd = New SqlCommand("INSERT INTO Person.Address2(AddressID, City) " & _
            "VALUES(@addressid, @city)", sqlConn)
        sqlParam = New SqlParameter("@addressid", SqlDbType.Int)
        sqlCmd.Parameters.Add(sqlParam)
        sqlParam = New SqlParameter("@city", SqlDbType.NVarChar, 30)
        sqlCmd.Parameters.Add(sqlParam)

    End Sub

    Public Overrides Sub MyAddressInput_ProcessInputRow(ByVal Row As MyAddressInputBuffer)
        With sqlCmd
            .Parameters("@addressid").Value = Row.AddressID
            .Parameters("@city").Value = Row.City
            .ExecuteNonQuery()
        End With
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
    SqlCommand sqlCmd;
    SqlParameter sqlParam;

    public override void AcquireConnections(object Transaction)
    {

        connMgr = this.Connections.MyADONETConnectionManager;
        sqlConn = (SqlConnection)connMgr.AcquireConnection(null);

    }

    public override void PreExecute()
    {

        sqlCmd = new SqlCommand("INSERT INTO Person.Address2(AddressID, City) " +
            "VALUES(@addressid, @city)", sqlConn);
        sqlParam = new SqlParameter("@addressid", SqlDbType.Int);
        sqlCmd.Parameters.Add(sqlParam);
        sqlParam = new SqlParameter("@city", SqlDbType.NVarChar, 30);
        sqlCmd.Parameters.Add(sqlParam);

    }

    public override void MyAddressInput_ProcessInputRow(MyAddressInputBuffer Row)
    {
        {
            sqlCmd.Parameters["@addressid"].Value = Row.AddressID;
            sqlCmd.Parameters["@city"].Value = Row.City;
            sqlCmd.ExecuteNonQuery();
        }
    }

    public override void ReleaseConnections()
    {

        connMgr.ReleaseConnection(sqlConn);

    }

}
```

### <a name="flat-file-destination-example"></a><span data-ttu-id="8daf7-184">Пример назначения «Неструктурированный файл»</span><span class="sxs-lookup"><span data-stu-id="8daf7-184">Flat File Destination Example</span></span>
 <span data-ttu-id="8daf7-185">В этом примере показан компонент назначения, который с помощью существующего диспетчера соединений с неструктурированными файлами сохраняет данные из потока данных в неструктурированный файл.</span><span class="sxs-lookup"><span data-stu-id="8daf7-185">This example demonstrates a destination component that uses an existing Flat File connection manager to save data from the data flow to a flat file.</span></span>

 <span data-ttu-id="8daf7-186">Для запуска этого образца кода необходимо настроить пакет и компонент следующим образом.</span><span class="sxs-lookup"><span data-stu-id="8daf7-186">If you want to run this sample code, you must configure the package and the component as follows:</span></span>

1.  <span data-ttu-id="8daf7-187">Создайте диспетчер соединений с неструктурированными файлами, соединяющийся с целевым файлом.</span><span class="sxs-lookup"><span data-stu-id="8daf7-187">Create a Flat File connection manager that connects to a destination file.</span></span> <span data-ttu-id="8daf7-188">Файл может не существовать; компонент назначения создаст его.</span><span class="sxs-lookup"><span data-stu-id="8daf7-188">The file does not have to exist; the destination component will create it.</span></span> <span data-ttu-id="8daf7-189">Настройте файл назначения как файл с разделителями-запятыми, содержащий столбцы **AddressID** и **City**.</span><span class="sxs-lookup"><span data-stu-id="8daf7-189">Configure the destination file as a comma-delimited file that contains the **AddressID** and **City** columns.</span></span>

2.  <span data-ttu-id="8daf7-190">Добавьте новый компонент скрипта в область конструктора потока данных и настройте его в качестве назначения.</span><span class="sxs-lookup"><span data-stu-id="8daf7-190">Add a new Script component to the Data Flow designer surface and configure it as a destination.</span></span>

3.  <span data-ttu-id="8daf7-191">Соедините выход источника или преобразования, расположенного выше в потоке данных, с компонентом назначения в конструкторе служб [!INCLUDE[ssIS](../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8daf7-191">Connect the output of an upstream source or transformation to the destination component in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="8daf7-192">(Источник можно подключить непосредственно к назначению без каких-либо преобразований.) Этот выход должен предоставлять данные из таблицы **Person. Address** `AdventureWorks` образца базы данных и содержать по крайней мере столбцы **AddressID** и **City** .</span><span class="sxs-lookup"><span data-stu-id="8daf7-192">(You can connect a source directly to a destination without any transformations.) This output should provide data from the **Person.Address** table of the `AdventureWorks` sample database, and should contain at least the **AddressID** and **City** columns.</span></span>

4.  <span data-ttu-id="8daf7-193">Откройте **редактор преобразования "Скрипт"** .</span><span class="sxs-lookup"><span data-stu-id="8daf7-193">Open the **Script Transformation Editor**.</span></span> <span data-ttu-id="8daf7-194">На странице **Входные столбцы** выберите столбцы **AddressID** и **City**.</span><span class="sxs-lookup"><span data-stu-id="8daf7-194">On the **Input Columns** page, select the **AddressID** and **City** columns.</span></span>

5.  <span data-ttu-id="8daf7-195">На странице **Входы и выходы** измените имя входа на более описательное, например **ВходАдреса**.</span><span class="sxs-lookup"><span data-stu-id="8daf7-195">On the **Inputs and Outputs** page, rename the input with a more descriptive name, such as **MyAddressInput**.</span></span>

6.  <span data-ttu-id="8daf7-196">На странице **Диспетчеры соединений** добавьте или создайте диспетчер подключений к неструктурированным файлам с описательным именем, например **MyFlatFileDestConnectionManager**.</span><span class="sxs-lookup"><span data-stu-id="8daf7-196">On the **Connection Managers** page, add or create the Flat File connection manager with a descriptive name such as **MyFlatFileDestConnectionManager**.</span></span>

7.  <span data-ttu-id="8daf7-197">На странице **Скрипт** нажмите кнопку **Изменить скрипт** и введите следующий скрипт.</span><span class="sxs-lookup"><span data-stu-id="8daf7-197">On the **Script** page, click **Edit Script** and enter the script that follows.</span></span> <span data-ttu-id="8daf7-198">Затем закройте среду разработки скрипта.</span><span class="sxs-lookup"><span data-stu-id="8daf7-198">Then close the script development environment.</span></span>

8.  <span data-ttu-id="8daf7-199">Закройте **редактор преобразования "Скрипт"** и запустите образец.</span><span class="sxs-lookup"><span data-stu-id="8daf7-199">Close the **Script Transformation Editor** and run the sample.</span></span>

```vb
Imports System.IO
...
Public Class ScriptMain
    Inherits UserComponent

    Dim copiedAddressFile As String
    Private textWriter As StreamWriter
    Private columnDelimiter As String = ","

    Public Overrides Sub AcquireConnections(ByVal Transaction As Object)

        Dim connMgr As IDTSConnectionManager100 = _
            Me.Connections.MyFlatFileDestConnectionManager
        copiedAddressFile = CType(connMgr.AcquireConnection(Nothing), String)

    End Sub

    Public Overrides Sub PreExecute()

        textWriter = New StreamWriter(copiedAddressFile, False)

    End Sub

    Public Overrides Sub MyAddressInput_ProcessInputRow(ByVal Row As MyAddressInputBuffer)

        With textWriter
            If Not Row.AddressID_IsNull Then
                .Write(Row.AddressID)
            End If
            .Write(columnDelimiter)
            If Not Row.City_IsNull Then
                .Write(Row.City)
            End If
            .WriteLine()
        End With

    End Sub

    Public Overrides Sub PostExecute()

        textWriter.Close()

    End Sub

End Class
```

```csharp
using System.IO;
public class ScriptMain:
    UserComponent

{
    string copiedAddressFile;
    private StreamWriter textWriter;
    private string columnDelimiter = ",";

    public override void AcquireConnections(object Transaction)
    {

        IDTSConnectionManager100 connMgr = this.Connections.MyFlatFileDestConnectionManager;
        copiedAddressFile = (string) connMgr.AcquireConnection(null);

    }

    public override void PreExecute()
    {

        textWriter = new StreamWriter(copiedAddressFile, false);

    }

    public override void MyAddressInput_ProcessInputRow(MyAddressInputBuffer Row)
    {

        {
            if (!Row.AddressID_IsNull)
            {
                textWriter.Write(Row.AddressID);
            }
            textWriter.Write(columnDelimiter);
            if (!Row.City_IsNull)
            {
                textWriter.Write(Row.City);
            }
            textWriter.WriteLine();
        }

    }

    public override void PostExecute()
    {

        textWriter.Close();

    }

}
```

<span data-ttu-id="8daf7-200">![Значок Integration Services (маленький)](../media/dts-16.gif "Значок служб Integration Services (маленький)")  **следит за обновлениями Integration Services**</span><span class="sxs-lookup"><span data-stu-id="8daf7-200">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="8daf7-201">Чтобы загрузить новейшую документацию, статьи, образцы и видеоматериалы корпорации Майкрософт, а также лучшие решения участников сообщества, посетите страницу служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] на сайте MSDN:</span><span class="sxs-lookup"><span data-stu-id="8daf7-201">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="8daf7-202">Посетить страницу «Службы Integration Services» на сайте MSDN</span><span class="sxs-lookup"><span data-stu-id="8daf7-202">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="8daf7-203">Чтобы получать автоматические уведомления об этих обновлениях, подпишитесь на RSS-каналы, предлагаемые на этой странице.</span><span class="sxs-lookup"><span data-stu-id="8daf7-203">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="8daf7-204">См. также:</span><span class="sxs-lookup"><span data-stu-id="8daf7-204">See Also</span></span>
 <span data-ttu-id="8daf7-205">[Создание источника с помощью компонента скрипта](../extending-packages-scripting-data-flow-script-component-types/creating-a-source-with-the-script-component.md) [Разработка пользовательского компонента назначения](../extending-packages-custom-objects-data-flow-types/developing-a-custom-destination-component.md)</span><span class="sxs-lookup"><span data-stu-id="8daf7-205">[Creating a Source with the Script Component](../extending-packages-scripting-data-flow-script-component-types/creating-a-source-with-the-script-component.md) [Developing a Custom Destination Component](../extending-packages-custom-objects-data-flow-types/developing-a-custom-destination-component.md)</span></span>


