---
title: Отладка потока данных | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- progress reporting [Integration Services]
- data viewers [Integration Services]
- data flow [Integration Services], debugging
- debugging [Integration Services], data flow
- counting rows
ms.assetid: 1c574f1b-54f7-4c05-8e42-8620e2c1df0f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ed1d1b7ebb119d452ca3de92fdad47552d1cc36c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734270"
---
# <a name="debugging-data-flow"></a><span data-ttu-id="d2473-102">Отладка потока данных</span><span class="sxs-lookup"><span data-stu-id="d2473-102">Debugging Data Flow</span></span>
  [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="d2473-103">[!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] и конструктор служб [!INCLUDE[ssIS](../../includes/ssis-md.md)] содержат функции и средства, используемые для исправления ошибок в потоках данных пакета служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d2473-103">[!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] and the [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer include features and tools that you can use to troubleshoot the data flows in an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package.</span></span>  
  
-   [!INCLUDE[ssIS](../../includes/ssis-md.md)] <span data-ttu-id="d2473-104">включает средства просмотра данных.</span><span class="sxs-lookup"><span data-stu-id="d2473-104">Designer provides data viewers.</span></span>  
  
-   [!INCLUDE[ssIS](../../includes/ssis-md.md)] <span data-ttu-id="d2473-105">и в преобразованиях служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d2473-105">Designer and [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] transformations provide row counts.</span></span>  
  
-   [!INCLUDE[ssIS](../../includes/ssis-md.md)] <span data-ttu-id="d2473-106">во время выполнения предоставляет отчет о ходе выполнения.</span><span class="sxs-lookup"><span data-stu-id="d2473-106">Designer provides progress reporting at run time.</span></span>  
  
## <a name="data-viewers"></a><span data-ttu-id="d2473-107">Средства просмотра данных</span><span class="sxs-lookup"><span data-stu-id="d2473-107">Data Viewers</span></span>  
 <span data-ttu-id="d2473-108">Средства просмотра данных служат для просмотра данных, передаваемых между двумя компонентами потока данных.</span><span class="sxs-lookup"><span data-stu-id="d2473-108">Data viewers display data between two components in a data flow.</span></span> <span data-ttu-id="d2473-109">Средства просмотра данных могут отображать данные при первом попадании в поток после извлечения из источника, до и после обновления данных в ходе преобразования, а также перед загрузкой их в назначения.</span><span class="sxs-lookup"><span data-stu-id="d2473-109">Data viewers can display data when the data is extracted from a data source and first enters a data flow, before and after a transformation updates the data, and before the data is loaded into its destination.</span></span>  
  
 <span data-ttu-id="d2473-110">Для просмотра данных следует подключить средство просмотра данных к пути, соединяющему два компонента потока данных.</span><span class="sxs-lookup"><span data-stu-id="d2473-110">To view the data, you attach data viewers to the path that connects two data flow components.</span></span> <span data-ttu-id="d2473-111">Возможность просмотра данных, передаваемых между компонентами потока данных, облегчает выявление непредвиденных значений данных, наблюдение за процессом изменения значений столбцов при преобразовании, а также определение причины аварийного завершения преобразования.</span><span class="sxs-lookup"><span data-stu-id="d2473-111">The ability to view data between data flow components makes it easier to identify unexpected data values, view the way a transformation changes column values, and discover the reason that a transformation fails.</span></span> <span data-ttu-id="d2473-112">Например, можно обнаружить, что уточняющий запрос в ссылочной таблице завершился аварийно, и устранить причину этого, добавив преобразование, передающее определенные по умолчанию данные в пустые столбцы.</span><span class="sxs-lookup"><span data-stu-id="d2473-112">For example, you may find that a lookup in a reference table fails, and to correct this you may want to add a transformation that provides default data for blank columns.</span></span>  
  
 <span data-ttu-id="d2473-113">В средстве просмотра данные могут отображаться в сетке.</span><span class="sxs-lookup"><span data-stu-id="d2473-113">A data viewer can display data in a grid.</span></span> <span data-ttu-id="d2473-114">Для использования сетки необходимо выбрать отображаемые столбцы.</span><span class="sxs-lookup"><span data-stu-id="d2473-114">Using a grid, you select the columns to display.</span></span> <span data-ttu-id="d2473-115">Значения выбранных столбцов отображаются в табличном формате.</span><span class="sxs-lookup"><span data-stu-id="d2473-115">The values for the selected columns display in a tabular format.</span></span>  
  
 <span data-ttu-id="d2473-116">К одному пути можно подключить несколько средств просмотра данных.</span><span class="sxs-lookup"><span data-stu-id="d2473-116">You can also include multiple data viewers on a path.</span></span> <span data-ttu-id="d2473-117">Одни и те же данные можно просматривать в различных форматах. Например, можно создать представление данных в виде диаграммы и сетки или создать различные средства просмотра данных для различных столбцов.</span><span class="sxs-lookup"><span data-stu-id="d2473-117">You can display the same data in different formats-for example, create a chart view and a grid view of the data-or create different data viewers for different columns of data.</span></span>  
  
 <span data-ttu-id="d2473-118">При добавлении средства просмотра данных к пути конструктор [!INCLUDE[ssIS](../../includes/ssis-md.md)] добавляет значок средства просмотра данных в область конструктора вкладки **Поток данных** рядом с местоположением.</span><span class="sxs-lookup"><span data-stu-id="d2473-118">When you add a data viewer to a path, [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer adds a data viewer icon to the design surface of the **Data Flow** tab, next to the path.</span></span> <span data-ttu-id="d2473-119">Преобразования с несколькими выходами (например, преобразование «Условное разбиение») могут иметь средство просмотра данных для каждого из путей.</span><span class="sxs-lookup"><span data-stu-id="d2473-119">Transformations that can have multiple outputs, such as the Conditional Split transformation, can include a data viewer on each path.</span></span>  
  
 <span data-ttu-id="d2473-120">Во время выполнения открывается окно **Средство просмотра данных** , отображающее данные в формате этого средства.</span><span class="sxs-lookup"><span data-stu-id="d2473-120">At run time, a **Data Viewer** window opens and displays the information specified by the data viewer format.</span></span> <span data-ttu-id="d2473-121">Например, средство просмотра данных, использующее формат сетки, отображает данные для выбранных столбцов, число выходных строк, переданных компоненту потока данных, и число отображенных строк.</span><span class="sxs-lookup"><span data-stu-id="d2473-121">For example, a data viewer that uses the grid format shows data for the selected columns, the number of output rows passed to the data flow component, and the number of rows displayed.</span></span> <span data-ttu-id="d2473-122">Данные отображаются побуферно, и в зависимости от ширины строк в потоке данных буфер может содержать большее или меньшее число строк.</span><span class="sxs-lookup"><span data-stu-id="d2473-122">The information displays buffer by buffer and, depending on the width of the rows in the data flow, a buffer may contain more or fewer rows.</span></span>  
  
 <span data-ttu-id="d2473-123">В диалоговом окне **Средство просмотра данных** можно копировать данные в буфер обмена, удалять все данные из таблицы, изменять настройку средства просмотра данных, возобновлять поток данных, а также отсоединять или присоединять средство просмотра данных.</span><span class="sxs-lookup"><span data-stu-id="d2473-123">In the **Data Viewer** dialog box, you can copy the data to the Clipboard, clear all data from the table, reconfigure the data viewer, resume the flow of data, and detach or attach the data viewer.</span></span>  
  
#### <a name="to-add-a-data-viewer"></a><span data-ttu-id="d2473-124">Добавление средства просмотра данных</span><span class="sxs-lookup"><span data-stu-id="d2473-124">To add a data viewer</span></span>  
  
-   [<span data-ttu-id="d2473-125">Добавление средства просмотра данных к потоку данных</span><span class="sxs-lookup"><span data-stu-id="d2473-125">Add a Data Viewer to a Data Flow</span></span>](../add-a-data-viewer-to-a-data-flow.md)  
  
## <a name="row-counts"></a><span data-ttu-id="d2473-126">Счетчики строк</span><span class="sxs-lookup"><span data-stu-id="d2473-126">Row Counts</span></span>  
 <span data-ttu-id="d2473-127">Число строк, переданных по данному пути, отображается в области конструктора вкладки **Поток данных** в конструкторе служб [!INCLUDE[ssIS](../../includes/ssis-md.md)] сразу после пути.</span><span class="sxs-lookup"><span data-stu-id="d2473-127">The number of rows that have passed through a path is displayed on the design surface of the **Data Flow** tab in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer next to the path.</span></span> <span data-ttu-id="d2473-128">Количество периодически обновляется по мере перемещения данных по пути.</span><span class="sxs-lookup"><span data-stu-id="d2473-128">The number is updated periodically while the data moves through the path.</span></span>  
  
 <span data-ttu-id="d2473-129">Также для захвата конечного числа строк в переменную можно добавить преобразование «Подсчет строк» в поток данных.</span><span class="sxs-lookup"><span data-stu-id="d2473-129">You can also add a Row Count transformation to the data flow to capture the final row count in a variable.</span></span> <span data-ttu-id="d2473-130">Дополнительные сведения см. в разделе [Row Count Transformation](../data-flow/transformations/row-count-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="d2473-130">For more information, see [Row Count Transformation](../data-flow/transformations/row-count-transformation.md).</span></span>  
  
## <a name="progress-reporting"></a><span data-ttu-id="d2473-131">Отчет о состоянии</span><span class="sxs-lookup"><span data-stu-id="d2473-131">Progress Reporting</span></span>  
 <span data-ttu-id="d2473-132">При запуске пакета ход его выполнения можно просматривать в области конструктора вкладки [!INCLUDE[ssIS](../../includes/ssis-md.md)] Поток данных **конструктора служб** , где каждый компонент потока данных изображается цветом, показывающим его состояние.</span><span class="sxs-lookup"><span data-stu-id="d2473-132">When you run a package, [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer depicts progress on the design surface of the **Data Flow** tab by displaying each data flow component in a color that indicates status.</span></span> <span data-ttu-id="d2473-133">При запуске какого-либо компонента его изображение из бесцветного становится желтым, а после успешного завершения — зеленым.</span><span class="sxs-lookup"><span data-stu-id="d2473-133">When each component starts to perform its work, it changes from no color to yellow, and when it finishes successfully, it changes to green.</span></span> <span data-ttu-id="d2473-134">Красный цвет указывает на аварийное завершение компонента.</span><span class="sxs-lookup"><span data-stu-id="d2473-134">A red color indicates that the component failed.</span></span>  
  
 <span data-ttu-id="d2473-135">В следующей таблице приводится описание цветового кодирования.</span><span class="sxs-lookup"><span data-stu-id="d2473-135">The following table describes the color-coding.</span></span>  
  
|<span data-ttu-id="d2473-136">Color</span><span class="sxs-lookup"><span data-stu-id="d2473-136">Color</span></span>|<span data-ttu-id="d2473-137">Description</span><span class="sxs-lookup"><span data-stu-id="d2473-137">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d2473-138">Бесцветный</span><span class="sxs-lookup"><span data-stu-id="d2473-138">No color</span></span>|<span data-ttu-id="d2473-139">Ожидание вызова подсистемой обработки потока данных.</span><span class="sxs-lookup"><span data-stu-id="d2473-139">Waiting to be called by the data flow engine.</span></span>|  
|<span data-ttu-id="d2473-140">Желтый</span><span class="sxs-lookup"><span data-stu-id="d2473-140">Yellow</span></span>|<span data-ttu-id="d2473-141">Выполнение преобразования, извлечения данных или загрузки данных.</span><span class="sxs-lookup"><span data-stu-id="d2473-141">Performing a transformation, extracting data, or loading data.</span></span>|  
|<span data-ttu-id="d2473-142">Зеленый</span><span class="sxs-lookup"><span data-stu-id="d2473-142">Green</span></span>|<span data-ttu-id="d2473-143">Успешное завершение.</span><span class="sxs-lookup"><span data-stu-id="d2473-143">Ran successfully.</span></span>|  
|<span data-ttu-id="d2473-144">красный</span><span class="sxs-lookup"><span data-stu-id="d2473-144">red</span></span>|<span data-ttu-id="d2473-145">Завершение с ошибками.</span><span class="sxs-lookup"><span data-stu-id="d2473-145">Ran with errors.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d2473-146">См. также:</span><span class="sxs-lookup"><span data-stu-id="d2473-146">See Also</span></span>  
 [<span data-ttu-id="d2473-147">Инструменты устранения неполадок при разработке пакета</span><span class="sxs-lookup"><span data-stu-id="d2473-147">Troubleshooting Tools for Package Development</span></span>](troubleshooting-tools-for-package-development.md)  
  
  
