---
title: Задание свойств для компонента потока данных | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- components [Integration Services], properties
ms.assetid: 73000ef6-52a2-4dec-8320-0e79acf0c2c5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1fd045ba076eed2d65d801015b881a477976f5d6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667335"
---
# <a name="set-the-properties-of-a-data-flow-component"></a><span data-ttu-id="0d259-102">Установление свойств компонента потока данных</span><span class="sxs-lookup"><span data-stu-id="0d259-102">Set the Properties of a Data Flow Component</span></span>
  <span data-ttu-id="0d259-103">Чтобы задать свойства компонентов потока данных, которые включают источники, целевые объекты и преобразования, можно использовать следующие компоненты.</span><span class="sxs-lookup"><span data-stu-id="0d259-103">To set the properties of data flow components, which include sources, destinations, and transformations, use one of the following features:</span></span>  
  
-   <span data-ttu-id="0d259-104">Редакторы компонентов, предоставляемые службами [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0d259-104">The component editors that [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] provides.</span></span> <span data-ttu-id="0d259-105">В редакторы компонентов включены только пользовательские свойства каждого компонента потока данных.</span><span class="sxs-lookup"><span data-stu-id="0d259-105">These editors include only the custom properties of each data flow component.</span></span>  
  
-   <span data-ttu-id="0d259-106">В окне " **Свойства** " перечислены характерные свойства каждого компонента, а также общие свойства для всех элементов потока данных.</span><span class="sxs-lookup"><span data-stu-id="0d259-106">The **Properties** window lists the component-level custom properties of each element, as well as the properties common to all data flow elements.</span></span>  
  
-   <span data-ttu-id="0d259-107">Диалоговое окно **Расширенный редактор** предоставляет доступ к пользовательским свойствам каждого компонента.</span><span class="sxs-lookup"><span data-stu-id="0d259-107">The **Advanced Editor** dialog box provides access to custom properties for each component.</span></span> <span data-ttu-id="0d259-108">Диалоговое окно **Расширенный редактор** также предоставляет доступ к общим свойствам всех компонентов потока данных — к свойствам входов, выходов, выводов ошибок на выходе, а также к свойствам столбцов и внешних столбцов.</span><span class="sxs-lookup"><span data-stu-id="0d259-108">The **Advanced Editor** dialog box also provides access to the properties common to all data flow components-the properties of inputs, outputs, error outputs, columns, and external columns.</span></span>  
  
### <a name="to-set-the-properties-of-a-data-flow-component-by-using-a-component-editor"></a><span data-ttu-id="0d259-109">Задание свойств компонента потока данных с помощью редактора компонентов</span><span class="sxs-lookup"><span data-stu-id="0d259-109">To set the properties of a data flow component by using a component editor</span></span>  
  
1.  <span data-ttu-id="0d259-110">В среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]откройте проект служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , содержащий необходимый пакет.</span><span class="sxs-lookup"><span data-stu-id="0d259-110">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="0d259-111">Чтобы открыть пакет, дважды щелкните его в обозревателе решений.</span><span class="sxs-lookup"><span data-stu-id="0d259-111">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="0d259-112">Выберите вкладку **Поток управления** и дважды щелкните задачу потока данных, содержащую компонент, который необходимо просмотреть и изменить.</span><span class="sxs-lookup"><span data-stu-id="0d259-112">Click the **Control Flow** tab, and then double-click the Data Flow task that contains the data flow with the component whose properties you want to view and modify.</span></span>  
  
4.  <span data-ttu-id="0d259-113">Дважды щелкните компонент потока данных.</span><span class="sxs-lookup"><span data-stu-id="0d259-113">Double-click the data flow component.</span></span>  
  
5.  <span data-ttu-id="0d259-114">В редакторе компонента просмотрите или измените значения свойств, затем закройте редактор.</span><span class="sxs-lookup"><span data-stu-id="0d259-114">In the component editor, view or modify the property values, and then close the editor.</span></span>  
  
