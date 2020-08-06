---
title: Добавление датчика в отчет (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 45da4fef-2b02-40e1-977c-f8f80d87155e
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 7125080d95e9c7b882df8d715cce5c6cf8aa6344
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87738006"
---
# <a name="add-a-gauge-to-a-report-report-builder-and-ssrs"></a><span data-ttu-id="d9dac-102">Добавление датчика в отчет (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="d9dac-102">Add a Gauge to a Report (Report Builder and SSRS)</span></span>
  <span data-ttu-id="d9dac-103">Если необходимо создать сводку данных в визуальном формате, то можно использовать область данных «Датчик».</span><span class="sxs-lookup"><span data-stu-id="d9dac-103">When you want to summarize data in a visual format, you can use a Gauge data region.</span></span> <span data-ttu-id="d9dac-104">После добавления области данных датчика в область конструктора можно перетаскивать поля набора данных отчета на панель данных в датчике.</span><span class="sxs-lookup"><span data-stu-id="d9dac-104">After you add a Gauge data region to the design surface, you can drag report dataset fields to a data pane on the gauge.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-gauge-to-your-report"></a><span data-ttu-id="d9dac-105">Добавление датчика в отчет</span><span class="sxs-lookup"><span data-stu-id="d9dac-105">To add a gauge to your report</span></span>  
  
1.  <span data-ttu-id="d9dac-106">Создайте отчет или откройте существующий отчет.</span><span class="sxs-lookup"><span data-stu-id="d9dac-106">Create a report or open an existing report.</span></span>  
  
2.  <span data-ttu-id="d9dac-107">На вкладке «Вставка» дважды щелкните «Датчик».</span><span class="sxs-lookup"><span data-stu-id="d9dac-107">On the Insert tab, double-click Gauge.</span></span> <span data-ttu-id="d9dac-108">Откроется диалоговое окно **Выбор типа датчика** .</span><span class="sxs-lookup"><span data-stu-id="d9dac-108">The **Select Gauge Type** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="d9dac-109">Выберите тип датчика, который нужно добавить в отчет.</span><span class="sxs-lookup"><span data-stu-id="d9dac-109">Select the type of gauge you want to add.</span></span> [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
    > [!NOTE]  
    >  <span data-ttu-id="d9dac-110">В отличие от диаграмм, для датчиков существует только два типа: линейный и радиальный.</span><span class="sxs-lookup"><span data-stu-id="d9dac-110">Unlike Chart, Gauge has only two types: linear and radial.</span></span> <span data-ttu-id="d9dac-111">В диалоговом окне **Выбор типа датчика** представлены шаблоны этих двух типов датчиков.</span><span class="sxs-lookup"><span data-stu-id="d9dac-111">The available gauges in the **Select a Gauge Type** dialog box are templates for these two types of gauges.</span></span> <span data-ttu-id="d9dac-112">По этой причине нельзя производить изменение типа датчика после его добавления в отчет.</span><span class="sxs-lookup"><span data-stu-id="d9dac-112">For this reason, you cannot change the gauge type after you add the gauge to your report.</span></span> <span data-ttu-id="d9dac-113">Чтобы изменить его тип, нужно удалить и вновь добавить датчик.</span><span class="sxs-lookup"><span data-stu-id="d9dac-113">You must delete and re-add a gauge to change its type.</span></span>  
  
     <span data-ttu-id="d9dac-114">Если в отчете нет источника данных и набора данных, то откроется диалоговое окно **Свойства источника данных** , которое поможет выполнить шаги для их создания.</span><span class="sxs-lookup"><span data-stu-id="d9dac-114">If the report has no data source and dataset the **Data Source Properties** dialog box opens and takes you through the steps to create both.</span></span> <span data-ttu-id="d9dac-115">Дополнительные сведения см. [в разделе Добавление и проверка подключения к данным или источника данных &#40;построитель отчетов и служб SSRS&#41;](../report-data/add-and-verify-a-data-connection-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="d9dac-115">For more information see, [Add and Verify a Data Connection or Data Source &#40;Report Builder and SSRS&#41;](../report-data/add-and-verify-a-data-connection-report-builder-and-ssrs.md).</span></span>  
  
     <span data-ttu-id="d9dac-116">Если в отчете есть источник данных, но нет набора данных, то откроется диалоговое окно **Свойства набора данных** , которое поможет выполнить шаги для его создания.</span><span class="sxs-lookup"><span data-stu-id="d9dac-116">If the report has a data source, but no dataset the **Dataset Properties** dialog box opens and takes you through the steps to create one.</span></span> <span data-ttu-id="d9dac-117">Дополнительные сведения см. в разделе [Создание общего или внедренного набора данных (построитель отчетов и службы SSRS)](../report-data/create-a-shared-dataset-or-embedded-dataset-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="d9dac-117">For more information, see [Create a Shared Dataset or Embedded Dataset &#40;Report Builder and SSRS&#41;](../report-data/create-a-shared-dataset-or-embedded-dataset-report-builder-and-ssrs.md).</span></span>  
  
4.  <span data-ttu-id="d9dac-118">Щелкните датчик, чтобы отобразить панель данных.</span><span class="sxs-lookup"><span data-stu-id="d9dac-118">Click the gauge to display the data pane.</span></span> <span data-ttu-id="d9dac-119">По умолчанию датчик имеет один указатель, соответствующий одному значению.</span><span class="sxs-lookup"><span data-stu-id="d9dac-119">By default, a gauge has one pointer corresponding to one value.</span></span> <span data-ttu-id="d9dac-120">Можно добавить дополнительные указатели.</span><span class="sxs-lookup"><span data-stu-id="d9dac-120">You can add additional pointers.</span></span>  
  
5.  <span data-ttu-id="d9dac-121">Добавьте одно поле из набора данных в область добавления поля данных.</span><span class="sxs-lookup"><span data-stu-id="d9dac-121">Add one field from the dataset to the data field drop-zone.</span></span> <span data-ttu-id="d9dac-122">Можно добавить только одно поле.</span><span class="sxs-lookup"><span data-stu-id="d9dac-122">You can add only one field.</span></span> <span data-ttu-id="d9dac-123">Если необходимо добавить несколько полей, необходимо добавить несколько указателей, по одному для каждого поля.</span><span class="sxs-lookup"><span data-stu-id="d9dac-123">If you want to display multiple fields, you must add additional pointers, one for each field.</span></span>  
  
     <span data-ttu-id="d9dac-124">Щелкните правой кнопкой мыши шкалу датчика и выберите пункт **Свойства шкалы**.</span><span class="sxs-lookup"><span data-stu-id="d9dac-124">Right-click the gauge scale, and select **Scale Properties**.</span></span> <span data-ttu-id="d9dac-125">Введите для шкалы значения **Минимум** и **Максимум** .</span><span class="sxs-lookup"><span data-stu-id="d9dac-125">Type a value for the **Minimum** and **Maximum** of the scale.</span></span> <span data-ttu-id="d9dac-126">Дополнительные сведения см. в разделе [Установка минимума и максимума на датчике (построитель отчетов и службы SSRS)](set-a-minimum-or-maximum-on-a-gauge-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="d9dac-126">For more information, see [Set a Minimum or Maximum on a Gauge &#40;Report Builder and SSRS&#41;](set-a-minimum-or-maximum-on-a-gauge-report-builder-and-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9dac-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="d9dac-127">See Also</span></span>  
 <span data-ttu-id="d9dac-128">[Вложенные области данных (построитель отчетов и службы SSRS)](nested-data-regions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="d9dac-128">[Nested Data Regions &#40;Report Builder and SSRS&#41;](nested-data-regions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="d9dac-129">Датчики (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="d9dac-129">Gauges &#40;Report Builder and SSRS&#41;</span></span>](gauges-report-builder-and-ssrs.md)  
  
  
