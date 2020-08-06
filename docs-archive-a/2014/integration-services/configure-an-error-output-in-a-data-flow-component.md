---
title: Настройка вывода ошибок в компоненте потока данных | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- errors [Integration Services], data flow components
- components [Integration Services], data flow
- error outputs [Integration Services]
ms.assetid: 53d7eeea-927d-4b45-8ea9-084e65ad5390
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ebd44383e27daa465576bb056a67f6dacad87b0a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750095"
---
# <a name="configure-an-error-output-in-a-data-flow-component"></a><span data-ttu-id="3cf42-102">Настройка вывода ошибок в компоненте потока данных</span><span class="sxs-lookup"><span data-stu-id="3cf42-102">Configure an Error Output in a Data Flow Component</span></span>
  <span data-ttu-id="3cf42-103">Многие компоненты потока данных поддерживают вывод ошибок. Основываясь на компоненте, конструктор [!INCLUDE[ssIS](../includes/ssis-md.md)] предлагает различные пути настройки вывода ошибок.</span><span class="sxs-lookup"><span data-stu-id="3cf42-103">Many data flow components support error outputs, and depending on the component, [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer provides different ways to configure an error output.</span></span> <span data-ttu-id="3cf42-104">Кроме настройки вывода ошибок, можно также настроить его столбцы.</span><span class="sxs-lookup"><span data-stu-id="3cf42-104">In addition to configuring an error output, you can also configure the columns of an error output.</span></span> <span data-ttu-id="3cf42-105">Сюда входит настройка столбцов **ErrorCode** и **ErrorColumn** , добавляемых этим компонентом.</span><span class="sxs-lookup"><span data-stu-id="3cf42-105">This includes configuring the **ErrorCode** and **ErrorColumn** columns that are added by the component.</span></span>  
  
## <a name="configuring-an-error-output"></a><span data-ttu-id="3cf42-106">Настройка вывода ошибок</span><span class="sxs-lookup"><span data-stu-id="3cf42-106">Configuring an Error Output</span></span>  
 <span data-ttu-id="3cf42-107">Настройку вывода ошибок можно производить двумя способами.</span><span class="sxs-lookup"><span data-stu-id="3cf42-107">To configure an error output, you have two options:</span></span>  
  
-   <span data-ttu-id="3cf42-108">С помощью диалогового окна **Настройка вывода ошибок** .</span><span class="sxs-lookup"><span data-stu-id="3cf42-108">Use the **Configure Error Output** dialog box.</span></span> <span data-ttu-id="3cf42-109">Это диалоговое окно можно использовать для настройки вывода ошибок в любом компоненте потока данных, поддерживающем выход ошибок.</span><span class="sxs-lookup"><span data-stu-id="3cf42-109">You can use this dialog box to configure an error output on any data flow component that supports an error output.</span></span>  
  
-   <span data-ttu-id="3cf42-110">Использовать диалоговое окно редактора этого компонента.</span><span class="sxs-lookup"><span data-stu-id="3cf42-110">Use the editor dialog box for the component.</span></span> <span data-ttu-id="3cf42-111">Некоторые компоненты позволяют настраивать вывод ошибок непосредственно через диалоговое окно редактора этого компонента.</span><span class="sxs-lookup"><span data-stu-id="3cf42-111">Some components let you configure error outputs directly from their editor dialog box.</span></span> <span data-ttu-id="3cf42-112">Однако через диалоговое окно редактора компонента нельзя настраивать вывод ошибок источника ADO NET, преобразования «Импорт столбца», преобразования «Команда OLE DB» и назначения [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact.</span><span class="sxs-lookup"><span data-stu-id="3cf42-112">However, you cannot configure error outputs from the editor dialog box for the ADO NET source, the Import Column transformation, the OLE DB Command transformation, or the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact destination.</span></span>  
  
 <span data-ttu-id="3cf42-113">Далее приводятся описания процедур настройки вывода ошибок с помощью этих диалоговых окон.</span><span class="sxs-lookup"><span data-stu-id="3cf42-113">The following procedures describe how to use these dialog boxes to configure error outputs.</span></span>  
  
#### <a name="to-configure-an-error-output-using-the-configure-error-output-dialog-box"></a><span data-ttu-id="3cf42-114">Настройка вывода ошибок с помощью диалогового окна «Настроить вывод ошибок»</span><span class="sxs-lookup"><span data-stu-id="3cf42-114">To configure an error output using the Configure Error Output dialog box</span></span>  
  
1.  <span data-ttu-id="3cf42-115">В среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]откройте проект служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , содержащий необходимый пакет.</span><span class="sxs-lookup"><span data-stu-id="3cf42-115">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="3cf42-116">Чтобы открыть пакет, дважды щелкните его в обозревателе решений.</span><span class="sxs-lookup"><span data-stu-id="3cf42-116">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="3cf42-117">В конструкторе служб [!INCLUDE[ssIS](../includes/ssis-md.md)] перейдите на вкладку **Поток данных** .</span><span class="sxs-lookup"><span data-stu-id="3cf42-117">In [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, click the **Data Flow** tab.</span></span>  
  
4.  <span data-ttu-id="3cf42-118">Перетащите вывод ошибок, представленный красной стрелкой, из компонента источника ошибок в другой компонент потока данных.</span><span class="sxs-lookup"><span data-stu-id="3cf42-118">Drag the error output, represented by the red arrow, from the component that is the source of the errors to another component in the data flow.</span></span>  
  
5.  <span data-ttu-id="3cf42-119">В диалоговом окне **Настройка вывода ошибок** выберите действие в столбцах **Ошибка** и **Усечение** для каждого столбца на входе компонента.</span><span class="sxs-lookup"><span data-stu-id="3cf42-119">In the **Configure Error Output** dialog box, select an action in the **Error** and **Truncation** columns for each column in the component input.</span></span>  
  
6.  <span data-ttu-id="3cf42-120">Чтобы сохранить измененный пакет, в меню **Файл** выберите команду **Сохранить выбранные элементы**.</span><span class="sxs-lookup"><span data-stu-id="3cf42-120">To save the updated package, on the **File** menu, click **Save Selected Items**.</span></span>  
  
#### <a name="to-add-an-error-output-using-the-editor-dialog-box-for-the-component"></a><span data-ttu-id="3cf42-121">Добавление вывода ошибок с помощью диалогового окна редактора компонента</span><span class="sxs-lookup"><span data-stu-id="3cf42-121">To add an error output using the editor dialog box for the component</span></span>  
  
1.  <span data-ttu-id="3cf42-122">В среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]откройте проект служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , содержащий необходимый пакет.</span><span class="sxs-lookup"><span data-stu-id="3cf42-122">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="3cf42-123">Чтобы открыть пакет, дважды щелкните его в обозревателе решений.</span><span class="sxs-lookup"><span data-stu-id="3cf42-123">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="3cf42-124">В конструкторе служб [!INCLUDE[ssIS](../includes/ssis-md.md)] перейдите на вкладку **Поток данных** .</span><span class="sxs-lookup"><span data-stu-id="3cf42-124">In [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, click the **Data Flow** tab.</span></span>  
  
4.  <span data-ttu-id="3cf42-125">Дважды щелкните компоненты потока данных, для которых необходимо настроить вывод ошибок, и в зависимости от компонента выполните следующее.</span><span class="sxs-lookup"><span data-stu-id="3cf42-125">Double-click the data flow components in which you want to configure an error output and, depending on the component, do one of the following steps:</span></span>  
  
    -   <span data-ttu-id="3cf42-126">Щелкните **Настроить вывод ошибок**.</span><span class="sxs-lookup"><span data-stu-id="3cf42-126">Click **Configure Error Output**.</span></span>  
  
    -   <span data-ttu-id="3cf42-127">Щелкните **Вывод ошибок**.</span><span class="sxs-lookup"><span data-stu-id="3cf42-127">Click **Error Output**.</span></span>  
  
5.  <span data-ttu-id="3cf42-128">Установите параметр **Ошибка** для каждого столбца.</span><span class="sxs-lookup"><span data-stu-id="3cf42-128">Set the **Error** option for each column.</span></span>  
  
6.  <span data-ttu-id="3cf42-129">Установите параметр **Усечение** для каждого столбца.</span><span class="sxs-lookup"><span data-stu-id="3cf42-129">Set the **Truncation** option for each column.</span></span>  
  
7.  <span data-ttu-id="3cf42-130">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="3cf42-130">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="3cf42-131">Чтобы сохранить измененный пакет, в меню **Файл** выберите команду **Сохранить выбранные элементы**.</span><span class="sxs-lookup"><span data-stu-id="3cf42-131">To save the updated package, on the **File** menu, click **Save Selected Items**.</span></span>  
  
## <a name="configuring-error-output-columns"></a><span data-ttu-id="3cf42-132">Настройка столбцов вывода ошибок</span><span class="sxs-lookup"><span data-stu-id="3cf42-132">Configuring Error Output Columns</span></span>  
 <span data-ttu-id="3cf42-133">Для настройки столбцов вывода ошибок используется вкладка **Свойства входов и выходов** диалогового окна **расширенного редактора** .</span><span class="sxs-lookup"><span data-stu-id="3cf42-133">To configure the error output columns, you have to use the **Input and Output Properties** tab of the **Advanced Editor** dialog box.</span></span>  
  
#### <a name="to-configure-error-output-columns"></a><span data-ttu-id="3cf42-134">Настройка столбцов вывода ошибок</span><span class="sxs-lookup"><span data-stu-id="3cf42-134">To configure error output columns</span></span>  
  
1.  <span data-ttu-id="3cf42-135">В среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]откройте проект служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , содержащий необходимый пакет.</span><span class="sxs-lookup"><span data-stu-id="3cf42-135">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="3cf42-136">Чтобы открыть пакет, дважды щелкните его в обозревателе решений.</span><span class="sxs-lookup"><span data-stu-id="3cf42-136">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="3cf42-137">В конструкторе служб [!INCLUDE[ssIS](../includes/ssis-md.md)] перейдите на вкладку **Поток данных** .</span><span class="sxs-lookup"><span data-stu-id="3cf42-137">In [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, click the **Data Flow** tab.</span></span>  
  
4.  <span data-ttu-id="3cf42-138">Щелкните правой кнопкой мыши компонент, столбцы вывода ошибок которого необходимо настроить, и выберите пункт **Показать расширенный редактор**.</span><span class="sxs-lookup"><span data-stu-id="3cf42-138">Right-click the component whose error output columns you want to configure and click **Show Advanced Editor**.</span></span>  
  
5.  <span data-ttu-id="3cf42-139">Откройте вкладку **Свойства входов и выходов** и разверните узлы **Вывод ошибок \<component name>** и **Выходные столбцы**.</span><span class="sxs-lookup"><span data-stu-id="3cf42-139">Click the **Input and Output Properties** tab and expand **\<component name> Error Output** and then expand **Output Columns**.</span></span>  
  
6.  <span data-ttu-id="3cf42-140">Щелкните столбец и обновите его свойства.</span><span class="sxs-lookup"><span data-stu-id="3cf42-140">Click a column and update its properties.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="3cf42-141">Список столбцов содержит столбцы входа компонента, столбцы **ErrorCode** и **ErrorColumn** , добавленные предшествующим выводом ошибок, и столбцы **ErrorCode** и **ErrorColumn** , добавленные данным компонентом.</span><span class="sxs-lookup"><span data-stu-id="3cf42-141">The list of columns includes the columns in the component input, the **ErrorCode** and **ErrorColumn** columns added by previous error outputs, and the **ErrorCode** and **ErrorColumn** columns added by this component.</span></span>  
  
7.  <span data-ttu-id="3cf42-142">Нажмите кнопку **ОК.**</span><span class="sxs-lookup"><span data-stu-id="3cf42-142">Click **OK.**</span></span>  
  
8.  <span data-ttu-id="3cf42-143">Чтобы сохранить измененный пакет, в меню **Файл** выберите команду **Сохранить выбранные элементы**.</span><span class="sxs-lookup"><span data-stu-id="3cf42-143">To save the updated package, on the **File** menu, click **Save Selected Items**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3cf42-144">См. также:</span><span class="sxs-lookup"><span data-stu-id="3cf42-144">See Also</span></span>  
 [<span data-ttu-id="3cf42-145">Обработка ошибок в данных</span><span class="sxs-lookup"><span data-stu-id="3cf42-145">Error Handling in Data</span></span>](data-flow/error-handling-in-data.md)  
  
  