6.  <span data-ttu-id="0d259-115">Чтобы сохранить измененный пакет, в меню **Файл** выберите команду **Сохранить выбранные элементы**.</span><span class="sxs-lookup"><span data-stu-id="0d259-115">To save the updated package, on the **File** menu, click **Save Selected Items**.</span></span>  
  
### <a name="to-set-the-properties-of-a-data-flow-component-by-using-the-properties-window"></a><span data-ttu-id="0d259-116">Задание свойств компонента потока данных с помощью окна «Свойства»</span><span class="sxs-lookup"><span data-stu-id="0d259-116">To set the properties of a data flow component by using the Properties window</span></span>  
  
1.  <span data-ttu-id="0d259-117">В среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]откройте проект служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , содержащий необходимый пакет.</span><span class="sxs-lookup"><span data-stu-id="0d259-117">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="0d259-118">Чтобы открыть пакет, дважды щелкните его в обозревателе решений.</span><span class="sxs-lookup"><span data-stu-id="0d259-118">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="0d259-119">Выберите вкладку **Поток управления** и дважды щелкните задачу потока данных, содержащую компонент, который необходимо просмотреть и изменить.</span><span class="sxs-lookup"><span data-stu-id="0d259-119">Click the **Control Flow** tab, and then double-click the Data Flow task that contains the component whose properties you want to view and modify.</span></span>  
  
4.  <span data-ttu-id="0d259-120">Щелкните правой кнопкой мыши компонент потока данных и выберите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="0d259-120">Right-click the data flow component, and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="0d259-121">Просмотрите или измените значения свойств, затем закройте окно **Свойства** .</span><span class="sxs-lookup"><span data-stu-id="0d259-121">View or modify the property values, and then close the **Properties** window.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="0d259-122">Многие свойства доступны только для чтения, и их нельзя изменить.</span><span class="sxs-lookup"><span data-stu-id="0d259-122">Many properties are read-only, and cannot be modified.</span></span>  
  
6.  <span data-ttu-id="0d259-123">Чтобы сохранить измененный пакет, в меню **Файл** выберите команду **Сохранить выбранные элементы**.</span><span class="sxs-lookup"><span data-stu-id="0d259-123">To save the updated package, on the **File** menu, click **Save Selected Items**.</span></span>  
  
### <a name="to-set-the-properties-of-a-data-flow-component-by-using-the-advanced-editor"></a><span data-ttu-id="0d259-124">Задание свойств компонента потока данных с помощью расширенного редактора</span><span class="sxs-lookup"><span data-stu-id="0d259-124">To set the properties of a data flow component by using the Advanced Editor</span></span>  
  
1.  <span data-ttu-id="0d259-125">В среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]откройте проект служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , содержащий необходимый пакет.</span><span class="sxs-lookup"><span data-stu-id="0d259-125">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="0d259-126">Чтобы открыть пакет, дважды щелкните его в обозревателе решений.</span><span class="sxs-lookup"><span data-stu-id="0d259-126">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="0d259-127">Выберите вкладку **Поток управления** и дважды щелкните задачу потока данных, содержащую компонент, который необходимо просмотреть или изменить.</span><span class="sxs-lookup"><span data-stu-id="0d259-127">Click the **Control Flow** tab, and then double-click the Data Flow task that contains the component you want to view or modify.</span></span>  
  
4.  <span data-ttu-id="0d259-128">В конструкторе потока данных щелкните компонент потока данных правой кнопкой и выберите **Показать расширенный редактор**.</span><span class="sxs-lookup"><span data-stu-id="0d259-128">In the data flow designer, right-click the data flow component, and then click **Show Advanced Editor**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="0d259-129">В [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]компоненты потока данных, которые поддерживают несколько входов, не могут использовать **Расширенный редактор**.</span><span class="sxs-lookup"><span data-stu-id="0d259-129">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], data flow components that support multiple inputs cannot use the **Advanced Editor**.</span></span>  
  
