---
title: Диалоговое окно "обработка" (Analysis Services-многомерные данные) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.processdialog.f1
ms.assetid: c065248c-9001-4f0c-928f-9c59eccb618b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 369c121713894bba9b2ce6c40aa2869de49eaa72
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750259"
---
# <a name="process-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="76698-102">Диалоговое окно «Обработка» (службы Analysis Services — многомерные данные)</span><span class="sxs-lookup"><span data-stu-id="76698-102">Process Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="76698-103">Используйте диалоговое окно **Обработка** в средах [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] и [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] для обработки объектов служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="76698-103">Use the **Process** dialog box in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] and [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to process [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] objects.</span></span> <span data-ttu-id="76698-104">Можно вызвать диалоговое окно **Обработка** в среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] следующим образом:</span><span class="sxs-lookup"><span data-stu-id="76698-104">You can display the **Process** dialog box in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] by:</span></span>  
  
-   <span data-ttu-id="76698-105">Щелкнув правой кнопкой мыши проект служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , куб, измерение или структуру интеллектуального анализа данных в **обозревателе решений** и выбрав пункт **Обработка**.</span><span class="sxs-lookup"><span data-stu-id="76698-105">Right-clicking an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project, cube, dimension, or mining structure in **Solution Explorer** and selecting **Process**.</span></span>  
  
-   <span data-ttu-id="76698-106">Выбрав параметр **Обработка** панели инструментов на каждой странице компонента **конструктор кубов**, на каждой странице **конструктора измерений**или на страницах **Структуры интеллектуального анализа данных** и **Модели интеллектуального анализа данных\*\*\*\*конструктора моделей интеллектуального анализа данных**.</span><span class="sxs-lookup"><span data-stu-id="76698-106">Selecting **Process** from the toolbar on every page of **Cube Designer**, every page of **Dimension Designer**, or the **Mining Structure** and **Mining Models** pages of **Data Mining Model Designer**.</span></span>  
  
-   <span data-ttu-id="76698-107">Щелкнув правой кнопкой мыши на модель интеллектуальной обработки данных на странице **Модели интеллектуального анализа данных** в **конструкторе моделей интеллектуального анализа данных** и выбрав пункт **Обработать структуру интеллектуального анализа данных и все модели** или **Обработать модель**.</span><span class="sxs-lookup"><span data-stu-id="76698-107">Right-clicking a mining model in the **Mining Models** page of **Data Mining Model Designer** and selecting **Process Mining Structure and All Models** or **Process Model**.</span></span>  
  
 <span data-ttu-id="76698-108">Можно вызвать диалоговое окно **Обработка** в среде **SQL Server Management Studio** следующим образом:</span><span class="sxs-lookup"><span data-stu-id="76698-108">You can display the **Process** dialog box in **SQL Server Management Studio** by:</span></span>  
  
