---
title: Концепция параметров отчета (построитель отчетов и службы SSRS) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: b0aa2159-4e49-4713-8824-5ef9a9edbc62
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 4b740362daea83b50a62f0b4453ce818ab21ace7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730170"
---
# <a name="report-parameters-concept-report-builder-and-ssrs"></a><span data-ttu-id="5e9d6-102">Концепция параметров отчета (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="5e9d6-102">Report Parameters Concept (Report Builder and SSRS)</span></span>
  <span data-ttu-id="5e9d6-103">Можно добавлять в отчет параметры, чтобы добавлять ссылки на связанные отчеты, управлять видом отчета, фильтровать данные отчета или ограничить область отчета определенными пользователями или расположениями.</span><span class="sxs-lookup"><span data-stu-id="5e9d6-103">You can add parameters to a report to link related reports, to control the report appearance, to filter report data, or to narrow the scope of a report to specific users or locations.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
 <span data-ttu-id="5e9d6-104">Параметры отчета создаются следующими способами.</span><span class="sxs-lookup"><span data-stu-id="5e9d6-104">Report parameters are created in the following ways:</span></span>  
  
-   <span data-ttu-id="5e9d6-105">Автоматически при определении запроса набора данных, содержащего переменные запроса.</span><span class="sxs-lookup"><span data-stu-id="5e9d6-105">Automatically, when you define dataset query that contains query variables.</span></span> <span data-ttu-id="5e9d6-106">Для каждой переменной запроса создается соответствующий параметр запроса набора данных и параметр отчета с тем же именем.</span><span class="sxs-lookup"><span data-stu-id="5e9d6-106">For each query variable, a corresponding dataset query parameter and report parameter with the same names are created.</span></span> <span data-ttu-id="5e9d6-107">Параметр запроса может выступать в качестве ссылки на переменную запроса или выходной параметр хранимой процедуры.</span><span class="sxs-lookup"><span data-stu-id="5e9d6-107">A query parameter can be a reference to a query variable or to an input parameter for a stored procedure.</span></span>  
  
-   <span data-ttu-id="5e9d6-108">Автоматически при добавлении ссылки на общий набор данных, содержащий параметры запроса.</span><span class="sxs-lookup"><span data-stu-id="5e9d6-108">Automatically, when you add a reference to a shared dataset that contains query parameters.</span></span>  
  
-   <span data-ttu-id="5e9d6-109">Вручную при создании параметров отчета на панели данных отчета.</span><span class="sxs-lookup"><span data-stu-id="5e9d6-109">Manually, when you create report parameters in the Report Data pane.</span></span> <span data-ttu-id="5e9d6-110">Параметры являются одной из встроенных коллекций, которые можно включать в выражения отчета.</span><span class="sxs-lookup"><span data-stu-id="5e9d6-110">Parameters are one of the built-in collections that you can include in an expression in a report.</span></span> <span data-ttu-id="5e9d6-111">Так как выражения используются для задания значений повсюду в определении отчета, можно использовать параметры, чтобы управлять видом отчета или чтобы передавать значения в связанные вложенные отчеты или отчеты, которые тоже используют параметры.</span><span class="sxs-lookup"><span data-stu-id="5e9d6-111">Because expressions are used to define values throughout a report definition, you can use parameters to control report appearance or to pass values to related subreports or reports that also use parameters.</span></span>  
  
 <span data-ttu-id="5e9d6-112">Дополнительные сведения см. в разделе [Параметры отчета (построитель отчетов и конструктор отчетов)](report-parameters-report-builder-and-report-designer.md).</span><span class="sxs-lookup"><span data-stu-id="5e9d6-112">For more information, see [Report Parameters &#40;Report Builder and Report Designer&#41;](report-parameters-report-builder-and-report-designer.md).</span></span>  
  
 <span data-ttu-id="5e9d6-113">Параметры часто используются для фильтрации данных отчета как до, так и после того, как данные возвращены отчету.</span><span class="sxs-lookup"><span data-stu-id="5e9d6-113">Parameters are frequently used to filter report data both before and after the data is returned to the report.</span></span> <span data-ttu-id="5e9d6-114">Дополнительные сведения см. в разделе [Фильтрация, группирование и сортировка данных (построитель отчетов и службы SSRS)](filter-group-and-sort-data-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="5e9d6-114">For more information, see [Filter, Group, and Sort Data &#40;Report Builder and SSRS&#41;](filter-group-and-sort-data-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="5e9d6-115">При разработке отчета параметры отчета сохраняются в определении отчета.</span><span class="sxs-lookup"><span data-stu-id="5e9d6-115">When you design a report, report parameters are saved in the report definition.</span></span> <span data-ttu-id="5e9d6-116">При публикации отчета сохранение параметров отчета и управление ими осуществляется отдельно от определения отчета.</span><span class="sxs-lookup"><span data-stu-id="5e9d6-116">When you publish a report, report parameters are saved and managed separately from the report definition.</span></span> <span data-ttu-id="5e9d6-117">После сохранения отчета на сервере отчетов можно сделать следующее.</span><span class="sxs-lookup"><span data-stu-id="5e9d6-117">After you save the report to the report server, you can do the following:</span></span>  
  
-   <span data-ttu-id="5e9d6-118">Изменить значения параметров отчета напрямую на сервере отчетов, независимо от определения отчета.</span><span class="sxs-lookup"><span data-stu-id="5e9d6-118">Change report parameter values directly on the report server independently from the report definition.</span></span>  
  
-   <span data-ttu-id="5e9d6-119">Создать множественные связанные отчеты, в которых каждый связанный отчет представляет собой ссылку на определение отчета с отдельным набором значений параметров, который может управляться независимо на сервере отчетов.</span><span class="sxs-lookup"><span data-stu-id="5e9d6-119">Create multiple linked reports in which each linked report is a link to the report definition with a separate set of parameter values that can be managed independently on the report server.</span></span>  
  
 <span data-ttu-id="5e9d6-120">Для создания моментальных снимков отчета, журналов или подписок на опубликованный отчет необходимо понимать, как параметры отчета влияют на требования по разработке отчета.</span><span class="sxs-lookup"><span data-stu-id="5e9d6-120">If you plan to create report snapshots, histories, or subscriptions to a published report, you must understand how report parameters affect the design requirements for the report.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e9d6-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="5e9d6-121">See Also</span></span>  
 <span data-ttu-id="5e9d6-122">[Основные понятия разработки отчетов &#40;построитель отчетов и службы SSRS&#41;](report-authoring-concepts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="5e9d6-122">[Report Authoring Concepts &#40;Report Builder and SSRS&#41;](report-authoring-concepts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="5e9d6-123">[Внедренные и общие наборы данных отчета &#40;построитель отчетов и службы SSRS&#41;](../report-data/report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="5e9d6-123">[Report Embedded Datasets and Shared Datasets &#40;Report Builder and SSRS&#41;](../report-data/report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="5e9d6-124">Учебник. Добавление параметра к отчету (построитель отчетов)</span><span class="sxs-lookup"><span data-stu-id="5e9d6-124">Tutorial: Add a Parameter to Your Report &#40;Report Builder&#41;</span></span>](../tutorial-add-a-parameter-to-your-report-report-builder.md)  
  
  