5.  <span data-ttu-id="0d259-130">В диалоговом окне **Расширенный редактор** выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="0d259-130">In the **Advanced Editor** dialog box, do any of the following steps:</span></span>  
  
    -   <span data-ttu-id="0d259-131">Перейдите на вкладку **Диспетчеры соединений** , чтобы просмотреть и определить соединение, которое использует компонент.</span><span class="sxs-lookup"><span data-stu-id="0d259-131">To view and specify the connection that the component uses, click the **Connection Managers** tab.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="0d259-132">На вкладке **Диспетчеры соединений** доступны только компоненты потоков данных, которые используют диспетчеры соединений для подключения к источникам данных, таким как файлы или базы данных.</span><span class="sxs-lookup"><span data-stu-id="0d259-132">The **Connection Managers** tab is available only to data flow components that use connection managers to connect to data sources such as files and databases</span></span>  
  
    -   <span data-ttu-id="0d259-133">Перейдите на вкладку **Свойства компонента** , чтобы просмотреть и изменить свойства уровня компонента.</span><span class="sxs-lookup"><span data-stu-id="0d259-133">To view and modify component-level properties, click the **Component Properties** tab.</span></span>  
  
    -   <span data-ttu-id="0d259-134">Перейдите на вкладку **Сопоставления столбцов** , чтобы просмотреть сопоставления между внешними столбцами и доступными выходами.</span><span class="sxs-lookup"><span data-stu-id="0d259-134">To view and modify mappings between external columns and the available output, click the **Column Mappings** tab.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="0d259-135">Вкладка **Сопоставление столбцов** доступна только для просмотра и редактирования источников и назначений.</span><span class="sxs-lookup"><span data-stu-id="0d259-135">The **Column Mappings** tab is available only when viewing or editing sources or destinations.</span></span>  
  
    -   <span data-ttu-id="0d259-136">Щелкните вкладку **Входные столбцы** для просмотра списка доступных входных столбцов и обновления имен выходных столбцов.</span><span class="sxs-lookup"><span data-stu-id="0d259-136">To view a list of the available input columns and to update the names of output columns, click the **Input Columns** tab.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="0d259-137">Вкладка «Входные столбцы» доступна только при работе с преобразованиями и назначениями.</span><span class="sxs-lookup"><span data-stu-id="0d259-137">The Input Columns tab is available only when working with transformations or destinations.</span></span> <span data-ttu-id="0d259-138">Дополнительные сведения см. в статье [Integration Services Transformations](transformations/integration-services-transformations.md).</span><span class="sxs-lookup"><span data-stu-id="0d259-138">For more information, see [Integration Services Transformations](transformations/integration-services-transformations.md).</span></span>  
  
    -   <span data-ttu-id="0d259-139">Выберите вкладку **Свойства входов и выходов** , чтобы просмотреть и изменить свойства входов, выходов, выводов ошибок на выходе, а также свойств столбцов, которые они содержат.</span><span class="sxs-lookup"><span data-stu-id="0d259-139">To view and modify the properties of inputs, outputs, and error outputs, and the properties of the columns they contain, click the **Input and Output Properties** tab.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="0d259-140">Источники не имеют входов.</span><span class="sxs-lookup"><span data-stu-id="0d259-140">Sources have no inputs.</span></span> <span data-ttu-id="0d259-141">Назначения не имеют выходов, за исключением возможного выхода ошибок.</span><span class="sxs-lookup"><span data-stu-id="0d259-141">Destinations have no outputs, except for an optional error output.</span></span>  
  
6.  <span data-ttu-id="0d259-142">Просмотрите или измените значения свойств.</span><span class="sxs-lookup"><span data-stu-id="0d259-142">View or modify the property values.</span></span>  
  
7.  <span data-ttu-id="0d259-143">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="0d259-143">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="0d259-144">Чтобы сохранить измененный пакет, в меню **Файл** выберите команду **Сохранить выбранные элементы**.</span><span class="sxs-lookup"><span data-stu-id="0d259-144">To save the updated package, on the **File** menu, click **Save Selected Items**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d259-145">См. также:</span><span class="sxs-lookup"><span data-stu-id="0d259-145">See Also</span></span>  
 [<span data-ttu-id="0d259-146">Преобразования служб Integration Services</span><span class="sxs-lookup"><span data-stu-id="0d259-146">Integration Services Transformations</span></span>](transformations/integration-services-transformations.md)  
  
  
