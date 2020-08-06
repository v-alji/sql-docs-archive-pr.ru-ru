---
title: Добавление средства просмотра данных в поток данных | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- data viewers [Integration Services]
- data flow [Integration Services], data viewers
- adding data viewers
ms.assetid: 5e573274-a170-4132-bfc8-a8ff3a8411e4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7abd76417552ec50da736afe024a5ae36ee6a2ae
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655306"
---
# <a name="add-a-data-viewer-to-a-data-flow"></a><span data-ttu-id="47ebe-102">Добавление средства просмотра данных к потоку данных</span><span class="sxs-lookup"><span data-stu-id="47ebe-102">Add a Data Viewer to a Data Flow</span></span>
  <span data-ttu-id="47ebe-103">В данном разделе рассматриваются добавление средства просмотра данных к потоку данных и настройка этого средства.</span><span class="sxs-lookup"><span data-stu-id="47ebe-103">This topic describes how to add and configure a data viewer in a data flow.</span></span> <span data-ttu-id="47ebe-104">Средство просмотра данных отображает данные, перемещаемые между двумя компонентами потока данных.</span><span class="sxs-lookup"><span data-stu-id="47ebe-104">A data viewer displays data that is moving between two data flow components.</span></span> <span data-ttu-id="47ebe-105">Например, средство просмотра данных может отображать данные, извлеченные из источника данных до того, как преобразование в потоке данных изменит данные.</span><span class="sxs-lookup"><span data-stu-id="47ebe-105">For example, a data viewer can display the data that is extracted from a data source before a transformation in the data flow modifies the data.</span></span>  
  
 <span data-ttu-id="47ebe-106">Путь связывает компоненты в потоке данных при помощи соединения выхода одного компонента потока данных с входом другого.</span><span class="sxs-lookup"><span data-stu-id="47ebe-106">A path connects components in a data flow by connecting the output of one data flow component to the input of another component.</span></span>  
  
 <span data-ttu-id="47ebe-107">До того как добавить средства просмотра данных в пакет, он должен содержать задачу потока данных и не менее двух подключенных компонентов потока данных.</span><span class="sxs-lookup"><span data-stu-id="47ebe-107">Before you can add data viewers to a package, the package must include a Data Flow task and at least two data flow components that are connected.</span></span>  
  
### <a name="to-add-a-data-viewer-to-a-data-flow"></a><span data-ttu-id="47ebe-108">Добавление средства просмотра данных к потоку данных</span><span class="sxs-lookup"><span data-stu-id="47ebe-108">To add a data viewer to a data flow</span></span>  
  
1.  <span data-ttu-id="47ebe-109">В среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]откройте проект служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , содержащий необходимый пакет.</span><span class="sxs-lookup"><span data-stu-id="47ebe-109">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="47ebe-110">Чтобы открыть пакет, дважды щелкните его в обозревателе решений.</span><span class="sxs-lookup"><span data-stu-id="47ebe-110">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="47ebe-111">Перейдите на вкладку **Поток управления** , если она еще не активирована.</span><span class="sxs-lookup"><span data-stu-id="47ebe-111">Click the **Control Flow** tab, if it is not already active.</span></span>  
  
4.  <span data-ttu-id="47ebe-112">Щелкните задачу потока данных, к потоку данных которой нужно подключить средство просмотра данных, затем перейдите на вкладку **Поток данных** .</span><span class="sxs-lookup"><span data-stu-id="47ebe-112">Click the Data Flow task to whose data flow you want to attach a data viewer and then click the **Data Flow** tab.</span></span>  
  
5.  <span data-ttu-id="47ebe-113">Щелкните правой кнопкой мыши путь между двумя компонентами потока данных, затем выберите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="47ebe-113">Right-click a path between two data flow components, and click **Edit**.</span></span>  
  
6.  <span data-ttu-id="47ebe-114">На странице **Общие** можно просматривать и изменять свойства путей.</span><span class="sxs-lookup"><span data-stu-id="47ebe-114">On the **General** page, you can view and edit path properties.</span></span> <span data-ttu-id="47ebe-115">Например, в раскрывающемся списке **PathAnnotation** можно выбрать заметку, отображаемую рядом с путем.</span><span class="sxs-lookup"><span data-stu-id="47ebe-115">For example, from the **PathAnnotation** drop-down list you can select the annotation that appears next to the path.</span></span>  
  
7.  <span data-ttu-id="47ebe-116">На странице **Метаданные** можно просмотреть метаданные столбца и скопировать их в буфер обмена.</span><span class="sxs-lookup"><span data-stu-id="47ebe-116">On the **Metadata** page, you can view the column metadata and copy the metadata to the Clipboard.</span></span>  
  
8.  <span data-ttu-id="47ebe-117">На странице **Средство просмотра данных** щелкните **Включить средство просмотра данных**.</span><span class="sxs-lookup"><span data-stu-id="47ebe-117">On the **Data Viewer** page, click **Enable data viewer**.</span></span>  
  
