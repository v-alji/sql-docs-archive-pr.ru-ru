---
title: Выбор метода создания (мастер измерений) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.dimensionwizard.dimensiondefinition.f1
ms.assetid: 291b0b2d-a03a-4df6-82f7-90ad92d4d1cf
author: minewiskan
ms.author: owend
ms.openlocfilehash: 6338a0bde7865482fb7a98d7ec36ba5a71feb806
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728853"
---
# <a name="select-creation-method-dimension-wizard"></a><span data-ttu-id="40bf9-102">Выбор метода создания (мастер измерений)</span><span class="sxs-lookup"><span data-stu-id="40bf9-102">Select Creation Method (Dimension Wizard)</span></span>
  <span data-ttu-id="40bf9-103">Страница **Выбор метода создания** используется, чтобы выбрать метод создания измерения.</span><span class="sxs-lookup"><span data-stu-id="40bf9-103">Use the **Select Creation Method** page to select how to create the dimension.</span></span>  
  
 <span data-ttu-id="40bf9-104">**Открытие мастера измерений**</span><span class="sxs-lookup"><span data-stu-id="40bf9-104">**To open the Dimension Wizard**</span></span>  
  
-   <span data-ttu-id="40bf9-105">В [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]обозревателе решений \*\*\*\* щелкните правой кнопкой мыши папку **Измерения** для проекта [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , а затем выберите команду **Новое измерение**.</span><span class="sxs-lookup"><span data-stu-id="40bf9-105">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], in **Solution Explorer**, right-click the **Dimensions** folder for an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project, and then click **New Dimension**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="40bf9-106">Варианты</span><span class="sxs-lookup"><span data-stu-id="40bf9-106">Options</span></span>  
 <span data-ttu-id="40bf9-107">**Использовать существующую таблицу**</span><span class="sxs-lookup"><span data-stu-id="40bf9-107">**Use an existing table**</span></span>  
 <span data-ttu-id="40bf9-108">Создайте измерение из одной или нескольких таблиц источника данных.</span><span class="sxs-lookup"><span data-stu-id="40bf9-108">Create a dimension from one or more tables in a data source.</span></span> <span data-ttu-id="40bf9-109">Какие атрибуты будут доступны для измерения, будет зависеть от структуры данных в таблице.</span><span class="sxs-lookup"><span data-stu-id="40bf9-109">The attributes that are available for the dimension will depend on the structure of the data in the table.</span></span>  
  
 <span data-ttu-id="40bf9-110">Дополнительные сведения см. в разделе [Создание измерения с помощью существующей таблицы](multidimensional-models/create-a-dimension-by-using-an-existing-table.md).</span><span class="sxs-lookup"><span data-stu-id="40bf9-110">For more information, see [Create a Dimension by Using an Existing Table](multidimensional-models/create-a-dimension-by-using-an-existing-table.md).</span></span>  
  
 <span data-ttu-id="40bf9-111">**Создать в источнике данных таблицу времени**</span><span class="sxs-lookup"><span data-stu-id="40bf9-111">**Generate a time table in the data source**</span></span>  
 <span data-ttu-id="40bf9-112">Создайте таблицу времени в базовом источнике данных, а затем используйте эту таблицу, чтобы создать измерение времени.</span><span class="sxs-lookup"><span data-stu-id="40bf9-112">Create a time table in the underlying data source and then use that table to create a time dimension.</span></span> <span data-ttu-id="40bf9-113">Используйте этот параметр, если такой таблицы не существует и нежелательно использовать скрипт для ее создания.</span><span class="sxs-lookup"><span data-stu-id="40bf9-113">Use this option when no such table exists and you do not want to use a script to create one.</span></span> <span data-ttu-id="40bf9-114">В новой таблице времени будут содержаться данные для указанных в мастере диапазона данных, атрибутов и календарей.</span><span class="sxs-lookup"><span data-stu-id="40bf9-114">The new time table will contain data for the date range, attributes, and calendars that you specify in the wizard.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="40bf9-115">Чтобы использовать этот параметр, необходимо иметь разрешение на создание объектов в базовом источнике данных.</span><span class="sxs-lookup"><span data-stu-id="40bf9-115">To use this option, you must have permission to create objects in the underlying data source.</span></span> <span data-ttu-id="40bf9-116">Если отсутствует разрешение на создание объектов в источнике данных, попытайтесь использовать параметр **Создать на сервере таблицу времени** .</span><span class="sxs-lookup"><span data-stu-id="40bf9-116">If you do not have permission to create objects on the data source, try to use the **Generate a time table on the server** option instead.</span></span>  
  
 <span data-ttu-id="40bf9-117">Дополнительные сведения см. в разделе [Создание измерения времени посредством формирования таблицы времени](multidimensional-models/create-a-time-dimension-by-generating-a-time-table.md).</span><span class="sxs-lookup"><span data-stu-id="40bf9-117">For more information, see [Create a Time Dimension by Generating a Time Table](multidimensional-models/create-a-time-dimension-by-generating-a-time-table.md).</span></span>  
  
 <span data-ttu-id="40bf9-118">**Создать на сервере таблицу времени**</span><span class="sxs-lookup"><span data-stu-id="40bf9-118">**Generate a time table on the server**</span></span>  
 <span data-ttu-id="40bf9-119">Создайте таблицу времени непосредственно на сервере, а затем используйте эту таблицу, чтобы создать измерение времени.</span><span class="sxs-lookup"><span data-stu-id="40bf9-119">Create a time table directly on the server and then use that table to create a time dimension.</span></span> <span data-ttu-id="40bf9-120">Используйте этот параметр, если отсутствует разрешение на создание объектов в базовом источнике данных.</span><span class="sxs-lookup"><span data-stu-id="40bf9-120">Use this option if you do not have permission to create objects in the underlying data source.</span></span> <span data-ttu-id="40bf9-121">В новом измерении времени будут содержаться данные для указанных в мастере диапазона данных, атрибутов и календарей.</span><span class="sxs-lookup"><span data-stu-id="40bf9-121">The new time dimension will contain data for the date range, attributes, and calendars that you specify in the wizard.</span></span>  
  
 <span data-ttu-id="40bf9-122">Дополнительные сведения см. в разделе [Создание измерения времени посредством формирования таблицы времени](multidimensional-models/create-a-time-dimension-by-generating-a-time-table.md).</span><span class="sxs-lookup"><span data-stu-id="40bf9-122">For more information, see [Create a Time Dimension by Generating a Time Table](multidimensional-models/create-a-time-dimension-by-generating-a-time-table.md).</span></span>  
  
 <span data-ttu-id="40bf9-123">**Создать в источнике данных таблицу, не содержащую время**</span><span class="sxs-lookup"><span data-stu-id="40bf9-123">**Generate a non-time table in the data source**</span></span>  
 <span data-ttu-id="40bf9-124">Спроектируйте измерение без базового реляционного источника данных, а затем создайте необходимую схему для источника данных.</span><span class="sxs-lookup"><span data-stu-id="40bf9-124">Design the dimension without an underlying relational data source, and then generate the necessary schema for the data source.</span></span> <span data-ttu-id="40bf9-125">Этот подход известен как нисходящее моделирование.</span><span class="sxs-lookup"><span data-stu-id="40bf9-125">This approach is known as top-down modeling.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="40bf9-126">Чтобы использовать этот параметр, необходимо иметь разрешение на создание объектов в базовом источнике данных.</span><span class="sxs-lookup"><span data-stu-id="40bf9-126">To use this option, you must have permission to create objects in the underlying data source.</span></span>  
  
 <span data-ttu-id="40bf9-127">Можно построить измерение с шаблоном или без него.</span><span class="sxs-lookup"><span data-stu-id="40bf9-127">You can build the dimension with or without a template.</span></span> <span data-ttu-id="40bf9-128">Чтобы построить измерение с шаблоном, выберите шаблон из списка **Шаблон** .</span><span class="sxs-lookup"><span data-stu-id="40bf9-128">To build the dimension with a template, select the template from the **Template** list.</span></span>  
  
 <span data-ttu-id="40bf9-129">Дополнительные сведения см. в разделе [Создание измерения путем формирования в источнике данных таблицы, отличной от таблицы времени](multidimensional-models/create-a-dimension-by-generating-a-non-time-table-in-the-data-source.md).</span><span class="sxs-lookup"><span data-stu-id="40bf9-129">For more information, see [Create a Dimension by Generating a Non-Time Table in the Data Source](multidimensional-models/create-a-dimension-by-generating-a-non-time-table-in-the-data-source.md).</span></span>  
  
 <span data-ttu-id="40bf9-130">**Шаблон**</span><span class="sxs-lookup"><span data-stu-id="40bf9-130">**Template**</span></span>  
 <span data-ttu-id="40bf9-131">Выберите шаблон, используемый для создания измерения.</span><span class="sxs-lookup"><span data-stu-id="40bf9-131">Select the template that you want to use to create the dimension.</span></span> <span data-ttu-id="40bf9-132">Шаблоны предоставляют полный набор определений атрибутов и иерархий, ориентированных на конкретную бизнес-задачу.</span><span class="sxs-lookup"><span data-stu-id="40bf9-132">Templates provide a complete set of attribute and hierarchy definitions oriented towards a specific business purpose.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="40bf9-133">Этот параметр доступен только при выбранном параметре **Создать в источнике данных таблицу, не содержащую время** .</span><span class="sxs-lookup"><span data-stu-id="40bf9-133">This option is only available when the **Generate a non-time table in the data source** option has been selected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40bf9-134">См. также:</span><span class="sxs-lookup"><span data-stu-id="40bf9-134">See Also</span></span>  
 <span data-ttu-id="40bf9-135">[Справка F1 мастера измерений](dimension-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="40bf9-135">[Dimension Wizard F1 Help](dimension-wizard-f1-help.md) </span></span>  
 <span data-ttu-id="40bf9-136">[Измерения &#40;Analysis Services многомерных данных&#41;](multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="40bf9-136">[Dimensions &#40;Analysis Services - Multidimensional Data&#41;](multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="40bf9-137">Измерения в многомерных моделях</span><span class="sxs-lookup"><span data-stu-id="40bf9-137">Dimensions in Multidimensional Models</span></span>](multidimensional-models/dimensions-in-multidimensional-models.md)  
  
  