-   <span data-ttu-id="76698-109">Щелкнув правой кнопкой мыши базу данных служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , куб, группу мер, секцию, измерение, структуру интеллектуального анализа данных или модель интеллектуального анализа в **обозревателе объектов** и выбрав пункт **Обработка**.</span><span class="sxs-lookup"><span data-stu-id="76698-109">Right-clicking an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database, cube, measure group, partition, dimension, mining structure, or mining model in **Object Explorer** and selecting **Process**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="76698-110">Варианты</span><span class="sxs-lookup"><span data-stu-id="76698-110">Options</span></span>  
 <span data-ttu-id="76698-111">**Список объектов**</span><span class="sxs-lookup"><span data-stu-id="76698-111">**Object list**</span></span>  
 <span data-ttu-id="76698-112">Выберите объекты служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , которые должны быть обработаны, а также параметры обработки и установки, которые должны быть применены.</span><span class="sxs-lookup"><span data-stu-id="76698-112">Select the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] objects to be processed and the processing options and settings to be applied.</span></span> <span data-ttu-id="76698-113">Сетка содержит следующие столбцы:</span><span class="sxs-lookup"><span data-stu-id="76698-113">The grid contains the following columns:</span></span>  
  
 <span data-ttu-id="76698-114">**Имени объекта**</span><span class="sxs-lookup"><span data-stu-id="76698-114">**Object Name**</span></span>  
 <span data-ttu-id="76698-115">Отображает имя объекта, который должен быть обработан.</span><span class="sxs-lookup"><span data-stu-id="76698-115">Displays the name of the object to be processed.</span></span> <span data-ttu-id="76698-116">Значок слева от имени указывает тип объекта.</span><span class="sxs-lookup"><span data-stu-id="76698-116">The icon to the left of the name indicates the object type.</span></span>  
  
 <span data-ttu-id="76698-117">**Тип**</span><span class="sxs-lookup"><span data-stu-id="76698-117">**Type**</span></span>  
 <span data-ttu-id="76698-118">Отображает тип объекта, который должен быть обработан.</span><span class="sxs-lookup"><span data-stu-id="76698-118">Displays the type of the object to be processed.</span></span>  
  
 <span data-ttu-id="76698-119">**Параметры обработки**</span><span class="sxs-lookup"><span data-stu-id="76698-119">**Process Options**</span></span>  
 <span data-ttu-id="76698-120">Выберите тип обработки, которая должна быть выполнена над выделенным объектом.</span><span class="sxs-lookup"><span data-stu-id="76698-120">Select the type of processing to perform on the selected object.</span></span> <span data-ttu-id="76698-121">Дополнительные сведения о доступных параметрах обработки см. в разделе [Обработка объектов многомерной модели](multidimensional-models/processing-a-multidimensional-model-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="76698-121">For more information about available processing options, see [Multidimensional Model Object Processing](multidimensional-models/processing-a-multidimensional-model-analysis-services.md).</span></span>  
  
 <span data-ttu-id="76698-122">**Параметры**</span><span class="sxs-lookup"><span data-stu-id="76698-122">**Settings**</span></span>  
 <span data-ttu-id="76698-123">Отображает гиперссылку **Настроить** , если выбрана **Добавочная обработка** в **Параметрах обработки** для кубов, групп мер или секций.</span><span class="sxs-lookup"><span data-stu-id="76698-123">Displays the **Configure** hyperlink when you choose **Process Incremental** in **Process Options** for cubes, measure groups, or partitions.</span></span> <span data-ttu-id="76698-124">Щелкните ссылку **Настроить** для запуска диалогового окна **Добавочная обработка** .</span><span class="sxs-lookup"><span data-stu-id="76698-124">Click **Configure** to launch the **Incremental Update** dialog box.</span></span> <span data-ttu-id="76698-125">Дополнительные сведения о диалоговом окне **Добавочное обновление** см. в разделе [Диалоговое окно "Добавочное обновление" (службы Analysis Services — многомерные данные)](incremental-update-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="76698-125">For more information about the **Incremental Update** dialog box, see [Incremental Update Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](incremental-update-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="76698-126">**Удалить**</span><span class="sxs-lookup"><span data-stu-id="76698-126">**Remove**</span></span>  
 <span data-ttu-id="76698-127">Щелкните, чтобы удалить выбранные пункты из **списка объектов**.</span><span class="sxs-lookup"><span data-stu-id="76698-127">Click to remove the selected items from **Object list**.</span></span>  
  
 <span data-ttu-id="76698-128">**Анализ влияния**</span><span class="sxs-lookup"><span data-stu-id="76698-128">**Impact Analysis**</span></span>  
 <span data-ttu-id="76698-129">Выберите для открытия диалогового окна **Анализ влияния** и отображения объектов, которые связаны с задачей обработки.</span><span class="sxs-lookup"><span data-stu-id="76698-129">Click to open the **Impact Analysis** dialog box and display the objects that will be affected by the processing task.</span></span> <span data-ttu-id="76698-130">Дополнительные сведения о диалоговом окне **Анализ влияния** см. в разделе [Диалоговое окно "Анализ влияния" (службы Analysis Services — многомерные данные)](impact-analysis-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="76698-130">For more information about the **Impact Analysis** dialog box, see [Impact Analysis Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](impact-analysis-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="76698-131">Этот параметр недоступен, если параметр **Обработать затронутые объекты** выбран в диалоговом окне **Изменение настроек** .</span><span class="sxs-lookup"><span data-stu-id="76698-131">This option is disabled when the **Process affected objects** option is selected in the **Change Settings** dialog box.</span></span>  
  
 <span data-ttu-id="76698-132">**Изменить параметры**</span><span class="sxs-lookup"><span data-stu-id="76698-132">**Change Settings**</span></span>  
 <span data-ttu-id="76698-133">Выберите для открытия диалогового окна **Изменение настроек** и изменения настроек, которые управляют обработкой выделенных объектов, включая настройки пакетной обработки, настройки обратной записи и настройки ошибок ключа измерения.</span><span class="sxs-lookup"><span data-stu-id="76698-133">Click to open the **Change Settings** dialog box and change the settings that govern processing of the selected objects, including batch processing settings, writeback settings, and dimension key error settings.</span></span> <span data-ttu-id="76698-134">Дополнительные сведения о диалоговом окне **Изменение настроек** см. в разделе [Диалоговое окно "Изменение настроек" (службы Analysis Services — многомерные данные)](change-settings-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="76698-134">For more information about the **Change Settings** dialog box, see [Change Settings Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](change-settings-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="76698-135">**Выполнить**</span><span class="sxs-lookup"><span data-stu-id="76698-135">**Run**</span></span>  
 <span data-ttu-id="76698-136">Нажмите для обработки объектов.</span><span class="sxs-lookup"><span data-stu-id="76698-136">Click to process the objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76698-137">См. также:</span><span class="sxs-lookup"><span data-stu-id="76698-137">See Also</span></span>  
 <span data-ttu-id="76698-138">[Analysis Services конструкторов и диалоговых окон &#40;многомерных данных&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="76698-138">[Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="76698-139">Диалоговое окно "Ход обработки" &#40;Analysis Services многомерных данных&#41;</span><span class="sxs-lookup"><span data-stu-id="76698-139">Process Progress Dialog Box &#40;Analysis Services - Multidimensional Data&#41;</span></span>](process-progress-dialog-box-analysis-services-multidimensional-data.md)  
  
  
