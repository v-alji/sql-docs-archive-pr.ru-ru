---
title: Диалоговое окно "Свойства набора данных" — "поля" (построитель отчетов) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10021"
ms.assetid: 75c7e54a-3d20-4c9a-88da-ab36dce2ce42
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2b766aa23cce390bc3ffdcf10efdb38efc91f3e9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656250"
---
# <a name="dataset-properties-dialog-box-fields-report-builder"></a><span data-ttu-id="600d8-102">Диалоговое окно «Свойства набора данных» — «Поля» (построитель отчетов)</span><span class="sxs-lookup"><span data-stu-id="600d8-102">Dataset Properties Dialog Box, Fields (Report Builder)</span></span>
  <span data-ttu-id="600d8-103">Чтобы изменить коллекцию полей для набора данных отчета, перейдите на вкладку **Поля** в диалоговом окне **Свойства набора данных** .</span><span class="sxs-lookup"><span data-stu-id="600d8-103">Select **Fields** on the **Dataset Properties** dialog box to change the field collection for the report dataset.</span></span> <span data-ttu-id="600d8-104">Список полей формируется автоматически, но с помощью вкладки **Поля** можно добавлять, изменять и удалять поля запросов и вычисляемые поля.</span><span class="sxs-lookup"><span data-stu-id="600d8-104">The fields list is automatically populated, but you can use **Fields** to add, edit, and delete query and calculated fields.</span></span>  
  
 <span data-ttu-id="600d8-105">Вычисляемые поля поддерживаются только во внедренных наборах данных.</span><span class="sxs-lookup"><span data-stu-id="600d8-105">Calculated fields are supported only on embedded datasets.</span></span> <span data-ttu-id="600d8-106">Дополнительные сведения см. в разделе [Внедренные и общие наборы данных отчета (построитель отчетов и службы SSRS)](report-data/report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="600d8-106">For more information, see [Report Embedded Datasets and Shared Datasets &#40;Report Builder and SSRS&#41;](report-data/report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="600d8-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="600d8-107">Options</span></span>  
 <span data-ttu-id="600d8-108">**Добавление**</span><span class="sxs-lookup"><span data-stu-id="600d8-108">**Add**</span></span>  
 <span data-ttu-id="600d8-109">Добавить в набор данных новое поле запроса или вычисляемое поле.</span><span class="sxs-lookup"><span data-stu-id="600d8-109">Add a new query or calculated field to the dataset.</span></span>  
  
 <span data-ttu-id="600d8-110">**Удалить**</span><span class="sxs-lookup"><span data-stu-id="600d8-110">**Delete**</span></span>  
 <span data-ttu-id="600d8-111">Удалить выбранное поле из набора данных.</span><span class="sxs-lookup"><span data-stu-id="600d8-111">Delete the selected field from the dataset.</span></span>  
  
 <span data-ttu-id="600d8-112">**Имя поля**</span><span class="sxs-lookup"><span data-stu-id="600d8-112">**Field Name**</span></span>  
 <span data-ttu-id="600d8-113">Введите имя для поля.</span><span class="sxs-lookup"><span data-stu-id="600d8-113">Type a name for the field.</span></span> <span data-ttu-id="600d8-114">Имя поля должно быть уникально в пределах набора данных.</span><span class="sxs-lookup"><span data-stu-id="600d8-114">The field must be unique within the dataset.</span></span> <span data-ttu-id="600d8-115">Имя каждого существующего поля в наборе данных заполняется заранее.</span><span class="sxs-lookup"><span data-stu-id="600d8-115">For each existing field in the dataset, the name is pre-populated.</span></span>  
  
 <span data-ttu-id="600d8-116">**Источник поля**</span><span class="sxs-lookup"><span data-stu-id="600d8-116">**Field Source**</span></span>  
 <span data-ttu-id="600d8-117">Введите значение для поля.</span><span class="sxs-lookup"><span data-stu-id="600d8-117">Enter a value for the field.</span></span>  
  
 <span data-ttu-id="600d8-118">Для вычисляемого поля источник должен иметь имя существующего поля, возвращаемого запросом набора данных, или имя выражения, создаваемого пользователем.</span><span class="sxs-lookup"><span data-stu-id="600d8-118">For a calculated field, the field source must be the name of an existing field retrieved by the dataset query, or an expression that you create.</span></span> <span data-ttu-id="600d8-119">Например, чтобы создать поле, представляющее удесятеренное значение поля Sales в запросе, используйте выражение `=10 * Fields!Sales.Value`.</span><span class="sxs-lookup"><span data-stu-id="600d8-119">For example, to create a field that represents 10 times the value in the query field Sales, use the expression `=10 * Fields!Sales.Value`.</span></span>  
  
 <span data-ttu-id="600d8-120">Для поля запроса источник должен иметь имя существующего поля, возвращаемого запросом набора данных.</span><span class="sxs-lookup"><span data-stu-id="600d8-120">For a query field, the field source must be the name of an existing field retrieved by the dataset query.</span></span>  
  
 <span data-ttu-id="600d8-121">**Выражение (fx)**</span><span class="sxs-lookup"><span data-stu-id="600d8-121">**Expression (fx)**</span></span>  
 <span data-ttu-id="600d8-122">Создайте или измените выражение для нового вычисляемого поля.</span><span class="sxs-lookup"><span data-stu-id="600d8-122">Add or change an expression for the new calculated field.</span></span> <span data-ttu-id="600d8-123">Эта кнопка появляется, только если нажать кнопку **Добавить** и выбрать пункт **Вычисляемое поле**.</span><span class="sxs-lookup"><span data-stu-id="600d8-123">This button only appears when you click **Add** and select **Calculated Field**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="600d8-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="600d8-124">See Also</span></span>  
 <span data-ttu-id="600d8-125">[Коллекция полей набора данных (построитель отчетов и службы SSRS)](report-data/dataset-fields-collection-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="600d8-125">[Dataset Fields Collection &#40;Report Builder and SSRS&#41;](report-data/dataset-fields-collection-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="600d8-126">[Создание общего набора данных или внедренного набора данных &#40;построитель отчетов и служб SSRS&#41;](report-data/create-a-shared-dataset-or-embedded-dataset-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="600d8-126">[Create a Shared Dataset or Embedded Dataset &#40;Report Builder and SSRS&#41;](report-data/create-a-shared-dataset-or-embedded-dataset-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="600d8-127">[Построитель отчетов справки по диалоговым окнам, панелям и мастерам](../../2014/reporting-services/report-builder-help-for-dialog-boxes-panes-and-wizards.md) </span><span class="sxs-lookup"><span data-stu-id="600d8-127">[Report Builder Help for Dialog Boxes, Panes, and Wizards](../../2014/reporting-services/report-builder-help-for-dialog-boxes-panes-and-wizards.md) </span></span>  
 <span data-ttu-id="600d8-128">[Диалоговое окно "Свойства набора данных", параметры &#40;построитель отчетов&#41;](report-data/dataset-properties-dialog-box-options-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="600d8-128">[Dataset Properties Dialog Box, Options &#40;Report Builder&#41;](report-data/dataset-properties-dialog-box-options-report-builder.md) </span></span>  
 <span data-ttu-id="600d8-129">[Диалоговое окно "Свойства набора данных" — фильтры &#40;построитель отчетов&#41;](../../2014/reporting-services/dataset-properties-dialog-box-filters-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="600d8-129">[Dataset Properties Dialog Box, Filters &#40;Report Builder&#41;](../../2014/reporting-services/dataset-properties-dialog-box-filters-report-builder.md) </span></span>  
 <span data-ttu-id="600d8-130">[Диалоговое окно "Свойства набора данных", параметры &#40;построитель отчетов&#41;](../../2014/reporting-services/dataset-properties-dialog-box-parameters-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="600d8-130">[Dataset Properties Dialog Box, Parameters &#40;Report Builder&#41;](../../2014/reporting-services/dataset-properties-dialog-box-parameters-report-builder.md) </span></span>  
 <span data-ttu-id="600d8-131">[Диалоговое окно "Свойства набора данных", построитель отчетов &#40;запросов&#41;](report-data/dataset-properties-dialog-box-query-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="600d8-131">[Dataset Properties Dialog Box, Query &#40;Report Builder&#41;](report-data/dataset-properties-dialog-box-query-report-builder.md) </span></span>  
 <span data-ttu-id="600d8-132">[Выражения (построитель отчетов и службы SSRS)](report-design/expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="600d8-132">[Expressions &#40;Report Builder and SSRS&#41;](report-design/expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="600d8-133">Подключения к данным, источники данных и строки подключения в построителе отчетов</span><span class="sxs-lookup"><span data-stu-id="600d8-133">Data Connections, Data Sources, and Connection Strings in Report Builder</span></span>](../../2014/reporting-services/data-connections-data-sources-and-connection-strings-in-report-builder.md)  
  
  