9. <span data-ttu-id="47ebe-118">В области «Отображаемые столбцы» выберите столбцы, которые нужно отображать в средстве просмотра данных.</span><span class="sxs-lookup"><span data-stu-id="47ebe-118">In the Columns to display area, select the columns you want to display in the data viewer.</span></span> <span data-ttu-id="47ebe-119">По умолчанию выбраны все доступные столбцы, их перечень содержится в списке **Отображенные столбцы** .</span><span class="sxs-lookup"><span data-stu-id="47ebe-119">By default, all the available columns are selected and listed in the **Displayed Columns** list.</span></span> <span data-ttu-id="47ebe-120">Переместите ненужные столбцы в список **Неиспользуемые столбцы** . Для этого выберите их, а затем нажмите стрелку влево.</span><span class="sxs-lookup"><span data-stu-id="47ebe-120">Move columns that you do not want to use to the **Unused Column** list by selecting them and then clicking the left arrow.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="47ebe-121">Значения типа данных DT_DATE, DT_DBTIME2, DT_FILETIME, DT_DBTIMESTAMP, DT_DBTIMESTAMP2 и DT_DBTIMESTAMPOFFSET отображаются в сетке как строки, форматированные по стандарту ISO 8601, а разделитель `T` заменяется пробелом.</span><span class="sxs-lookup"><span data-stu-id="47ebe-121">In the grid, values that represent the DT_DATE, DT_DBTIME2, DT_FILETIME, DT_DBTIMESTAMP, DT_DBTIMESTAMP2, and DT_DBTIMESTAMPOFFSET data types appear as ISO 8601 formatted strings and a space separator replaces the `T` separator.</span></span> <span data-ttu-id="47ebe-122">Значения типов данных DT_DATE и DT_FILETIME имеют семь разрядов для хранения долей секунды.</span><span class="sxs-lookup"><span data-stu-id="47ebe-122">Values that represent the DT_DATE and DT_FILETIME data types include seven digits for fractional seconds.</span></span> <span data-ttu-id="47ebe-123">Так как тип данных DT_FILETIME хранит доли секунды только в трех разрядах, в остальных четырех выводятся нули.</span><span class="sxs-lookup"><span data-stu-id="47ebe-123">Because the DT_FILETIME data type stores only three digits of fractional seconds, the grid displays zeros for the remaining four digits.</span></span> <span data-ttu-id="47ebe-124">Значения типа DT_DBTIMESTAMP имеют три разряда для хранения долей секунды.</span><span class="sxs-lookup"><span data-stu-id="47ebe-124">Values that represent the DT_DBTIMESTAMP data type include three digits for fractional seconds.</span></span> <span data-ttu-id="47ebe-125">У типов данных DT_DBTIME2, DT_DBTIMESTAMP2 и DT_DBTIMESTAMPOFFSET число разрядов для долей секунды соответствует масштабу, указанному для типа данных столбца.</span><span class="sxs-lookup"><span data-stu-id="47ebe-125">For values that represent the DT_DBTIME2, DT_DBTIMESTAMP2, and DT_DBTIMESTAMPOFFSET data types, the number of digits for fractional seconds corresponds to the scale specified for the column's data type.</span></span> <span data-ttu-id="47ebe-126">Дополнительные сведения о форматах ISO 8601 см. в разделе [Date and Time Formats](../../2014/integration-services/date-and-time-formats.md).</span><span class="sxs-lookup"><span data-stu-id="47ebe-126">For more information about ISO 8601 formats, see [Date and Time Formats](../../2014/integration-services/date-and-time-formats.md).</span></span> <span data-ttu-id="47ebe-127">Дополнительные сведения о типах данных см. в разделе [Integration Services Data Types](data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="47ebe-127">For more information about data types, see [Integration Services Data Types](data-flow/integration-services-data-types.md).</span></span>  
  
10. <span data-ttu-id="47ebe-128">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="47ebe-128">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47ebe-129">См. также:</span><span class="sxs-lookup"><span data-stu-id="47ebe-129">See Also</span></span>  
 <span data-ttu-id="47ebe-130">[Преобразования служб Integration Services](data-flow/transformations/integration-services-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="47ebe-130">[Integration Services Transformations](data-flow/transformations/integration-services-transformations.md) </span></span>  
 <span data-ttu-id="47ebe-131">[Пути служб Integration Services](data-flow/integration-services-paths.md) </span><span class="sxs-lookup"><span data-stu-id="47ebe-131">[Integration Services Paths](data-flow/integration-services-paths.md) </span></span>  
 <span data-ttu-id="47ebe-132">[Поток данных](data-flow/data-flow.md) </span><span class="sxs-lookup"><span data-stu-id="47ebe-132">[Data Flow](data-flow/data-flow.md) </span></span>  
 [<span data-ttu-id="47ebe-133">Отладка потока данных</span><span class="sxs-lookup"><span data-stu-id="47ebe-133">Debugging Data Flow</span></span>](troubleshooting/debugging-data-flow.md)  
  
  
